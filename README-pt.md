<div style="text-align: center; margin-bottom: 20px;">

![Banner do PivotPHP](assets/banner.svg)

---

**O Ecossistema PHP Evolutivo**

*Construindo ferramentas que se adaptam aos desenvolvedores, e não o contrário.*

[![Seguidores no GitHub](https://img.shields.io/github/followers/pivotphp?style=social)](https://github.com/pivotphp)

---

### ⚡ Pacotes focados | 🚀 Sintaxe Express.js | 🧪 Projeto de pesquisa

---

</div>

## 🎯 Nossa missão

**Tornar o desenvolvimento PHP prazeroso de novo.**

O PivotPHP é um ecossistema PHP experimental que explora padrões inspirados no Express.js — um
pacote pequeno e focado de cada vez.

> **🧪 Estado do projeto**: PivotPHP é um projeto de pesquisa e desenvolvimento. Ótimo para
> protótipos, estudo e validação de conceitos de API. Não recomendado para produção.

## 🏗️ Princípios de design

- **Fazer bem uma coisa** — cada pacote tem uma única responsabilidade (roteamento, HTTP, segurança).
- **PSR em tudo** — PSR-7 (HTTP), PSR-15 (middleware), PSR-17 (factories), PSR-11 (container),
  PSR-14 (eventos).
- **Pacotes pequenos** — o core apenas conecta as peças; recursos vivem em pacotes dedicados.

## 🌐 O ecossistema

| Pacote | Responsabilidade |
|---|---|
| [`pivotphp/core`](https://github.com/PivotPHP/pivotphp-core) | Microframework — conecta aplicação + roteamento + pipeline (container, eventos, hooks, extensões) |
| [`pivotphp/http`](https://github.com/PivotPHP/pivotphp-http) | Camada HTTP: PSR-7/PSR-17 (nyholm/psr7) + fachada Express (`ExpressRequest`/`ExpressResponse`), parsing de corpo, emissor |
| [`pivotphp/core-routing`](https://github.com/PivotPHP/pivotphp-core-routing) | Motor de roteamento — registrar, compilar, casar; grupos; arquivos estáticos |
| [`pivotphp/security`](https://github.com/PivotPHP/pivotphp-security) | Middlewares PSR-15 de segurança — CORS, headers, CSRF, JWT, rate limiting, proxies confiáveis |
| [`pivotphp/skeleton`](https://github.com/PivotPHP/pivotphp-skeleton) | Template inicial via `composer create-project` |
| [`pivotphp/benchmarks`](https://github.com/PivotPHP/pivotphp-benchmarks) | Suíte de benchmark em Docker (vs. Slim, Mezzio, Symfony, Webman) |

## 💎 Início rápido

```bash
composer create-project pivotphp/skeleton minha-api
cd minha-api && composer serve      # http://localhost:8000
```

```php
use PivotPHP\Core\Core\Application;

$app = new Application();

$app->get('/hello/:name', fn ($req, $res) => $res->json([
    'message' => "Olá, {$req->param('name')}!",
]));

$app->run();
```

Os handlers recebem `PivotPHP\Http\ExpressRequest`/`ExpressResponse` (fachada Express) sobre PSR-7.
Os middlewares de segurança vêm do [`pivotphp/security`](https://github.com/PivotPHP/pivotphp-security):

```php
use PivotPHP\Http\Factory\Psr17Factory;
use PivotPHP\Security\Cors\{CorsConfig, CorsMiddleware};
use PivotPHP\Security\Headers\SecurityHeadersMiddleware;

$factory = new Psr17Factory();
$app->use(new SecurityHeadersMiddleware());
$app->use(new CorsMiddleware($factory, new CorsConfig(['https://app.exemplo.com'])));
```

## 📊 Benchmarks

Benchmarks realistas e isolados em Docker (a mesma API de votação entre frameworks) ficam em
[`pivotphp/benchmarks`](https://github.com/PivotPHP/pivotphp-benchmarks). Frameworks PHP-FPM
(PivotPHP, Slim, Mezzio, Symfony) ficam na mesma faixa; runtimes assíncronos (Webman) são mais
rápidos, mas com arquitetura diferente. Os números são relativos ao WSL2 — veja os relatórios.

## 🤝 Comunidade

- **Reporte bugs / peça recursos** nas Issues de cada repositório (veja os templates em `.github/`)
- **Melhore a documentação** no [website](https://github.com/PivotPHP/website)
- **Participe** nas [Discussions](https://github.com/orgs/pivotphp/discussions)

## 📦 Arquivados

- `pivotphp/cycle-orm` — **[pausado](https://github.com/PivotPHP/pivotphp-specs/blob/main/SPECS/SPEC-103-archive-cycle-orm.md)**;
  aponta para o PivotPHP Core 1.x e ainda não foi migrado para o Core 4.x. Não está abandonado —
  será retomado.

## 📜 Licença e suporte

- **Licença:** MIT
- **Patrocínio:** [GitHub Sponsors](https://github.com/sponsors/CAFernandes)

---

<div align="center">

### ⭐ Dê uma estrela nos repositórios para apoiar!

**[💎 Core](https://github.com/PivotPHP/pivotphp-core)** • **[🌐 HTTP](https://github.com/PivotPHP/pivotphp-http)** • **[🛡️ Security](https://github.com/PivotPHP/pivotphp-security)** • **[🚀 Skeleton](https://github.com/PivotPHP/pivotphp-skeleton)**

*PivotPHP: código que evolui com você.*

</div>

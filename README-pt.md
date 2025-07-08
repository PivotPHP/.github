<div align="center">

![PivotPHP Banner](./assets/banner.svg)

---

**O Ecossistema PHP Evolutivo**

*Construindo ferramentas que se adaptam aos desenvolvedores, não o contrário.*

[![Inglês](https://img.shields.io/badge/README-em%20Ingl%C3%AAs-009c3b?style=flat&logo=Brazil&logoColor=white)](./profile/README.md)
[![Português](https://img.shields.io/badge/README-em%20Português-009c3b?style=flat&logo=Brazil&logoColor=white)](./README-pt.md)
[![GitHub followers](https://img.shields.io/github/followers/pivotphp?style=social)](https://github.com/pivotphp)
[![Twitter Follow](https://img.shields.io/twitter/follow/pivotphp?style=social)](https://twitter.com/pivotphp)
[![Discord](https://img.shields.io/discord/placeholder?color=7289da&label=Discord&logo=discord&logoColor=white)](https://discord.gg/pivotphp)

---

### ⚡ 13.374 req/seg | 🚀 Sintaxe Express.js | ⏱️ < 1ms Latência | 🧪 Perfeito para protótipos

---

</div>

## 🎯 Nossa Missão

**Tornar o desenvolvimento PHP alegre novamente.**

Depois de anos lutando com frameworks pesados e arquiteturas rígidas, acreditamos que os desenvolvedores PHP merecem algo melhor. PivotPHP não é apenas um framework—é uma filosofia de que o código deve evoluir com suas necessidades, não limitá-las.

> **🚧 Status do Projeto**: PivotPHP está em desenvolvimento ativo. Perfeito para prototipagem, aprendizado e validação de conceitos de API. Estamos trabalhando duro para torná-lo pronto para produção!

Estamos construindo um ecossistema onde:
- ⚡ **Performance vem primeiro**, não como repensamento
- 🔧 **Flexibilidade é o padrão**, não um recurso premium
- 💖 **Experiência do desenvolvedor importa**, do primeiro `composer require` ao deploy em produção
- 🌱 **Evolução é incentivada**, deixando seu código crescer naturalmente

## 💎 Por que PivotPHP?

### Para Startups
- **Deploy rápido**: Da ideia ao MVP em horas, não semanas
- **Custo zero**: Sem taxas de licença, sem serviços proprietários
- **Escale conforme cresce**: Microframework que se expande com suas necessidades

### Para Validação de Conceitos
- **Desenvolvimento ágil**: Crie MVPs em horas, não semanas
- **Iteração rápida**: Teste ideias e pivote conforme necessário
- **Código limpo**: Fácil de entender e modificar durante experimentação

### Para Desenvolvedores
- **Sintaxe familiar**: Se você conhece Express.js, você já conhece PivotPHP
- **PHP moderno**: Aproveite todo o poder do PHP 8.1+
- **Sem mágica**: Código previsível que faz exatamente o que você espera

## 🚀 Nosso Ecossistema

<table>
<tr>
<td width="50%">

### 🏗️ Framework Core
**[pivotphp-core](https://github.com/pivotphp/pivotphp-core)**
O coração do PivotPHP. Microframework rápido e sem opiniões com sintaxe inspirada no Express.js.

```php
// Crie uma aplicação em segundos
$app = new Application();

// Defina rotas com sintaxe expressiva
$app->get('/ola/:nome', fn($req, $res) =>
    $res->json(['mensagem' => "Olá, {$req->params->nome}!"])
);

// Inicie o servidor
$app->listen(8000);
```

</td>
<td width="50%">

### 🗄️ Integração com Banco
**[pivotphp-cycle-orm](https://github.com/pivotphp/pivotphp-cycle-orm)**
Camada de banco zero-config com Cycle ORM. Alta performance e type safety.

```php
// Conecte com uma linha
DB::connect('mysql://user:pass@localhost/db');

// Consulte com sintaxe fluente
$usuarios = Usuario::where('ativo', true)->get();
```

</td>
</tr>
<tr>
<td width="50%">

### 📚 Site Oficial
**[website](https://github.com/pivotphp/website)**
Documentação, guias e site de marketing. Construído com Jekyll para velocidade e simplicidade.

</td>
<td width="50%">

### 💡 Coleção de Exemplos
**[examples](https://github.com/pivotphp/examples)**
Aplicações do mundo real mostrando padrões e melhores práticas do PivotPHP.

</td>
</tr>
</table>

## 📊 Pelos Números

<div align="center">

| Métrica | Valor |
|---------|-------|
| **🚀 Performance** | 13.374 requisições/segundo |
| **🐘 Versão PHP** | 8.1+ |
| **💾 Uso de Memória** | 0-2MB média |
| **⏱️ Tempo de Resposta** | 0.07ms média |
| **📦 Dependências** | Core mínimo |

</div>

## 🔥 Construído para PHP Moderno

```php
// 🎯 Sintaxe limpa e expressiva
$app->group('/api/v1', function($group) {
    // Middleware em cadeia
    $group->middleware([Auth::jwt(), RateLimit::perMinute(100)]);

    // Rotas RESTful
    $group->get('/perfil', fn($req, $res) => $res->json($req->user));
    $group->resource('/posts', PostController::class);
});

// ✅ Validação type-safe
$dados = $req->validate([
    'email' => 'required|email',
    'nome' => 'required|string|max:100'
]);

// 🔌 WebSockets zero-config
$ws = new WebSocket\Server($app);
$ws->on('message', fn($socket, $dados) => $socket->broadcast('update', $dados));
```

## 🚀 Começando

### 👨‍💻 Para Desenvolvedores
```bash
# Crie sua primeira app PivotPHP
composer create-project pivotphp/skeleton minha-api
cd minha-api

# Inicie o servidor de desenvolvimento
php -S localhost:8000

# Ou use o servidor integrado
composer serve
```

**Sua primeira rota:**
```php
// index.php
require 'vendor/autoload.php';

$app = new PivotPHP\Application();

$app->get('/', fn($req, $res) =>
    $res->send('Olá, PivotPHP! 🚀')
);

$app->listen(8000);
```

### 🤝 Para Contribuidores
```bash
# Clone o repositório
git clone https://github.com/pivotphp/pivotphp-core.git
cd pivotphp-core

# Instale dependências
composer install

# Execute os testes
composer test

# Verifique a qualidade do código
composer quality:check
```

## 🌟 Comunidade

<div align="center">

**Junte-se a milhares de desenvolvedores construindo o futuro do PHP**

[![Discord](https://img.shields.io/badge/Discord-Entrar%20no%20Chat-7289da?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/pivotphp)
[![GitHub Discussions](https://img.shields.io/badge/GitHub-Discussions-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/orgs/pivotphp/discussions)
[![Twitter](https://img.shields.io/badge/Twitter-Seguir-1da1f2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/pivotphp)

</div>

### 🤝 Como Contribuir

Acreditamos que grandes softwares vêm de grandes comunidades. Veja como você pode ajudar:

- 🐛 **Reporte bugs** e solicite recursos em nossas [Issues](https://github.com/pivotphp/pivotphp-core/issues)
- 💻 **Submeta código** via Pull Requests em qualquer um dos nossos repositórios
- 📝 **Melhore docs** editando nosso [website](https://github.com/pivotphp/website)
- 💬 **Ajude outros** no [Discord](https://discord.gg/pivotphp) e [Discussions](https://github.com/orgs/pivotphp/discussions)
- ⭐ **Espalhe a palavra** dando estrela nos repos e compartilhando com amigos

## 💡 Filosofia

### 🧬 Design Evolutivo
Como DNA que se adapta a diferentes ambientes, o PivotPHP evolui com seu projeto. Comece simples, escale complexo, nunca reescreva.

### ⚡ Performance Primeiro
Cada linha de código é otimizada. Medimos tudo e tornamos a performance visível, porque APIs rápidas fazem usuários felizes.

### 😊 Felicidade do Desenvolvedor
O melhor framework é aquele que você não pensa sobre. PivotPHP sai do seu caminho enquanto fornece as ferramentas que você precisa.

### 👥 Dirigido pela Comunidade
Construído por desenvolvedores, para desenvolvedores. Cada decisão é feita pensando no uso do mundo real, não em ideais acadêmicos.

## 🗺️ Roadmap

<details>
<summary><strong>📍 Foco Atual (Q3 2025)</strong></summary>

- ✅ Estabilização do framework core
- ✅ Integração com Cycle ORM
- ✅ Coleção básica de middleware
- 🔄 Suite de benchmarking de performance (em progresso)
- 🔄 Ferramenta CLI oficial (em progresso)
- 📋 Package de utilitários de teste (planejado)

</details>

<details>
<summary><strong>🔜 Em Breve (Q4 2025)</strong></summary>

- 🔌 Integração com servidor WebSocket
- 💾 Camada avançada de cache
- 📝 Geração OpenAPI/Swagger
- 🐳 Containers Docker para desenvolvimento
- 🎨 Extensão VS Code
- 🚀 Guias de deployment

</details>

<details>
<summary><strong>🚀 Visão Futura (2026)</strong></summary>

- 🔗 Suporte GraphQL
- ⚡ Subscriptions em tempo real
- 🏗️ Toolkit para microserviços
- ☁️ Integrações com plataformas cloud
- 🔐 Recursos de segurança enterprise
- 🎤 Palestras e workshops em conferências

</details>

## 👨‍💻 Sobre o Criador

**[Caio Alberto Fernandes](https://github.com/CAFernandes)** começou o PivotPHP após 6 anos de frustração com frameworks PHP existentes. O que começou como um experimento de fim de semana para trazer a elegância do Express.js para o PHP cresceu e virou um movimento por melhores ferramentas para desenvolvedores.

*"Acredito que os melhores frameworks são invisíveis—eles amplificam suas habilidades sem impor suas opiniões. PivotPHP é minha tentativa de construir essa camada invisível para desenvolvedores PHP."*

## 📄 Licença & Suporte

- 📜 **Licença:** MIT (livre para uso comercial)
- 💬 **Suporte:** Dirigido pela comunidade via Discord e GitHub
- ❤️ **Patrocínio:** [GitHub Sponsors](https://github.com/sponsors/pivotphp)

---

<div align="center">

### ⭐ Dê estrela nos nossos repositórios para mostrar seu apoio!

**[Framework Core](https://github.com/pivotphp/pivotphp-core)** • **[Cycle ORM](https://github.com/pivotphp/pivotphp-cycle-orm)** • **[Website](https://github.com/pivotphp/website)** • **[Exemplos](https://github.com/pivotphp/examples)**

---

**Feito com ❤️ pela comunidade PHP, para a comunidade PHP.**

*PivotPHP: Código que evolui com você.*

</div>

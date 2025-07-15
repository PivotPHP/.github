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

### ⚡ Benchmarks de Alta Performance | 🚀 Sintaxe Express.js | 🧪 Desenvolvimento Ativo | 🔬 Projeto de Pesquisa

---

</div>

## 🎯 Nossa Missão

**Tornar o desenvolvimento PHP alegre novamente.**

Depois de anos lutando com frameworks pesados e arquiteturas rígidas, acreditamos que os desenvolvedores PHP merecem algo melhor. PivotPHP é um framework experimental explorando padrões inspirados no Express.js em PHP.

> **🧪 Status do Projeto**: PivotPHP é um projeto de pesquisa e desenvolvimento. Perfeito para prototipagem, aprendizado e validação de conceitos de API. Atualmente não recomendado para uso em produção.

Estamos construindo um ecossistema onde:
- ⚡ **Performance vem primeiro**, não como repensamento
- 🔧 **Flexibilidade é o padrão**, não um recurso premium
- 💖 **Experiência do desenvolvedor importa**, do primeiro `composer require` ao deploy em produção
- 🌱 **Evolução é incentivada**, deixando seu código crescer naturalmente

## 🤔 Por que PivotPHP?

<table>
<tr>
<td>

**🚀 APIs de Performance Excepcional**
- 41.000+ ops/sec média (Core v1.1.4)
- 105.786 ops/sec criação de aplicação
- 0,0095ms tempo médio de resposta
- Suporte a Array Callable (PHP 8.4+)
- Benchmarks Docker validados

</td>
<td>

**🎯 Desenvolvedor em Primeiro Lugar**
- Simplicidade tipo Express.js
- Zero configuração
- Design de API intuitivo

</td>
<td>

**🧪 Ideal para Prototipagem**
- Desenvolvimento rápido de API
- Validação rápida de conceitos
- Tempo mínimo de configuração

</td>
</tr>
</table>

Estamos construindo um ecossistema onde:
- ⚡ **Performance vem primeiro**, não como repensamento
- 🔧 **Flexibilidade é o padrão**, não um recurso premium
- 💝 **Experiência do desenvolvedor importa**, do primeiro `composer require` ao deploy em produção
- 🌱 **Evolução é incentivada**, deixando seu código crescer naturalmente

## 🌐 Nosso Ecossistema

### Framework Core & Extensões Oficiais

<table>
<tr>
<td width="50%">

### 💎 Framework Core
**[pivotphp-core](https://github.com/pivotphp/pivotphp-core)**
O coração do PivotPHP. Microframework rápido e sem opiniões com sintaxe inspirada no Express.js.

```php
// 🚀 Construa APIs em segundos
$app = new Application();

$app->get('/ola/:nome', fn($req, $res) =>
    $res->json(['mensagem' => "Olá, {$req->params->nome}!"])
);

$app->run(); // É isso! Zero boilerplate
```

**Recursos:**
- Roteamento inspirado no Express.js
- Compatível com PSR-7/PSR-15
- Middleware de segurança integrado
- Autenticação JWT & API Key
- v1.1.4: Architectural Excellence & Performance Optimization Edition

</td>
<td width="50%">

### 🗄️ Extensão Cycle ORM
**[pivotphp-cycle-orm](https://github.com/pivotphp/pivotphp-cycle-orm)** `composer require pivotphp/cycle-orm`

Integração poderosa de ORM com banco de dados com zero configuração.

```php
// 🔍 Conexão em uma linha, consultas type-safe
$app->register(new CycleServiceProvider([
    'dbal' => ['databases' => ['default' => [
        'connection' => 'mysql://user:pass@localhost/db'
    ]]]
]));

$usuarios = Usuario::where('ativo', true)
    ->with('posts')
    ->limit(10)
    ->get(); // Otimização automática de queries
```

**Recursos:**
- Migrações automáticas
- Gerenciamento de relacionamentos
- Suporte a transações
- Múltiplas conexões de banco

</td>
</tr>
<tr>
<td width="50%">

### ⚡ Extensão ReactPHP
**[pivotphp-reactphp](https://github.com/pivotphp/pivotphp-reactphp)** `composer require pivotphp/reactphp`

Runtime assíncrono para aplicações de longa duração.

```php
// 🔄 Servidor contínuo sem reinicializações
$app->register(new ReactServiceProvider([
    'server' => ['host' => '0.0.0.0', 'port' => 8080]
]));

$app->runAsync(); // Event loop não-bloqueante
```

**Recursos:**
- Arquitetura orientada a eventos
- Suporte WebSocket (em breve)
- Operações I/O assíncronas
- Timer e tarefas periódicas

</td>
<td width="50%">

### 📊 Suite de Benchmarking
**[pivotphp-benchmarks](https://github.com/pivotphp/pivotphp-benchmarks)**

Ferramentas abrangentes de teste de performance e comparação.

```bash
# Execute benchmarks com Docker
docker-compose up
php run-benchmarks.php
```

**Recursos:**
- Testes isolados baseados em Docker
- Comparações entre frameworks
- Profiling de memória
- Análise de tempo de resposta

</td>
</tr>
</table>

### Extensões da Comunidade

<table>
<tr>
<td width="33%">

#### 📝 Swagger/OpenAPI
**pivotphp/swagger**
```php
$app->register(new SwaggerProvider([
    'version' => '3.0',
    'title' => 'Minha API'
]));
```

</td>
<td width="33%">

#### 📧 Serviço de Email
**pivotphp/mail**
```php
$app->mail->send(
    to: 'user@example.com',
    subject: 'Bem-vindo!',
    template: 'welcome'
);
```

</td>
<td width="33%">

#### 🚦 Sistema de Filas
**pivotphp/queue**
```php
$app->queue->push(
    new SendEmailJob($user)
);
```

</td>
</tr>
</table>

### Criando Sua Própria Extensão

```php
// 1. Crie o Service Provider
class MyExtensionServiceProvider extends ServiceProvider
{
    public function register(): void
    {
        $this->container->singleton('myservice', MyService::class);
    }
    
    public function boot(): void
    {
        $this->app->get('/my-route', [MyController::class, 'handle']);
    }
}

// 2. Registre em sua app
$app->register(new MyExtensionServiceProvider());
```

**Diretrizes para Extensões:**
- Siga a convenção de nomes `pivotphp-{nome}`
- Forneça testes abrangentes
- Documente com exemplos
- Marque como `pivotphp-extension` no Packagist

## 📊 Pelos Números

<div align="center">

| Métrica | Valor |
|---------|-------|
| **Performance Core** | 41.000+ ops/sec (v1.1.4) |
| **Melhor Performance** | 105.786 ops/sec (criação app) |
| **Latência** | 0,0095ms tempo médio |
| **Uso de Memória** | ~17.5MB (todas operações) |
| **Extensões** | Core + ORM + ReactPHP |
| **Status** | Pesquisa & Desenvolvimento |

</div>

## 🔥 Construído para PHP Moderno

```php
// 🔒 API segura com autenticação JWT em 5 linhas
$app->group('/api/v1', function($group) {
    $group->middleware([Auth::jwt(), RateLimit::perMinute(100)]);
    $group->get('/perfil', fn($req, $res) => $res->json($req->user));
    $group->resource('/posts', PostController::class);
});

// ✅ Validação type-safe pronta para usar
$dados = $req->validate([
    'email' => 'required|email',
    'nome' => 'required|string|max:100'
]);

// 🔌 Recursos em tempo real em 2 linhas
$ws = new WebSocket\Server($app);
$ws->on('message', fn($socket, $dados) => $socket->broadcast('update', $dados));
```

## 🚀 Começando

### 👨‍💻 Início Rápido (60 segundos)
```bash
# Crie sua primeira app PivotPHP
composer create-project pivotphp/skeleton minha-api
cd minha-api && php -S localhost:8000

# 🎉 Sua API está rodando em http://localhost:8000
```

### 🤝 Para Contribuidores
```bash
# Junte-se ao desenvolvimento
git clone https://github.com/pivotphp/pivotphp-core.git
cd pivotphp-core
composer install && composer test
```

## 🤝 Comunidade

<div align="center">

**Junte-se a milhares de desenvolvedores construindo o futuro do PHP**

[![Discord](https://img.shields.io/badge/Discord-Entrar%20no%20Chat-7289da?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/pivotphp)
[![GitHub Discussions](https://img.shields.io/badge/GitHub-Discussions-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/orgs/pivotphp/discussions)
[![Twitter](https://img.shields.io/badge/Twitter-Seguir-1da1f2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/pivotphp)

</div>

### Como Contribuir

Acreditamos que grandes softwares vêm de grandes comunidades. Veja como você pode ajudar:

- **Reporte bugs** e solicite recursos em nossas [Issues](https://github.com/pivotphp/pivotphp-core/issues)
- **Submeta código** via Pull Requests em qualquer um dos nossos repositórios
- **Melhore docs** editando nosso [website](https://github.com/pivotphp/website)
- **Ajude outros** no [Discord](https://discord.gg/pivotphp) e [Discussions](https://github.com/orgs/pivotphp/discussions)
- **Espalhe a palavra** dando estrela nos repos e compartilhando com amigos

## 💡 Filosofia

### 🌱 Design Evolutivo
Como DNA que se adapta a diferentes ambientes, o PivotPHP evolui com seu projeto. Comece simples, escale complexo, nunca reescreva.

### ⚡ Performance Primeiro
Cada linha de código é otimizada. Medimos tudo e tornamos a performance visível, porque APIs rápidas fazem usuários felizes.

### 💝 Felicidade do Desenvolvedor
O melhor framework é aquele que você não pensa sobre. PivotPHP sai do seu caminho enquanto fornece as ferramentas que você precisa.

### 🤝 Dirigido pela Comunidade
Construído por desenvolvedores, para desenvolvedores. Cada decisão é feita pensando no uso do mundo real, não em ideais acadêmicos.

## 🗺️ Roadmap

<details>
<summary><strong>Foco Atual (Q3 2025)</strong></summary>

- Estabilização do framework core ✅
- Integração com Cycle ORM ✅
- Extensão ReactPHP ✅
- Coleção básica de middleware ✅
- Suite de benchmarking de performance ✅
- Modo de alta performance (v1.1.0) ✅
- Ferramenta CLI oficial (em progresso)
- Package de utilitários de teste (planejado)

</details>

<details>
<summary><strong>Em Breve (Q4 2025)</strong></summary>

**Extensões Oficiais:**
- pivotphp/websocket - Servidor WebSocket em tempo real
- pivotphp/cache - Cache multi-driver (Redis, Memcached)
- pivotphp/swagger - Auto-geração OpenAPI/Swagger
- pivotphp/queue - Processamento de jobs em background
- pivotphp/mail - Abstração de serviço de email

**Ferramentas do Desenvolvedor:**
- Containers Docker de desenvolvimento
- Extensão VS Code com snippets
- Plugin PHPStorm
- Guias de deployment (Heroku, AWS, DigitalOcean)

</details>

<details>
<summary><strong>Visão Futura (2026)</strong></summary>

**Extensões Avançadas:**
- pivotphp/graphql - Implementação de servidor GraphQL
- pivotphp/grpc - Suporte a serviços gRPC
- pivotphp/events - Barramento de eventos distribuído
- pivotphp/admin - Gerador de painel admin automático
- pivotphp/testing - Utilitários avançados de teste

**Recursos Enterprise:**
- Suporte multi-tenancy
- Middleware de segurança avançada
- Toolkit para microserviços
- Integrações com plataformas cloud
- Palestras e workshops em conferências

</details>

## 👨‍💻 Sobre o Criador

**[Caio Alberto Fernandes](https://github.com/CAFernandes)** começou o PivotPHP após 6 anos de frustração com frameworks PHP existentes. O que começou como um experimento de fim de semana para trazer a elegância do Express.js para o PHP cresceu e virou um movimento por melhores ferramentas para desenvolvedores.

*"Acredito que os melhores frameworks são invisíveis—eles amplificam suas habilidades sem impor suas opiniões. PivotPHP é minha tentativa de construir essa camada invisível para desenvolvedores PHP."*

## 📜 Licença & Suporte

- **Licença:** MIT (livre para uso comercial)
- **Suporte:** Dirigido pela comunidade via Discord e GitHub
- **Patrocínio:** [GitHub Sponsors](https://github.com/sponsors/pivotphp)

---

<div align="center">

### ⭐ Dê estrela nos nossos repositórios para mostrar seu apoio!

**[💎 Framework Core](https://github.com/pivotphp/pivotphp-core)** • **[🗄️ Cycle ORM](https://github.com/pivotphp/pivotphp-cycle-orm)** • **[📚 Website](https://github.com/pivotphp/website)** • **[🎓 Exemplos](https://github.com/pivotphp/examples)**

---

**Feito com amor pela comunidade PHP, para a comunidade PHP.**

*PivotPHP: Código que evolui com você.*

</div>

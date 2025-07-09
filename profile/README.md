<div align="center">

![PivotPHP Banner](../assets/banner.svg)

---

**The Evolutionary PHP Ecosystem**

*Building tools that adapt to developers, not the other way around.*

[![Inglês](https://img.shields.io/badge/README-em%20Ingl%C3%AAs-009c3b?style=flat&logo=Brazil&logoColor=white)](./README.md)
[![Português](https://img.shields.io/badge/README-em%20Português-009c3b?style=flat&logo=Brazil&logoColor=white)](../README-pt.md)
[![GitHub followers](https://img.shields.io/github/followers/pivotphp?style=social)](https://github.com/pivotphp)
[![Twitter Follow](https://img.shields.io/twitter/follow/pivotphp?style=social)](https://twitter.com/pivotphp)
[![Discord](https://img.shields.io/discord/placeholder?color=7289da&label=Discord&logo=discord&logoColor=white)](https://discord.gg/pivotphp)

---

### ⚡ 13,374 req/s | 🚀 Express.js syntax | ⏱️ < 1ms Latency | 🧪 Perfect for prototyping

---

</div>

## 🎯 Our Mission

**Making PHP development joyful again.**

After years of wrestling with heavyweight frameworks and rigid architectures, we believe PHP developers deserve better. PivotPHP isn't just a framework—it's a philosophy that code should evolve with your needs, not constrain them.

> **🚧 Project Status**: PivotPHP is under active development. Perfect for prototyping, learning, and validating API concepts. We're working hard to make it production-ready!

## 🤔 Why PivotPHP?

<table>
<tr>
<td>

**🚀 Lightning Fast**
- 13,374 req/s throughput
- < 1ms response time
- 0-2MB memory footprint

</td>
<td>

**🎯 Developer First**
- Express.js-like simplicity
- Zero configuration
- Intuitive API design

</td>
<td>

**🧪 Ideal for Prototyping**
- Rapid API development
- Quick concept validation
- Minimal setup time

</td>
</tr>
</table>

We're building an ecosystem where:
- ⚡ **Performance comes first**, not as an afterthought
- 🔧 **Flexibility is the default**, not a premium feature
- 💝 **Developer experience matters**, from first `composer require` to production deploy
- 🌱 **Evolution is encouraged**, letting your code grow naturally

## 🌐 Our Ecosystem

### Core Framework & Official Extensions

<table>
<tr>
<td width="50%">

### 💎 Core Framework
**[pivotphp-core](https://github.com/pivotphp/pivotphp-core)**
The heart of PivotPHP. Fast, unopinionated microframework with Express.js-inspired syntax.

```php
// 🚀 Build APIs in seconds
$app = new Application();

$app->get('/hello/:name', fn($req, $res) =>
    $res->json(['message' => "Hello, {$req->params->name}!"])
);

$app->run(); // That's it! Zero boilerplate
```

**Features:**
- Express.js-inspired routing
- PSR-7/PSR-15 compliant
- Built-in security middleware
- JWT & API Key authentication
- v1.1.0: High-performance mode with object pooling

</td>
<td width="50%">

### 🗄️ Cycle ORM Extension
**[pivotphp-cycle-orm](https://github.com/pivotphp/pivotphp-cycle-orm)** `composer require pivotphp/cycle-orm`

Powerful database ORM integration with zero configuration.

```php
// 🔍 One line connection, type-safe queries
$app->register(new CycleServiceProvider([
    'dbal' => ['databases' => ['default' => [
        'connection' => 'mysql://user:pass@localhost/db'
    ]]]
]));

$users = User::where('active', true)
    ->with('posts')
    ->limit(10)
    ->get(); // Automatic query optimization
```

**Features:**
- Automatic migrations
- Relationship management
- Transaction support
- Multiple database connections

</td>
</tr>
<tr>
<td width="50%">

### ⚡ ReactPHP Extension
**[pivotphp-reactphp](https://github.com/pivotphp/pivotphp-reactphp)** `composer require pivotphp/reactphp`

Async runtime for long-running applications.

```php
// 🔄 Continuous server without restarts
$app->register(new ReactServiceProvider([
    'server' => ['host' => '0.0.0.0', 'port' => 8080]
]));

$app->runAsync(); // Non-blocking event loop
```

**Features:**
- Event-driven architecture
- WebSocket support (coming soon)
- Async I/O operations
- Timer and periodic tasks

</td>
</tr>
</table>

### Community Extensions

<table>
<tr>
<td width="33%">

#### 📝 Swagger/OpenAPI
**pivotphp/swagger**
```php
$app->register(new SwaggerProvider([
    'version' => '3.0',
    'title' => 'My API'
]));
```

</td>
<td width="33%">

#### 📧 Mail Service
**pivotphp/mail**
```php
$app->mail->send(
    to: 'user@example.com',
    subject: 'Welcome!',
    template: 'welcome'
);
```

</td>
<td width="33%">

#### 🚦 Queue System
**pivotphp/queue**
```php
$app->queue->push(
    new SendEmailJob($user)
);
```

</td>
</tr>
</table>

### Creating Your Own Extension

```php
// 1. Create Service Provider
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

// 2. Register in your app
$app->register(new MyExtensionServiceProvider());
```

**Extension Guidelines:**
- Follow `pivotphp-{name}` naming convention
- Provide comprehensive tests
- Document with examples
- Tag as `pivotphp-extension` on Packagist

## 📊 By the Numbers

<div align="center">

| Metric | Value |
|--------|-------|
| **Performance** | 13,374 requests/second |
| **PHP Version** | 8.1+ |
| **Memory Usage** | 0-2MB average |
| **Response Time** | 0.07ms average |
| **Dependencies** | Minimal core |

</div>

## 🔥 Built for Modern PHP

```php
// 🔒 Secure API with JWT auth in 5 lines
$app->group('/api/v1', function($group) {
    $group->middleware([Auth::jwt(), RateLimit::perMinute(100)]);
    $group->get('/profile', fn($req, $res) => $res->json($req->user));
    $group->resource('/posts', PostController::class);
});

// ✅ Type-safe validation out of the box
$data = $req->validate([
    'email' => 'required|email',
    'name' => 'required|string|max:100'
]);

// 🔌 Real-time features in 2 lines
$ws = new WebSocket\Server($app);
$ws->on('message', fn($socket, $data) => $socket->broadcast('update', $data));
```

## 🚀 Getting Started

### 👨‍💻 Quick Start (60 seconds)
```bash
# Create your first PivotPHP app
composer create-project pivotphp/skeleton my-api
cd my-api && php -S localhost:8000

# 🎉 Your API is now running at http://localhost:8000
```

### 🤝 For Contributors
```bash
# Join the development
git clone https://github.com/pivotphp/pivotphp-core.git
cd pivotphp-core
composer install && composer test
```

## 🤝 Community

<div align="center">

**Join thousands of developers building the future of PHP**

[![Discord](https://img.shields.io/badge/Discord-Join%20Chat-7289da?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/pivotphp)
[![GitHub Discussions](https://img.shields.io/badge/GitHub-Discussions-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/orgs/pivotphp/discussions)
[![Twitter](https://img.shields.io/badge/Twitter-Follow-1da1f2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/pivotphp)

</div>

### How to Contribute

We believe great software comes from great communities. Here's how you can help:

- **Report bugs** and request features in our [Issues](https://github.com/pivotphp/pivotphp-core/issues)
- **Submit code** via Pull Requests to any of our repositories
- **Improve docs** by editing our [website](https://github.com/pivotphp/website)
- **Help others** in [Discord](https://discord.gg/pivotphp) and [Discussions](https://github.com/orgs/pivotphp/discussions)
- **Spread the word** by starring our repos and sharing with friends

## 💡 Philosophy

### 🌱 Evolutionary Design
Like DNA that adapts to different environments, PivotPHP evolves with your project. Start simple, scale complex, never rewrite.

### ⚡ Performance First
Every line of code is optimized. We measure everything and make performance visible, because fast APIs make happy users.

### 💝 Developer Happiness
The best framework is the one you don't think about. PivotPHP stays out of your way while providing the tools you need.

### 🤝 Community Driven
Built by developers, for developers. Every decision is made with real-world usage in mind, not academic ideals.

## 🗺️ Roadmap

<details>
<summary><strong>Current Focus (Q3 2025)</strong></summary>

- Core framework stabilization ✅
- Cycle ORM integration ✅
- ReactPHP extension ✅
- Basic middleware collection ✅
- Performance benchmarking suite ✅
- High-performance mode (v1.1.0) ✅
- Official CLI tool (in progress)
- Testing utilities package (planned)

</details>

<details>
<summary><strong>Coming Soon (Q4 2025)</strong></summary>

**Official Extensions:**
- pivotphp/websocket - Real-time WebSocket server
- pivotphp/cache - Multi-driver caching (Redis, Memcached)
- pivotphp/swagger - OpenAPI/Swagger auto-generation
- pivotphp/queue - Background job processing
- pivotphp/mail - Email service abstraction

**Developer Tools:**
- Docker development containers
- VS Code extension with snippets
- PHPStorm plugin
- Deployment guides (Heroku, AWS, DigitalOcean)

</details>

<details>
<summary><strong>Future Vision (2026)</strong></summary>

**Advanced Extensions:**
- pivotphp/graphql - GraphQL server implementation
- pivotphp/grpc - gRPC service support
- pivotphp/events - Distributed event bus
- pivotphp/admin - Auto-admin panel generator
- pivotphp/testing - Advanced testing utilities

**Enterprise Features:**
- Multi-tenancy support
- Advanced security middleware
- Microservices toolkit
- Cloud platform integrations
- Conference talks and workshops

</details>

## 👨‍💻 About the Creator

**[Caio Alberto Fernandes](https://github.com/CAFernandes)** started PivotPHP after 6 years of frustration with existing PHP frameworks. What began as a weekend experiment to bring Express.js elegance to PHP has grown into a movement for better developer tools.

*"I believe the best frameworks are invisible—they amplify your skills without imposing their opinions. PivotPHP is my attempt to build that invisible layer for PHP developers."*

## 📜 License & Support

- **License:** MIT (free for commercial use)
- **Support:** Community-driven via Discord and GitHub
- **Sponsorship:** [GitHub Sponsors](https://github.com/sponsors/pivotphp)

---

<div align="center">

### ⭐ Star our repositories to show your support!

**[💎 Core Framework](https://github.com/pivotphp/pivotphp-core)** • **[🗄️ Cycle ORM](https://github.com/pivotphp/pivotphp-cycle-orm)** • **[📚 Website](https://github.com/pivotphp/website)** • **[🎓 Examples](https://github.com/pivotphp/examples)**

---

**Made with love by the PHP community, for the PHP community.**

*PivotPHP: Code that evolves with you.*

</div>

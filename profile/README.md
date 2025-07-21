<div align="center">

![PivotPHP Banner](../assets/banner.svg)

---

**The Evolutionary PHP Ecosystem**

*Building tools that adapt to developers, not the other way around.*

[![Inglês](https://img.shields.io/badge/README-em%20Ingl%C3%AAs-009c3b?style=flat&logo=Brazil&logoColor=white)](./README.md)
[![Português](https://img.shields.io/badge/README-em%20Português-009c3b?style=flat&logo=Brazil&logoColor=white)](../README-pt.md)
[![GitHub followers](https://img.shields.io/github/followers/pivotphp?style=social)](https://github.com/pivotphp)
[![Twitter Follow](https://img.shields.io/twitter/follow/pivotphp?style=social)](https://twitter.com/pivotphp)
[![Discord](https://img.shields.io/discord/placeholder?color=7289da&label=Discord&logo=discord&logoColor=white)](https://discord.gg/DMtxsP7z)

---

### ⚡ High-Performance Benchmarks | 🚀 Express.js syntax | 🧪 Active Development | 🔬 Research Project

---

</div>

## 🎯 Our Mission

**Making PHP development joyful again.**

After years of wrestling with heavyweight frameworks and rigid architectures, we believe PHP developers deserve better. PivotPHP is an experimental framework exploring Express.js-inspired patterns in PHP.

> **🧪 Project Status**: PivotPHP is a research and development project. Perfect for prototyping, learning, and validating API concepts. Currently not recommended for production use.

## 🤔 Why PivotPHP?

<table>
<tr>
<td>

**🚀 Exceptional Performance APIs**
- 2.122 req/sec peak HTTP (Docker v1.2.0)
- 1.418 req/sec average HTTP performance
- 3.6M ops/sec OpenAPI generation
- Array Callable support (PHP 8.4+)
- Docker-validated benchmarks

</td>
<td>

**🎯 Developer First**
- Express.js-like simplicity
- Zero configuration
- Intuitive API design

</td>
<td>

**🧪 Research & Development**
- Rapid API prototyping
- Framework concept validation
- Experimental features testing

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
**[pivotphp-core](https://github.com/PivotPHP/pivotphp-core)** 
[![Packagist](https://img.shields.io/packagist/v/pivotphp/core.svg)](https://packagist.org/packages/pivotphp/core)
[![Downloads](https://img.shields.io/packagist/dt/pivotphp/core.svg)](https://packagist.org/packages/pivotphp/core)

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
- Express.js-inspired routing with regex constraints
- PSR-7/PSR-15 hybrid implementation  
- Built-in security middleware (CSRF, XSS, Rate limiting)
- JWT & API Key authentication
- v1.2.0: Simplicity Edition - "Simplicidade sobre Otimização Prematura"

</td>
<td width="50%">

### 🗄️ Cycle ORM Extension
**[pivotphp-cycle-orm](https://github.com/PivotPHP/pivotphp-cycle-orm)** 
[![Packagist](https://img.shields.io/packagist/v/pivotphp/cycle-orm.svg)](https://packagist.org/packages/pivotphp/cycle-orm)
[![Downloads](https://img.shields.io/packagist/dt/pivotphp/cycle-orm.svg)](https://packagist.org/packages/pivotphp/cycle-orm)

`composer require pivotphp/cycle-orm`

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
- Zero-configuration setup
- Automatic migrations & schema compilation
- Repository pattern with type safety
- Transaction middleware & monitoring
- Multiple database connections (SQLite, MySQL)
- v1.0.1: Performance profiling & query logging

</td>
</tr>
<tr>
<td width="50%">

### ⚡ ReactPHP Extension
**[pivotphp-reactphp](https://github.com/PivotPHP/pivotphp-reactphp)** 
[![Packagist](https://img.shields.io/packagist/v/pivotphp/reactphp.svg)](https://packagist.org/packages/pivotphp/reactphp)
[![Downloads](https://img.shields.io/packagist/dt/pivotphp/reactphp.svg)](https://packagist.org/packages/pivotphp/reactphp)

`composer require pivotphp/reactphp`

Async runtime for long-running applications.

```php
// 🔄 Continuous server without restarts
$app->register(new ReactServiceProvider([
    'server' => ['host' => '0.0.0.0', 'port' => 8080]
]));

$app->runAsync(); // Non-blocking event loop
```

**Features:**
- Continuous runtime without restarts
- PSR-7 bridge compatibility
- Event-driven architecture  
- Memory management & isolation
- Global state protection
- v0.0.2: Stable production runtime

</td>
</tr>
</table>

### Community Extensions

The PivotPHP ecosystem is designed to be extended! We're excited to see what the community will build.

**Built-in Core Features:**
- 📝 **OpenAPI/Swagger** - Automatic API documentation generation (NEW v1.2.0)
- 🎯 **Interactive Swagger UI** - Zero-config API testing interface (/swagger)
- 🔄 **15+ Automatic Aliases** - Zero breaking changes guaranteed
- 🎓 **Educational Architecture** - Simple over complex implementations
- 🛡️ **Security Suite** - CSRF, XSS, Rate limiting built-in
- 📊 **Performance Monitoring** - Real-time metrics and profiling

**Future Extensions:**
- 🔌 **WebSocket Server** - Real-time communication (planned)
- 💾 **Advanced Caching** - Multi-driver support (concept)
- 📊 **Additional Middleware** - Extended security and performance features

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
| **HTTP Peak** | 2.122 req/sec (Docker v1.2.0) |
| **OpenAPI Generation** | 3.6M ops/sec (Swagger UI) |
| **HTTP Average** | 1.418 req/sec |
| **Memory Usage** | ~17.5MB (all operations) |
| **Extensions** | Core + ORM + ReactPHP |
| **Status** | Research & Development |

</div>

## 🔥 Built for Modern PHP

```php
// 📝 Automatic OpenAPI/Swagger in 3 lines (NEW v1.2.0)
use PivotPHP\Core\Middleware\Http\ApiDocumentationMiddleware;

$app->use(new ApiDocumentationMiddleware());
// ✅ Access: http://localhost:8080/swagger (Swagger UI)
// ✅ Access: http://localhost:8080/docs (OpenAPI JSON)

// 🔒 Secure API with JWT auth in 5 lines
$app->group('/api/v1', function($group) {
    $group->middleware([Auth::jwt(), RateLimit::perMinute(100)]);
    $group->get('/profile', fn($req, $res) => $res->json($req->user));
    $group->resource('/posts', PostController::class);
});

// 📚 PHPDoc-powered automatic documentation
$app->get('/users', function($req, $res) {
    /**
     * @summary List all users
     * @description Returns paginated list of users
     * @tags Users
     * @response 200 array List of users
     */
    return $res->json(['users' => User::all()]);
});
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
git clone https://github.com/PivotPHP/pivotphp-core.git
cd pivotphp-core
composer install && composer test
```

## 🤝 Community

<div align="center">

**Join thousands of developers building the future of PHP**

[![Discord](https://img.shields.io/badge/Discord-Join%20Chat-7289da?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/DMtxsP7z)
[![GitHub Discussions](https://img.shields.io/badge/GitHub-Discussions-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/orgs/pivotphp/discussions)
[![Twitter](https://img.shields.io/badge/Twitter-Follow-1da1f2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/pivotphp)

</div>

### How to Contribute

We believe great software comes from great communities. Here's how you can help:

- **Report bugs** and request features in our [Issues](https://github.com/PivotPHP/pivotphp-core/issues)
- **Submit code** via Pull Requests to any of our repositories
- **Improve docs** by editing our [website](https://github.com/PivotPHP/website)
- **Help others** in [Discord](https://discord.gg/DMtxsP7z) and [Discussions](https://github.com/orgs/pivotphp/discussions)
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
- Cycle ORM integration v1.0.1 ✅
- ReactPHP extension v0.1.0 ✅ 
- Performance benchmarking suite ✅
- OpenAPI/Swagger integration v1.2.0 ✅
- Interactive API documentation ✅
- Simplified educational architecture ✅
- Zero breaking changes system ✅

</details>

<details>
<summary><strong>Coming Soon (Q4 2025)</strong></summary>

**Community Extensions:**
- WebSocket integration for ReactPHP extension
- Enhanced middleware collection
- Testing utilities and helpers

**Developer Tools:**
- Docker development containers
- VS Code extension with snippets
- PHPStorm plugin
- Deployment guides (Heroku, AWS, DigitalOcean)

</details>

<details>
<summary><strong>Future Vision (2026)</strong></summary>

**Research Extensions:**
- Enhanced performance monitoring
- Advanced middleware patterns
- Extended PSR compliance features

**Long-term Vision:**
- Framework stabilization for production use
- Extended documentation and examples
- Community-driven development
- Educational resources and tutorials

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

**[💎 Core Framework](https://github.com/PivotPHP/pivotphp-core)** • **[🗄️ Cycle ORM](https://github.com/PivotPHP/pivotphp-cycle-orm)** • **[📚 Website](https://github.com/PivotPHP/website)** • **[🎓 Examples](https://github.com/PivotPHP/examples)**

---

**Made with love by the PHP community, for the PHP community.**

*PivotPHP: Code that evolves with you.*

</div>

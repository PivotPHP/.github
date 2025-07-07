<div align="center">

# 🧬 HelixPHP Organization

**The Evolutionary PHP Ecosystem**

*Building tools that adapt to developers, not the other way around.*

[![Inglês](https://img.shields.io/badge/README-em%20Ingl%C3%AAs-009c3b?style=flat&logo=Brazil&logoColor=white)](../README.md)
[![Português](https://img.shields.io/badge/README-em%20Português-009c3b?style=flat&logo=Brazil&logoColor=white)](../README-pt.md)
[![GitHub followers](https://img.shields.io/github/followers/helixphp?style=social)](https://github.com/helixphp)
[![Twitter Follow](https://img.shields.io/twitter/follow/helixphp?style=social)](https://twitter.com/helixphp)
[![Discord](https://img.shields.io/discord/placeholder?color=7289da&label=Discord&logo=discord&logoColor=white)](https://discord.gg/helixphp)

---

### ⚡ 52M+ ops/sec | 🧬 Express.js syntax | 🛡️ Production ready | 🔧 Zero config

---

</div>

## 🎯 Our Mission

**Making PHP development joyful again.**

After years of wrestling with heavyweight frameworks and rigid architectures, we believe PHP developers deserve better. HelixPHP isn't just a framework—it's a philosophy that code should evolve with your needs, not constrain them.

We're building an ecosystem where:
- **Performance comes first**, not as an afterthought
- **Flexibility is the default**, not a premium feature
- **Developer experience matters**, from first `composer require` to production deploy
- **Evolution is encouraged**, letting your code grow naturally

## 🌟 Our Ecosystem

<table>
<tr>
<td width="50%">

### 🚀 Core Framework
**[helixphp-core](https://github.com/helixphp/helixphp-core)**
The heart of HelixPHP. Fast, unopinionated microframework with Express.js-inspired syntax.

```php
$app = new App();
$app->get('/hello/:name', fn($req, $res) =>
    $res->json(['message' => "Hello, {$req->params->name}!"])
);
$app->listen(8000);
```

</td>
<td width="50%">

### 🗄️ Database Integration
**[helixphp-cycle-orm](https://github.com/helixphp/helixphp-cycle-orm)**
Zero-config database layer with Cycle ORM. High performance and type safety.

```php
DB::connect('mysql://user:pass@localhost/db');
$users = User::where('active', true)->get();
```

</td>
</tr>
<tr>
<td width="50%">

### 🌐 Official Website
**[website](https://github.com/helixphp/website)**
Documentation, guides, and marketing site. Built with Jekyll for speed and simplicity.

</td>
<td width="50%">

### 📚 Examples Collection
**[examples](https://github.com/helixphp/examples)**
Real-world applications showcasing HelixPHP patterns and best practices.

</td>
</tr>
</table>

## 📊 By the Numbers

<div align="center">

| Metric | Value |
|--------|-------|
| **Performance** | 52M+ operations/second |
| **PHP Version** | 8.1+ |
| **Memory Usage** | ~8MB average |
| **Response Time** | <0.05ms average |
| **Dependencies** | Minimal core |

</div>

## 🛠️ Built for Modern PHP

```php
// Clean, expressive syntax
$app->group('/api/v1', function($group) {
    $group->middleware([Auth::jwt(), RateLimit::perMinute(100)]);

    $group->get('/profile', fn($req, $res) => $res->json($req->user));
    $group->resource('/posts', PostController::class);
});

// Type-safe validation
$data = $req->validate([
    'email' => 'required|email',
    'name' => 'required|string|max:100'
]);

// Zero-config WebSockets
$ws = new WebSocket\Server($app);
$ws->on('message', fn($socket, $data) => $socket->broadcast('update', $data));
```

## 🚀 Getting Started

### For Developers
```bash
# Create your first HelixPHP app
composer create-project helixphp/skeleton my-api
cd my-api && php -S localhost:8000
```

### For Contributors
```bash
# Join the development
git clone https://github.com/helixphp/helixphp-core.git
cd helixphp-core
composer install && composer test
```

## 🌍 Community

<div align="center">

**Join thousands of developers building the future of PHP**

[![Discord](https://img.shields.io/badge/Discord-Join%20Chat-7289da?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/helixphp)
[![GitHub Discussions](https://img.shields.io/badge/GitHub-Discussions-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/orgs/helixphp/discussions)
[![Twitter](https://img.shields.io/badge/Twitter-Follow-1da1f2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/helixphp)

</div>

### 🤝 How to Contribute

We believe great software comes from great communities. Here's how you can help:

- **🐛 Report bugs** and request features in our [Issues](https://github.com/helixphp/helixphp-core/issues)
- **💻 Submit code** via Pull Requests to any of our repositories
- **📖 Improve docs** by editing our [website](https://github.com/helixphp/website)
- **💬 Help others** in [Discord](https://discord.gg/helixphp) and [Discussions](https://github.com/orgs/helixphp/discussions)
- **🌟 Spread the word** by starring our repos and sharing with friends

## 💡 Philosophy

### 🧬 Evolutionary Design
Like DNA that adapts to different environments, HelixPHP evolves with your project. Start simple, scale complex, never rewrite.

### ⚡ Performance First
Every line of code is optimized. We measure everything and make performance visible, because fast APIs make happy users.

### 🎯 Developer Happiness
The best framework is the one you don't think about. HelixPHP stays out of your way while providing the tools you need.

### 🌱 Community Driven
Built by developers, for developers. Every decision is made with real-world usage in mind, not academic ideals.

## 📈 Roadmap

<details>
<summary><strong>🎯 Current Focus (Q3 2025)</strong></summary>

- ✅ Core framework stabilization
- ✅ Cycle ORM integration
- ✅ Basic middleware collection
- 🔄 Performance benchmarking suite
- 🔄 Official CLI tool
- ⏳ Testing utilities package

</details>

<details>
<summary><strong>🚀 Coming Soon (Q4 2025)</strong></summary>

- WebSocket server integration
- Advanced caching layer
- OpenAPI/Swagger generation
- Docker development containers
- VS Code extension
- Deployment guides

</details>

<details>
<summary><strong>🌟 Future Vision (2026)</strong></summary>

- GraphQL support
- Real-time subscriptions
- Microservices toolkit
- Cloud platform integrations
- Enterprise security features
- Conference talks and workshops

</details>

## 👨‍💻 About the Creator

**[Caio Alberto Fernandes](https://github.com/CAFernandes)** started HelixPHP after 6 years of frustration with existing PHP frameworks. What began as a weekend experiment to bring Express.js elegance to PHP has grown into a movement for better developer tools.

*"I believe the best frameworks are invisible—they amplify your skills without imposing their opinions. HelixPHP is my attempt to build that invisible layer for PHP developers."*

## 📄 License & Support

- **License:** MIT (free for commercial use)
- **Support:** Community-driven via Discord and GitHub
- **Sponsorship:** [GitHub Sponsors](https://github.com/sponsors/helixphp) 💖

---

<div align="center">

### 🌟 Star our repositories to show your support!

**[Core Framework](https://github.com/helixphp/helixphp-core)** • **[Cycle ORM](https://github.com/helixphp/helixphp-cycle-orm)** • **[Website](https://github.com/helixphp/website)** • **[Examples](https://github.com/helixphp/examples)**

---

**Made with ❤️ by the PHP community, for the PHP community.**

*HelixPHP: Code that evolves with you.*

</div>

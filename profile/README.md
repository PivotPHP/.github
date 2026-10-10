<div style="text-align: center; margin-bottom: 20px;">

![PivotPHP Banner](../assets/banner.svg)

---

**The Evolutionary PHP Ecosystem**

*Building tools that adapt to developers, not the other way around.*

[![GitHub followers](https://img.shields.io/github/followers/pivotphp?style=social)](https://github.com/pivotphp)

---

### ⚡ Focused Packages | 🚀 Express.js syntax | 🧪 Research Project

---

</div>

## 🎯 Our Mission

**Making PHP development joyful again.**

PivotPHP is an experimental PHP ecosystem exploring Express.js-inspired patterns — one small,
focused package at a time.

> **🧪 Project Status**: PivotPHP is a research and development project. Perfect for prototyping,
> learning, and validating API concepts. Not recommended for production use.

## 🏗️ Design Principles

- **One thing well** — each package owns a single responsibility (routing, HTTP, security).
- **PSR everywhere** — PSR-7 (HTTP), PSR-15 (middleware), PSR-17 (factories), PSR-11 (container),
  PSR-14 (events).
- **Small packages** — the core wires things together; features live in dedicated packages.

## 🌐 The Ecosystem

| Package | Responsibility |
|---|---|
| [`pivotphp/core`](https://github.com/PivotPHP/pivotphp-core) | Microframework — wires app + routing + pipeline (container, events, hooks, extensions) |
| [`pivotphp/http`](https://github.com/PivotPHP/pivotphp-http) | HTTP layer: PSR-7/PSR-17 (nyholm/psr7) + Express facade (`ExpressRequest`/`ExpressResponse`), body parsing, emitter |
| [`pivotphp/core-routing`](https://github.com/PivotPHP/pivotphp-core-routing) | Routing engine — register, compile, match; groups; static files |
| [`pivotphp/security`](https://github.com/PivotPHP/pivotphp-security) | PSR-15 security middlewares — CORS, security headers, CSRF, JWT, rate limiting, trusted proxies |
| [`pivotphp/skeleton`](https://github.com/PivotPHP/pivotphp-skeleton) | `composer create-project` starter template |
| [`pivotphp/benchmarks`](https://github.com/PivotPHP/pivotphp-benchmarks) | Docker-isolated benchmark suite (vs. Slim, Mezzio, Symfony, Webman) |

## 💎 Quick Start

```bash
composer create-project pivotphp/skeleton my-api
cd my-api && composer serve      # http://localhost:8000
```

```php
use PivotPHP\Core\Core\Application;

$app = new Application();

$app->get('/hello/:name', fn ($req, $res) => $res->json([
    'message' => "Hello, {$req->param('name')}!",
]));

$app->run();
```

Handlers receive `PivotPHP\Http\ExpressRequest`/`ExpressResponse` (the Express facade) over PSR-7.
Security middlewares come from [`pivotphp/security`](https://github.com/PivotPHP/pivotphp-security):

```php
use PivotPHP\Http\Factory\Psr17Factory;
use PivotPHP\Security\Cors\{CorsConfig, CorsMiddleware};
use PivotPHP\Security\Headers\SecurityHeadersMiddleware;

$factory = new Psr17Factory();
$app->use(new SecurityHeadersMiddleware());
$app->use(new CorsMiddleware($factory, new CorsConfig(['https://app.example.com'])));
```

## 📊 Benchmarks

Realistic, Docker-isolated benchmarks (same voting API across frameworks) live in
[`pivotphp/benchmarks`](https://github.com/PivotPHP/pivotphp-benchmarks). PHP-FPM frameworks
(PivotPHP, Slim, Mezzio, Symfony) run in the same ballpark; async runtimes (Webman) are faster but
are a different architecture. Numbers are WSL2-relative — see the reports for details and caveats.

## 🤝 Community

- **Report bugs / request features** in each repository's Issues (see its `.github/` templates)
- **Improve docs** via the [website](https://github.com/PivotPHP/website)
- **Discuss** in [GitHub Discussions](https://github.com/orgs/pivotphp/discussions)

## 📦 Archived

- `pivotphp/cycle-orm` — **[paused](https://github.com/PivotPHP/pivotphp-specs/blob/main/SPECS/SPEC-103-archive-cycle-orm.md)**;
  targets PivotPHP Core 1.x and is not yet migrated to Core 4.x. Not abandoned — it will be
  revisited.

## 📜 License & Support

- **License:** MIT
- **Sponsorship:** [GitHub Sponsors](https://github.com/sponsors/CAFernandes)

---

<div align="center">

### ⭐ Star our repositories to show your support!

**[💎 Core](https://github.com/PivotPHP/pivotphp-core)** • **[🌐 HTTP](https://github.com/PivotPHP/pivotphp-http)** • **[🛡️ Security](https://github.com/PivotPHP/pivotphp-security)** • **[🚀 Skeleton](https://github.com/PivotPHP/pivotphp-skeleton)**

*PivotPHP: code that evolves with you.*

</div>

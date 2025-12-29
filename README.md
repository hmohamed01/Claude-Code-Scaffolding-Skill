# Project Scaffolding Skill for Claude Code

IDE-grade project scaffolding wizard comparable to WebStorm and PyCharm project wizards. Supports **70+ project types** across web, mobile, desktop, and backend development.

## Features

- **Interactive Wizard Workflow**: Step-by-step project configuration like JetBrains IDEs
- **50+ Project Types**: From simple HTML/CSS to complex full-stack applications
- **SDK/Environment Configuration**: Node.js, Python, Go, Rust, Java version selection
- **Framework-Specific Options**: TypeScript, CSS frameworks, state management, routing
- **Database & ORM Setup**: PostgreSQL, MySQL, SQLite, MongoDB with various ORMs
- **Code Quality Tools**: ESLint, Prettier, Ruff, mypy, golangci-lint, clippy
- **Testing Configuration**: Vitest, Jest, pytest, Go testing, Playwright
- **DevOps Ready**: Docker, docker-compose, GitHub Actions CI/CD

## Supported Project Types

### Static Websites (HTML/CSS/JS)
- HTML/CSS (no build tools)
- HTML + Sass/SCSS
- HTML + Tailwind CLI
- Landing Pages
- Multi-page Sites

### Frontend Web Frameworks
- React (Vite)
- Next.js 14 (App Router)
- Vue 3 / Nuxt 3
- SvelteKit
- Angular
- Astro
- Remix
- Solid.js
- Qwik
- Preact

### Mobile & Cross-Platform
- React Native
- Expo
- Flutter
- Tauri (Desktop)
- Electron
- Ionic

### Backend - JavaScript/TypeScript
- Express
- NestJS
- Fastify
- Hono
- Elysia
- tRPC
- Koa

### Backend - Python
- FastAPI
- Django / Django REST
- Flask
- Litestar

### Backend - Go
- Go + Gin
- Go + Fiber
- Go + Echo
- Go + Chi

### Backend - Rust
- Rust + Axum
- Rust + Actix
- Rust + Rocket

### Backend - Java/Kotlin
- Spring Boot
- Quarkus
- Ktor
- Micronaut

### Backend - Other
- PHP + Laravel
- Ruby on Rails
- .NET Web API

### Libraries & Packages
- TypeScript NPM Package
- Python PyPI Package
- Go Module
- Rust Crate

### CLI Tools
- Node.js CLI
- Python CLI (Typer/Click)
- Go CLI (Cobra)
- Rust CLI (Clap)

### Browser Extensions & Plugins
- Chrome Extension (Manifest V3)
- Firefox Extension
- VS Code Extension
- Figma Plugin
- Obsidian Plugin

### Serverless & Edge
- AWS Lambda
- Cloudflare Workers
- Vercel Functions
- Supabase Functions

### Full-Stack Templates
- T3 Stack (Next.js + tRPC + Prisma)
- MERN Stack
- PERN Stack
- MEAN Stack

### Monorepos
- Turborepo
- Nx Workspace
- pnpm Workspace

## Installation

### Option 1: Extract from Archive (Recommended)

```bash
# Extract directly to your Claude Code skills directory
unzip project-scaffolding.skill -d ~/.claude/skills/project-scaffolding
```

### Option 2: Copy Source Files

If you have the unpacked source files:

```bash
# macOS/Linux
mkdir -p ~/.claude/skills/project-scaffolding
cp -r SKILL.md scripts/ references/ ~/.claude/skills/project-scaffolding/
```

### Verify Installation

The skill will be available when you see it listed in your Claude Code skills. You can verify by checking:

```bash
ls ~/.claude/skills/project-scaffolding/
```

## Usage

### Basic Usage

Simply ask Claude to create a project:

```
Create a simple HTML/CSS website
```

```
Create a new React project with TypeScript and Tailwind
```

```
Set up a FastAPI backend with PostgreSQL and SQLAlchemy
```

```
Build a Chrome extension with React
```

```
Create a mobile app with Expo
```

```
Initialize a Go API with Gin and PostgreSQL
```

### Interactive Wizard

For detailed configuration, Claude will guide you through:

1. **Project Category & Type** - Choose from 70+ options
2. **Basic Configuration** - Name, description, author
3. **Language & SDK** - Version selection, package managers
4. **Framework Options** - CSS, state management, routing, ORM
5. **Code Quality** - Linting, formatting, testing
6. **DevOps** - Docker, CI/CD, deployment

### Example Workflows

#### Simple HTML/CSS Website
```
User: Create a simple website

Claude: I'll create a static HTML/CSS website:

**Structure:**
- Multi-page (Home, About, Contact)
- Mobile-first responsive CSS
- BEM naming convention
- Live Server for development

**Files:**
my-website/
├── index.html
├── about.html
├── contact.html
├── css/style.css
├── js/main.js
├── images/
└── README.md

Shall I create this?
```

#### Mobile App with Expo
```
User: Create a mobile app for iOS and Android

Claude: I recommend Expo for the easiest setup:

**Configuration:**
- TypeScript
- Expo Router (file-based navigation)
- NativeWind (Tailwind for React Native)
- Tab navigation template

Ready to scaffold?
```

#### Go Backend API
```
User: Create a Go API with PostgreSQL

Claude: I'll set up Go + Gin:

**Structure:**
- Standard Go layout (cmd/, internal/, pkg/)
- sqlc for type-safe SQL
- JWT authentication
- Docker + docker-compose

**Features:**
- Swagger/OpenAPI docs
- Graceful shutdown
- Rate limiting

Proceed?
```

## Configuration Options

### JavaScript/TypeScript

| Option | Choices |
|--------|---------|
| Runtime | Node.js 18/20/22, Bun, Deno |
| Package Manager | npm, yarn, pnpm, bun |
| CSS | Tailwind, CSS Modules, Styled Components, Emotion |
| State | Zustand, Jotai, Redux, TanStack Query |
| Testing | Vitest, Jest, Playwright |

### Python

| Option | Choices |
|--------|---------|
| Version | 3.10, 3.11, 3.12, 3.13 |
| Environment | venv, uv, poetry, pipenv, conda |
| ORM | SQLAlchemy 2.0, SQLModel, Tortoise, Beanie |
| Linting | Ruff, Flake8+Black, Pylint |
| Testing | pytest |

### Go

| Option | Choices |
|--------|---------|
| Version | 1.21, 1.22, 1.23 |
| Framework | Gin, Fiber, Echo, Chi |
| Database | sqlc, GORM, sqlx, Ent |
| Testing | Built-in, Testify |

### Rust

| Option | Choices |
|--------|---------|
| Edition | 2021, 2024 |
| Framework | Axum, Actix, Rocket |
| Async Runtime | Tokio |
| Database | SQLx |

## What Gets Generated

### HTML/CSS Website
```
my-website/
├── index.html
├── about.html
├── contact.html
├── css/
│   ├── style.css
│   └── reset.css
├── js/main.js
├── images/
├── favicon.ico
├── robots.txt
└── README.md
```

### Next.js + tRPC + Prisma
```
my-nextjs-app/
├── .github/workflows/ci.yml
├── prisma/schema.prisma
├── src/
│   ├── app/
│   ├── components/
│   ├── lib/
│   ├── server/api/
│   └── types/
├── tests/
├── docker-compose.yml
├── Dockerfile
└── package.json
```

### Go + Gin
```
my-go-api/
├── cmd/server/main.go
├── internal/
│   ├── api/handlers/
│   ├── config/
│   ├── models/
│   └── repository/
├── db/migrations/
├── docker-compose.yml
├── Dockerfile
├── go.mod
└── Makefile
```

### Chrome Extension
```
my-extension/
├── src/
│   ├── popup/
│   ├── background/
│   ├── content/
│   └── options/
├── public/
│   ├── manifest.json
│   └── icons/
├── vite.config.ts
└── package.json
```

## Comparison with IDE Wizards

| Feature | WebStorm/PyCharm | This Skill |
|---------|------------------|------------|
| Project templates | ✅ | ✅ (70+) |
| SDK selection | ✅ | ✅ |
| Framework options | ✅ | ✅ |
| Database setup | ✅ | ✅ |
| Run configurations | ✅ | ✅ (VS Code) |
| Git initialization | ✅ | ✅ |
| Docker support | Limited | ✅ |
| CI/CD setup | ❌ | ✅ |
| Mobile apps | Limited | ✅ |
| Browser extensions | ❌ | ✅ |

## Quick Start Commands

### HTML/CSS
```bash
mkdir my-site && cd my-site && touch index.html style.css
# Or use boilerplate:
npx degit h5bp/html5-boilerplate my-site
```

### React + Vite
```bash
npm create vite@latest my-app -- --template react-ts
```

### Next.js (T3 Stack)
```bash
npx create-t3-app@latest my-app
```

### Expo (React Native)
```bash
npx create-expo-app@latest my-app --template tabs
```

### Astro
```bash
npm create astro@latest
```

### Tauri (Desktop)
```bash
npm create tauri-app@latest
```

### Chrome Extension
```bash
npm create plasmo@latest
```

## Files Included

```
project-scaffolding/
├── SKILL.md              # Main skill definition (70+ project types)
├── scripts/
│   └── scaffold.py       # Scaffolding engine
└── references/
    ├── frameworks.md     # Framework configuration guides
    ├── best-practices.md # Architecture patterns
    └── wizard-options.md # Detailed wizard configuration options
```

## Tips for Best Results

1. **Be specific** - "Create a React app with Tailwind and Zustand" works better than "create a web app"

2. **Mention your stack** - Include database, auth, or other requirements upfront

3. **Ask for recommendations** - Claude can suggest the best stack for your use case

4. **Start simple** - For HTML/CSS, just say "create a simple website"

5. **Specify platform** - For mobile, mention iOS/Android or both

## Version History

- **v2.2** - Restructured skill with progressive disclosure, added comprehensive wizard-options.md covering all 70+ project types, updated version defaults (Node.js 22, Python 3.12, Go 1.23)
- **v2.1** - Added HTML/CSS static websites, Go, Rust, Java backends, mobile frameworks, browser extensions, serverless
- **v2.0** - Initial enhanced release with 40+ project types
- **v1.0** - Basic web framework support

## License

MIT

---
name: project-scaffolding
description: IDE-grade project scaffolding wizard for creating new projects with comprehensive configuration. Supports 50+ project types including HTML/CSS websites, React, Next.js, Vue, Astro, Remix, React Native, Flutter, Expo, FastAPI, Django, Express, NestJS, Go/Gin, Rust/Axum, Spring Boot, Hono, Elysia, Chrome Extensions, VS Code Extensions, Tauri desktop apps, serverless functions, and more. Provides WebStorm/PyCharm-level project creation with interactive SDK selection, framework configuration, database setup, and DevOps tooling.
---

# Project Scaffolding Wizard

Professional-grade project scaffolding system comparable to WebStorm and PyCharm project wizards. Creates fully configured projects with SDK/interpreter setup, framework-specific options, database configuration, linting tools, and run configurations.

## Wizard Workflow

When a user requests a new project, follow this **interactive wizard workflow**:

### Step 1: Project Category & Type Selection

Present available project categories and types:

```
What type of project would you like to create?

═══════════════════════════════════════════════════════════════
STATIC WEBSITES (HTML/CSS/JS)
═══════════════════════════════════════════════════════════════
  1.  HTML/CSS        - Simple static website (no build tools)
  2.  HTML + Sass     - Static site with Sass/SCSS
  3.  HTML + Tailwind - Static site with Tailwind CLI
  4.  Landing Page    - Single page marketing/portfolio site
  5.  Multi-page Site - Traditional multi-page static website

═══════════════════════════════════════════════════════════════
FRONTEND WEB (FRAMEWORKS)
═══════════════════════════════════════════════════════════════
  6.  React           - SPA with Vite, hooks, modern tooling
  7.  Next.js         - Full-stack React with App Router (v14+)
  8.  Vue             - Vue 3 with Composition API
  9.  Nuxt            - Full-stack Vue framework
  10. Svelte          - SvelteKit application
  11. Angular         - Enterprise Angular application
  12. Astro           - Content-focused static site generator
  13. Remix           - Full-stack React with nested routing
  14. Solid           - Solid.js reactive UI framework
  15. Qwik            - Resumable framework for instant loading
  16. Preact          - Lightweight React alternative

═══════════════════════════════════════════════════════════════
MOBILE & CROSS-PLATFORM
═══════════════════════════════════════════════════════════════
  17. React Native    - Cross-platform mobile (iOS/Android)
  18. Expo            - React Native with managed workflow
  19. Flutter         - Google's cross-platform UI toolkit
  20. Tauri           - Lightweight desktop apps (Rust + Web)
  21. Electron        - Desktop apps with web technologies
  22. Ionic           - Hybrid mobile apps with web tech

═══════════════════════════════════════════════════════════════
BACKEND - JAVASCRIPT/TYPESCRIPT
═══════════════════════════════════════════════════════════════
  23. Express         - Minimal Node.js REST API
  24. NestJS          - Enterprise Node.js framework
  25. Fastify         - High-performance Node.js server
  26. Hono            - Ultrafast, multi-runtime framework
  27. Elysia          - Bun-first with end-to-end type safety
  28. tRPC            - End-to-end typesafe APIs
  29. Koa             - Expressive middleware framework

═══════════════════════════════════════════════════════════════
BACKEND - PYTHON
═══════════════════════════════════════════════════════════════
  30. FastAPI         - Modern async Python API (recommended)
  31. Django          - Full-featured Python framework
  32. Django REST     - Django with REST Framework
  33. Flask           - Lightweight Python framework
  34. Litestar        - High-performance async Python

═══════════════════════════════════════════════════════════════
BACKEND - GO
═══════════════════════════════════════════════════════════════
  35. Go + Gin        - Fast HTTP framework for Go
  36. Go + Fiber      - Express-inspired Go framework
  37. Go + Echo       - High performance Go framework
  38. Go + Chi        - Lightweight, composable router

═══════════════════════════════════════════════════════════════
BACKEND - RUST
═══════════════════════════════════════════════════════════════
  39. Rust + Axum     - Ergonomic async web framework
  40. Rust + Actix    - Powerful, fast actor framework
  41. Rust + Rocket   - Type-safe, boilerplate-free framework

═══════════════════════════════════════════════════════════════
BACKEND - JAVA/KOTLIN
═══════════════════════════════════════════════════════════════
  42. Spring Boot     - Enterprise Java framework
  43. Quarkus         - Cloud-native Java (fast startup)
  44. Ktor            - Kotlin async framework by JetBrains
  45. Micronaut       - Modern JVM framework

═══════════════════════════════════════════════════════════════
BACKEND - OTHER
═══════════════════════════════════════════════════════════════
  46. PHP + Laravel   - Popular PHP framework
  47. Ruby on Rails   - Convention over configuration
  48. .NET Web API    - C# ASP.NET Core API

═══════════════════════════════════════════════════════════════
LIBRARIES & PACKAGES
═══════════════════════════════════════════════════════════════
  49. TypeScript Lib  - NPM package with TypeScript
  50. Python Package  - PyPI package with modern tooling
  51. Go Module       - Go module/library
  52. Rust Crate      - Rust library (lib or bin)

═══════════════════════════════════════════════════════════════
CLI TOOLS
═══════════════════════════════════════════════════════════════
  53. Node CLI        - Node.js command-line tool
  54. Python CLI      - Python CLI with Typer/Click
  55. Go CLI          - Go CLI with Cobra
  56. Rust CLI        - Rust CLI with Clap

═══════════════════════════════════════════════════════════════
BROWSER EXTENSIONS & PLUGINS
═══════════════════════════════════════════════════════════════
  57. Chrome Extension     - Manifest V3 browser extension
  58. Firefox Extension    - WebExtension for Firefox
  59. VS Code Extension    - Visual Studio Code extension
  60. Figma Plugin         - Figma plugin with UI
  61. Obsidian Plugin      - Obsidian.md plugin

═══════════════════════════════════════════════════════════════
SERVERLESS & EDGE
═══════════════════════════════════════════════════════════════
  62. AWS Lambda      - Serverless function (Node/Python)
  63. Cloudflare Workers - Edge functions with Hono
  64. Vercel Functions - Serverless API routes
  65. Supabase Functions - Edge functions with Deno

═══════════════════════════════════════════════════════════════
FULL-STACK TEMPLATES
═══════════════════════════════════════════════════════════════
  66. T3 Stack        - Next.js + tRPC + Prisma + Tailwind
  67. MERN Stack      - MongoDB + Express + React + Node
  68. PERN Stack      - PostgreSQL + Express + React + Node
  69. MEAN Stack      - MongoDB + Express + Angular + Node

═══════════════════════════════════════════════════════════════
MONOREPOS & WORKSPACES
═══════════════════════════════════════════════════════════════
  70. Turborepo       - High-performance monorepo
  71. Nx Workspace    - Smart monorepo tooling
  72. pnpm Workspace  - Simple pnpm workspace
```

### Step 2: Project Configuration

Gather these details based on project type:

**For ALL projects:**
- Project name (required)
- Project location/directory
- Description
- Author name
- License (MIT, Apache-2.0, GPL-3.0, ISC, Unlicense)

### Step 3: Language & SDK Configuration

**For HTML/CSS projects (no framework):**
```
Project Type:
  [ ] Simple HTML/CSS (no build tools)
  [ ] HTML + Sass/SCSS (with compilation)
  [ ] HTML + Tailwind CLI
  [ ] HTML + PostCSS

Features:
  [ ] Normalize.css / Reset CSS
  [ ] Google Fonts
  [ ] Font Awesome icons
  [ ] jQuery (if needed)
  [ ] Live Server setup

CSS Methodology:
  [ ] BEM naming convention
  [ ] SMACSS
  [ ] Utility-first
  [ ] None (custom)
```

**For JavaScript/TypeScript projects:**
```
Language Configuration:
  [x] TypeScript (recommended)
  [ ] JavaScript

If TypeScript selected:
  - Strict mode: [Yes/No]
  - Path aliases (@/*): [Yes/No]
  - Declaration files: [Yes/No]

Runtime:
  [ ] Node.js 18.x LTS
  [x] Node.js 20.x LTS (recommended)
  [ ] Node.js 22.x
  [ ] Bun (for Elysia, Hono)
  [ ] Deno

Package Manager:
  [ ] npm
  [ ] yarn
  [x] pnpm (recommended)
  [ ] bun
```

**For Python projects:**
```
Python Version:
  [ ] 3.10
  [x] 3.11 (recommended)
  [ ] 3.12
  [ ] 3.13

Environment Type:
  [x] venv (built-in, recommended)
  [ ] uv (fast, modern)
  [ ] poetry
  [ ] pipenv
  [ ] conda

Type Hints:
  [x] Full type annotations (recommended)
  [ ] Minimal
  [ ] None
```

**For Go projects:**
```
Go Version:
  [ ] 1.21
  [x] 1.22 (recommended)
  [ ] 1.23

Module Path: github.com/username/project
```

**For Rust projects:**
```
Rust Edition:
  [x] 2021 (recommended)
  [ ] 2024 (nightly)

Crate Type:
  [ ] Binary (executable)
  [x] Library
  [ ] Both
```

**For Java/Kotlin projects:**
```
Java Version:
  [ ] 17 LTS
  [x] 21 LTS (recommended)
  [ ] 22

Build Tool:
  [x] Gradle (Kotlin DSL)
  [ ] Gradle (Groovy)
  [ ] Maven
```

### Step 4: Framework-Specific Options

#### HTML/CSS Static Website Projects
```
Structure:
  [ ] Single page (index.html only)
  [x] Multi-page (index, about, contact, etc.)
  [ ] Landing page template

CSS Approach:
  [ ] Plain CSS
  [x] Sass/SCSS
  [ ] Tailwind CLI
  [ ] CSS Variables + Custom Properties

Features:
  [x] Responsive design (mobile-first)
  [x] SEO meta tags
  [ ] Open Graph tags
  [ ] Favicon set
  [ ] Sitemap.xml
  [ ] Robots.txt

JavaScript:
  [ ] None (pure HTML/CSS)
  [ ] Vanilla JS (minimal interactivity)
  [ ] Alpine.js (reactive)
  [ ] HTMX (server interactions)

Development:
  [x] Live Server / Browser Sync
  [ ] Sass watch mode
  [ ] Image optimization script
```

#### React Projects
```
Build Tool:
  [x] Vite (recommended - fast, modern)
  [ ] Create React App (legacy)

CSS Framework:
  [x] Tailwind CSS (recommended)
  [ ] CSS Modules
  [ ] Styled Components
  [ ] Emotion
  [ ] Vanilla Extract
  [ ] UnoCSS
  [ ] None

UI Component Library:
  [ ] None
  [ ] shadcn/ui (recommended)
  [ ] Radix UI
  [ ] Headless UI
  [ ] Chakra UI
  [ ] Material UI
  [ ] Ant Design

State Management:
  [ ] None (React Context only)
  [x] Zustand (recommended - simple)
  [ ] Jotai (atomic)
  [ ] Redux Toolkit
  [ ] TanStack Query (server state)

Data Fetching:
  [x] TanStack Query (recommended)
  [ ] SWR
  [ ] Apollo Client (GraphQL)
  [ ] None

Routing:
  [x] React Router v6 (recommended)
  [ ] TanStack Router
  [ ] None

Forms:
  [x] React Hook Form + Zod (recommended)
  [ ] Formik + Yup
  [ ] None

Testing:
  [x] Vitest + Testing Library (recommended)
  [ ] Jest + Testing Library
  [ ] None
```

#### Next.js Projects
```
Version & Router:
  [x] Next.js 14+ App Router (recommended)
  [ ] Next.js Pages Router

Features:
  [x] TypeScript
  [x] ESLint
  [x] Tailwind CSS
  [x] src/ directory
  [ ] Turbopack (experimental)

Database/ORM:
  [ ] None
  [x] Prisma (recommended)
  [ ] Drizzle
  [ ] Supabase

Authentication:
  [ ] None
  [x] NextAuth.js / Auth.js
  [ ] Clerk
  [ ] Lucia
  [ ] Custom JWT

API Style:
  [ ] REST (Route Handlers)
  [x] tRPC (recommended for full-stack)
  [ ] GraphQL (Apollo/Yoga)
```

#### Astro Projects
```
Template:
  [x] Minimal
  [ ] Blog
  [ ] Documentation (Starlight)
  [ ] Portfolio

Integrations:
  [ ] React
  [ ] Vue
  [ ] Svelte
  [ ] Solid
  [x] Tailwind CSS
  [ ] MDX

Deployment:
  [ ] Static (SSG)
  [x] Hybrid (SSG + SSR)
  [ ] Server (SSR)
```

#### React Native / Expo Projects
```
Template:
  [x] Expo (managed workflow - recommended)
  [ ] Expo (bare workflow)
  [ ] React Native CLI

Navigation:
  [x] Expo Router (file-based)
  [ ] React Navigation

Features:
  [x] TypeScript
  [ ] NativeWind (Tailwind)
  [ ] Tamagui
  [ ] Expo Router typed routes
```

#### Flutter Projects
```
Platforms:
  [x] Android
  [x] iOS
  [ ] Web
  [ ] Desktop (Windows/macOS/Linux)

State Management:
  [x] Riverpod (recommended)
  [ ] BLoC
  [ ] Provider
  [ ] GetX

Features:
  [ ] Firebase integration
  [ ] Supabase integration
  [ ] Local storage (Hive/Isar)
```

#### FastAPI Projects
```
Project Structure:
  [ ] Simple (single main.py)
  [x] Standard (app/ directory)
  [ ] Large-scale (domain-driven)

Database:
  [ ] None
  [ ] SQLite (development)
  [x] PostgreSQL (recommended)
  [ ] MySQL
  [ ] MongoDB

ORM:
  [x] SQLAlchemy 2.0 (recommended)
  [ ] SQLModel
  [ ] Tortoise ORM
  [ ] Beanie (MongoDB)

Authentication:
  [ ] None
  [x] JWT with python-jose
  [ ] OAuth2 with authlib
  [ ] Session-based

Features:
  [ ] Background tasks (Celery/ARQ)
  [ ] WebSocket support
  [ ] GraphQL (Strawberry)
  [ ] Redis caching
```

#### Go + Gin/Fiber Projects
```
Project Structure:
  [ ] Simple (single main.go)
  [x] Standard (internal/, cmd/, pkg/)
  [ ] Domain-driven

Database:
  [ ] None
  [x] PostgreSQL
  [ ] MySQL
  [ ] MongoDB
  [ ] SQLite

ORM/Query Builder:
  [x] sqlc (type-safe SQL)
  [ ] GORM
  [ ] sqlx
  [ ] Ent

Features:
  [ ] JWT authentication
  [ ] Rate limiting
  [ ] Swagger/OpenAPI
  [ ] Graceful shutdown
```

#### Rust + Axum Projects
```
Features:
  [x] Async runtime (Tokio)
  [ ] Database (SQLx + PostgreSQL)
  [ ] Tracing/logging
  [ ] Error handling (thiserror/anyhow)
  [ ] Configuration (config-rs)
```

#### Spring Boot Projects
```
Language:
  [x] Java
  [ ] Kotlin

Dependencies:
  [x] Spring Web
  [x] Spring Data JPA
  [ ] Spring Security
  [ ] Spring Cloud
  [ ] Spring Actuator

Database:
  [ ] H2 (dev)
  [x] PostgreSQL
  [ ] MySQL
  [ ] MongoDB
```

#### Chrome Extension Projects
```
Manifest Version:
  [x] Manifest V3 (required for new extensions)

Features:
  [ ] Popup UI
  [ ] Options page
  [ ] Background service worker
  [ ] Content scripts
  [ ] Side panel

UI Framework:
  [x] React + Vite
  [ ] Vue + Vite
  [ ] Svelte
  [ ] Vanilla JS
  [ ] Plasmo framework
```

#### VS Code Extension Projects
```
Extension Type:
  [ ] Language support
  [ ] Themes/colors
  [ ] Snippets
  [x] Commands/tools
  [ ] Webview

Features:
  [x] TypeScript
  [ ] Webview UI
  [ ] Language Server Protocol
  [ ] Testing setup
```

#### Tauri Desktop Projects
```
Frontend:
  [x] React + Vite
  [ ] Vue + Vite
  [ ] Svelte + Vite
  [ ] Solid + Vite
  [ ] Vanilla

Features:
  [ ] System tray
  [ ] Auto-updater
  [ ] Custom titlebar
  [ ] File system access
```

### Step 5: Code Quality & Tooling

```
Linting & Formatting:

JavaScript/TypeScript:
  [x] ESLint (flat config)
  [x] Prettier
  [ ] Biome (all-in-one)

CSS:
  [x] Stylelint (for CSS/SCSS projects)
  [ ] None

Python:
  [x] Ruff (recommended - fast, all-in-one)
  [ ] Flake8 + Black
  [ ] Pylint

Go:
  [x] golangci-lint
  [x] gofmt/goimports

Rust:
  [x] clippy
  [x] rustfmt

Pre-commit Hooks:
  [x] Yes - lint-staged + husky (JS)
  [x] Yes - pre-commit framework (Python)
  [ ] No
```

### Step 6: Testing Configuration

```
JavaScript/TypeScript:
  [x] Vitest (recommended - fast)
  [ ] Jest
  [ ] None

Python:
  [x] pytest
  [ ] unittest
  [ ] None

Go:
  [x] Built-in testing
  [ ] Testify
  [ ] None

Rust:
  [x] Built-in testing
  [ ] None

E2E Testing:
  [x] Playwright (recommended)
  [ ] Cypress
  [ ] None

Coverage:
  [x] Yes - with threshold (80%)
  [ ] Yes - reporting only
  [ ] No
```

### Step 7: DevOps & Deployment

```
Version Control:
  [x] Initialize Git repository
  [x] Add .gitignore
  [x] Create initial commit

CI/CD:
  [x] GitHub Actions
  [ ] GitLab CI
  [ ] None

Containerization:
  [x] Dockerfile (multi-stage)
  [x] docker-compose.yml
  [ ] None

Deployment Target:
  [ ] GitHub Pages (static HTML/CSS)
  [ ] Netlify (static/JAMstack)
  [ ] Vercel (Next.js/frontend)
  [ ] Railway
  [ ] Fly.io
  [ ] AWS (ECS/Lambda)
  [ ] Google Cloud Run
  [ ] Self-hosted
  [ ] None (decide later)
```

### Step 8: Additional Features

```
Documentation:
  [x] README.md with setup instructions
  [ ] API documentation (OpenAPI/Swagger)
  [ ] Storybook (component docs)
  [ ] Docusaurus/VitePress

Environment Management:
  [x] .env.example template
  [x] Config validation (Zod/Pydantic)

Monitoring:
  [ ] Structured logging
  [ ] Error tracking (Sentry)
  [ ] None
```

## Generated Project Structures

### HTML/CSS Static Website
```
my-website/
├── index.html
├── about.html
├── contact.html
├── css/
│   ├── style.css           # Main styles
│   ├── reset.css           # CSS reset/normalize
│   └── components/
│       ├── header.css
│       ├── footer.css
│       └── buttons.css
├── js/
│   └── main.js             # Optional vanilla JS
├── images/
│   ├── logo.svg
│   └── hero.jpg
├── fonts/                  # Local fonts (optional)
├── favicon.ico
├── robots.txt
├── sitemap.xml
├── .gitignore
└── README.md
```

### HTML + Sass Project
```
my-sass-website/
├── src/
│   ├── index.html
│   ├── about.html
│   └── scss/
│       ├── main.scss
│       ├── _variables.scss
│       ├── _mixins.scss
│       ├── _base.scss
│       ├── _layout.scss
│       └── components/
│           ├── _header.scss
│           ├── _footer.scss
│           └── _buttons.scss
├── dist/
│   ├── css/
│   │   └── style.css       # Compiled CSS
│   └── *.html              # Copied HTML
├── images/
├── package.json            # npm scripts for Sass
├── .gitignore
└── README.md
```

### Next.js + tRPC + Prisma (T3-style)
```
my-nextjs-app/
├── .github/workflows/ci.yml
├── prisma/
│   ├── schema.prisma
│   └── migrations/
├── src/
│   ├── app/
│   │   ├── (auth)/
│   │   ├── api/trpc/[trpc]/route.ts
│   │   ├── layout.tsx
│   │   ├── page.tsx
│   │   └── globals.css
│   ├── components/
│   │   ├── ui/
│   │   └── features/
│   ├── lib/
│   │   ├── auth.ts
│   │   ├── db.ts
│   │   └── utils.ts
│   ├── server/
│   │   ├── api/
│   │   │   ├── routers/
│   │   │   └── trpc.ts
│   │   └── db.ts
│   ├── hooks/
│   ├── types/
│   └── env.ts
├── tests/
├── .env.example
├── docker-compose.yml
├── next.config.js
├── tailwind.config.ts
├── tsconfig.json
└── package.json
```

### FastAPI + SQLAlchemy
```
my-fastapi-app/
├── .github/workflows/ci.yml
├── alembic/
│   ├── versions/
│   └── env.py
├── app/
│   ├── api/
│   │   ├── v1/
│   │   │   ├── endpoints/
│   │   │   └── router.py
│   │   └── deps.py
│   ├── core/
│   │   ├── config.py
│   │   └── security.py
│   ├── db/
│   │   ├── session.py
│   │   └── base.py
│   ├── models/
│   ├── schemas/
│   ├── services/
│   └── main.py
├── tests/
├── .env.example
├── alembic.ini
├── docker-compose.yml
├── Dockerfile
├── pyproject.toml
└── requirements.txt
```

### Go + Gin
```
my-go-api/
├── .github/workflows/ci.yml
├── cmd/
│   └── server/
│       └── main.go
├── internal/
│   ├── api/
│   │   ├── handlers/
│   │   ├── middleware/
│   │   └── routes.go
│   ├── config/
│   ├── models/
│   ├── repository/
│   └── service/
├── pkg/
│   └── utils/
├── db/
│   ├── migrations/
│   └── queries/
├── .env.example
├── docker-compose.yml
├── Dockerfile
├── go.mod
├── go.sum
├── Makefile
└── sqlc.yaml
```

### React Native / Expo
```
my-expo-app/
├── app/
│   ├── (tabs)/
│   │   ├── index.tsx
│   │   ├── explore.tsx
│   │   └── _layout.tsx
│   ├── _layout.tsx
│   └── +not-found.tsx
├── components/
│   ├── ui/
│   └── features/
├── hooks/
├── lib/
├── constants/
├── assets/
├── .env.example
├── app.json
├── babel.config.js
├── tsconfig.json
└── package.json
```

### Chrome Extension (Manifest V3)
```
my-chrome-extension/
├── src/
│   ├── popup/
│   │   ├── Popup.tsx
│   │   ├── index.tsx
│   │   └── index.html
│   ├── background/
│   │   └── service-worker.ts
│   ├── content/
│   │   └── content-script.ts
│   ├── options/
│   │   └── Options.tsx
│   └── lib/
├── public/
│   ├── icons/
│   └── manifest.json
├── vite.config.ts
├── tsconfig.json
└── package.json
```

### Tauri Desktop App
```
my-tauri-app/
├── src/              # Frontend (React/Vue/etc)
│   ├── components/
│   ├── App.tsx
│   └── main.tsx
├── src-tauri/        # Rust backend
│   ├── src/
│   │   ├── main.rs
│   │   └── lib.rs
│   ├── Cargo.toml
│   ├── tauri.conf.json
│   └── icons/
├── index.html
├── vite.config.ts
├── tsconfig.json
└── package.json
```

## CLI Integration

Use native CLI tools when available:

| Framework | CLI Command |
|-----------|-------------|
| Next.js | `npx create-next-app@latest` |
| React (Vite) | `npm create vite@latest -- --template react-ts` |
| Vue | `npm create vue@latest` |
| Nuxt | `npx nuxi@latest init` |
| Astro | `npm create astro@latest` |
| Remix | `npx create-remix@latest` |
| SvelteKit | `npm create svelte@latest` |
| Solid | `npm create solid@latest` |
| Expo | `npx create-expo-app@latest` |
| React Native | `npx @react-native-community/cli init` |
| Flutter | `flutter create` |
| Tauri | `npm create tauri-app@latest` |
| NestJS | `npx @nestjs/cli new` |
| Spring Boot | `spring init` or start.spring.io |
| Go | `go mod init` |
| Rust | `cargo new` |
| Chrome Ext | `npm create plasmo@latest` |

## Quick Start Templates

### Quick HTML/CSS Website
```bash
mkdir my-website && cd my-website
touch index.html style.css
# Or use a boilerplate
npx degit h5bp/html5-boilerplate my-website
```

### Quick HTML + Tailwind (CDN)
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Website</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">
  <h1 class="text-3xl font-bold">Hello World</h1>
</body>
</html>
```

### Quick T3 Stack
```bash
npx create-t3-app@latest my-app
```

### Quick Expo
```bash
npx create-expo-app@latest my-app --template tabs
```

### Quick Astro
```bash
npm create astro@latest my-site -- --template starlight
```

### Quick Tauri + React
```bash
npm create tauri-app@latest my-app -- --template react-ts
```

### Quick Chrome Extension
```bash
npm create plasmo@latest my-extension
```

## Triggering Patterns

Activate this skill when you see:
- "Create a new [framework] project"
- "Create a simple website"
- "Create HTML/CSS project"
- "Set up a [framework] application"
- "Initialize a new [language] project"
- "Scaffold a project with [technology]"
- "Start a new codebase"
- "Generate project boilerplate"
- "New project wizard"
- "Create [mobile/desktop/web] app"
- "Build a [Chrome/VS Code] extension"
- "Set up a monorepo"
- "Create a landing page"
- "Make a static website"

## Example Conversations

### Example 1: Simple HTML/CSS Website
```
User: Create a simple website with HTML and CSS

Claude: I'll help you create a static HTML/CSS website. Let me configure it:

**Project Type:**
- Multi-page static website
- Pages: Home, About, Contact

**Styling:**
- Plain CSS with CSS variables
- Mobile-first responsive design
- BEM naming convention

**Features:**
- SEO meta tags
- Favicon
- Live Server for development

**Structure:**
my-website/
├── index.html
├── about.html
├── contact.html
├── css/
│   ├── style.css
│   └── reset.css
├── js/
│   └── main.js
├── images/
└── README.md

Shall I create this structure?
```

### Example 2: Mobile App
```
User: Create a mobile app for iOS and Android

Claude: I'll help you create a cross-platform mobile app. What framework would you prefer?

1. **Expo** (recommended) - React Native with managed workflow, easiest setup
2. **React Native CLI** - More control, native module support
3. **Flutter** - Google's UI toolkit, Dart language

User: Expo

Claude: Great choice! Here's your Expo configuration:

**Project Details:**
- Name: my-mobile-app
- TypeScript: Yes
- Navigation: Expo Router (file-based)

**Features:**
- Tab navigation template
- NativeWind (Tailwind for RN)
- AsyncStorage for local data

Shall I proceed?
```

### Example 3: Chrome Extension
```
User: Build a Chrome extension

Claude: I'll help you create a Chrome extension. What features do you need?

**Extension Type:**
- [ ] Popup (toolbar button with UI)
- [ ] Content script (modifies web pages)
- [ ] Background service worker
- [ ] Side panel

**Tech Stack:**
- React + Vite + TypeScript
- Manifest V3 (required)
- Plasmo framework (optional, simplifies development)

What's the main purpose of your extension?
```

### Example 4: Full-Stack with tRPC
```
User: Create a full-stack app with type-safe API

Claude: For end-to-end type safety, I recommend the T3 Stack:

**T3 Stack Configuration:**
- Next.js 14 (App Router)
- tRPC (type-safe API)
- Prisma (type-safe ORM)
- Tailwind CSS
- NextAuth.js

**Database:**
- PostgreSQL (recommended)
- Local: docker-compose with Postgres

This gives you full type safety from database to frontend!
```

## Available Resources

- `scripts/scaffold.py` - Python scaffolding engine
- `references/frameworks.md` - Detailed framework guides
- `references/best-practices.md` - Architecture patterns
- `assets/templates/` - Pre-configured templates

## Version History

- **v2.1** - Added HTML/CSS static websites, landing pages, additional backend frameworks
- **v2.0** - Added 40+ project types including mobile, desktop, extensions, Go, Rust, serverless
- **v1.0** - Initial release with web frameworks

# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Claude Code skill** that provides IDE-grade project scaffolding functionality, comparable to WebStorm and PyCharm project wizards. It supports 70+ project types across web, mobile, desktop, and backend development.

### Architecture

```
project-scaffolding/
├── SKILL.md                 # Skill definition - user interface and wizard workflow
├── scripts/scaffold.py      # Core scaffolding engine (2900+ lines)
├── references/
│   ├── frameworks.md        # Framework-specific configuration guides
│   └── best-practices.md    # Architecture patterns and conventions
└── assets/                  # Templates and boilerplates
```

**Key architectural principles:**
- **SKILL.md** is the contract - it defines what projects can be created and the interactive wizard flow
- **scaffold.py** is the implementation - a comprehensive Python engine that generates project structures
- **references/** contains deep knowledge - framework configurations, best practices, tooling options

## How the Skill Works

### Trigger Patterns
The skill activates when users request project creation:
- "Create a new [framework] project"
- "Create a simple website" / "Create HTML/CSS project"
- "Set up a [language] application"
- "Initialize a [mobile/desktop/web] app"
- "Build a Chrome extension"

### Wizard Flow (SKILL.md Lines 10-688)
1. **Project Category & Type Selection** - Present 70+ options organized by category
2. **Basic Configuration** - Name, description, author, license
3. **Language & SDK** - Version selection (Node.js, Python, Go, Rust, Java)
4. **Framework Options** - CSS frameworks, state management, routing, ORM
5. **Code Quality Tools** - Linting, formatting, testing
6. **DevOps Configuration** - Docker, CI/CD, deployment targets

### Project Type Categories
- **Static Websites**: HTML/CSS, HTML+Sass, HTML+Tailwind, landing pages
- **Frontend**: React, Next.js, Vue, Nuxt, Svelte, Angular, Astro, Remix, Solid, Qwik
- **Mobile/Desktop**: React Native, Expo, Flutter, Tauri, Electron, Ionic
- **Backend (JS/TS)**: Express, NestJS, Fastify, Hono, Elysia, tRPC, Koa
- **Backend (Python)**: FastAPI, Django, Flask, Litestar
- **Backend (Go)**: Gin, Fiber, Echo, Chi
- **Backend (Rust)**: Axum, Actix, Rocket
- **Backend (Java/Kotlin)**: Spring Boot, Quarkus, Ktor, Micronaut
- **Libraries**: TypeScript NPM, Python PyPI, Go Module, Rust Crate
- **CLI Tools**: Node.js CLI, Python CLI (Typer/Click), Go CLI (Cobra), Rust CLI (Clap)
- **Extensions**: Chrome Extension, Firefox Extension, VS Code Extension, Figma Plugin
- **Serverless**: AWS Lambda, Cloudflare Workers, Vercel Functions, Supabase Functions
- **Monorepos**: Turborepo, Nx Workspace, pnpm Workspace

## Working with scaffold.py

### Core Components

**ProjectConfig dataclass** (lines 64-101): Configuration object passed to all project creators
- SDK/runtime versions (Node, Python, Go, Rust, Java)
- Framework options (CSS, database, ORM)
- Tooling flags (ESLint, Prettier, testing, Docker, CI)

**ProjectScaffolder class** (lines 103-2834): Main scaffolding engine
- `create_project()` - Entry point, delegates to project-type-specific methods
- `_create_react()`, `_create_nextjs()`, `_create_fastapi()`, etc. - Project generators
- Helper methods for common files, configs, Docker, CI/CD

### Project Generator Pattern

Each `_create_[framework]()` method follows this pattern:
1. **Create directory structure** - Use `_create_dirs()` for nested folders
2. **Define dependencies** - Build `deps` and `dev_deps` dictionaries
3. **Generate package.json/pyproject.toml** - Use `_create_package_json()` or write directly
4. **Create config files** - TypeScript, ESLint, Prettier, Tailwind, etc.
5. **Write source files** - Entry points, app files, example components
6. **Add common files** - Use `_create_common_files()` for .gitignore, README, .env.example

### Important Methods

- **`_create_tsconfig(config, framework)`** (lines 1217-1301): TypeScript config generator
  - Framework-specific configs for: react, nextjs, vue, node, library, nestjs, angular
  - Handles strict mode, path aliases, module resolution

- **`_create_common_files(path, config, python=False)`** (lines 1303-1509):
  - Generates .gitignore (different for Python vs JS)
  - Creates .env.example with sensible defaults
  - Writes README.md with setup instructions
  - Configures VS Code settings for linting/formatting
  - Sets up GitHub Actions workflows
  - Adds Docker configuration

- **Template content methods** (lines 1706-2833): Generate file contents
  - Vite configs, React components, Next.js layouts
  - FastAPI/Django project structures
  - Express/NestJS boilerplate
  - Python/Node.js CLI templates

### Key Design Decisions

1. **Native CLI tools preferred**: The code recommends using official CLIs (create-next-app, create-vite) when available, scaffold.py provides fallback/augmentation

2. **Multi-stage Docker builds**: All Docker configs use multi-stage builds for optimization

3. **Type safety everywhere**: TypeScript strict mode by default, Python type hints encouraged

4. **Modern tooling defaults**: Vite over CRA, Ruff over Flake8+Black, pnpm over npm

## Modifying the Skill

### Adding a New Project Type

1. **Update SKILL.md**: Add to the project type list (lines 18-152) with clear description
2. **Add to wizard options**: Include in the formatted table in SKILL.md
3. **Implement creator method** in scaffold.py:
   ```python
   def _create_[framework](self, path: Path, config: ProjectConfig):
       # 1. Create directories
       self._create_dirs(path, ["src", "tests", ...])

       # 2. Define dependencies
       deps = {"framework": "^1.0.0"}
       dev_deps = {"typescript": "^5.0.0"}

       # 3. Create package.json/pyproject.toml
       package_json = self._create_package_json(config, deps, dev_deps, scripts)

       # 4. Write config files
       # 5. Create source files
       # 6. Add common files
       self._create_common_files(path, config)
   ```
4. **Map in create_project()**: Add to the `creators` dict (line 118)
5. **Add template methods**: Create `_[framework]_[file]()` methods for file contents

### Adding Framework Options

To add a new CSS framework, ORM, or other option:
1. Add to the relevant Enum (lines 18-61): `CSSFramework`, `Database`, `ORM`, etc.
2. Update ProjectConfig dataclass if needed (lines 64-101)
3. Add conditional logic in project creators to handle the new option
4. Update SKILL.md to document the new option in the wizard workflow

### Updating Dependencies

When updating default versions:
- Search for version strings in scaffold.py (e.g., `"^18.2.0"`)
- Update consistently across all occurrences
- Consider updating references/frameworks.md for documentation

## Testing Approach

The scaffold.py script is designed to be run standalone:
```bash
# Test the scaffolding engine directly
python scripts/scaffold.py react my-test-app --typescript --tailwind

# Or use through Claude Code
# Just ask: "Create a React app with TypeScript and Tailwind"
```

To verify changes:
1. Run scaffold.py with various project types
2. Check generated directory structure
3. Verify all config files are valid (no syntax errors)
4. Test that `npm install` / `pip install` succeeds
5. Confirm dev server starts: `npm run dev` / `uvicorn app.main:app`

## Common Tasks

### Update Default Node.js Version
Search for `node_version: str = "24"` in ProjectConfig (line 76) and update. Also update in templates:
- Dockerfile templates (search for `FROM node:`)
- GitHub Actions workflows (search for `node-version:`)

### Update Default Python Version
Search for `python_version: str = "3.14"` in ProjectConfig (line 77). Update in:
- Dockerfile templates
- GitHub Actions workflows
- pyproject.toml templates

### Add New Testing Framework
1. Add to project creator conditionals (e.g., in `_create_react()`)
2. Add dependencies to `dev_deps` dict
3. Create test config file (e.g., `_vitest_config()`, `_jest_config()`)
4. Update package.json scripts

### Customize Project Templates
Template methods return strings with file contents. To customize:
1. Find the relevant method (e.g., `_react_app()` for React App.tsx)
2. Modify the returned string
3. Use f-strings to inject config values: `f"{config.name}"`

## Important Notes

- **SKILL.md is the source of truth** for what the skill can do - always update it when adding features
- **Keep scaffold.py and SKILL.md in sync** - options in SKILL.md must be implemented in scaffold.py
- **Use type hints** - The codebase uses Python dataclasses and type hints throughout
- **Follow the pattern** - New project creators should match the structure of existing ones
- **Test locally first** - scaffold.py can be run directly without Claude Code for faster iteration
- **Version consistency** - When updating a framework version, update in all occurrences (deps, docs, configs)

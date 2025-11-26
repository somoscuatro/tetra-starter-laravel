# TetraStarter for Laravel

TetraStarter for Laravel is a batteries-included Laravel 12 starter kit designed for high-quality, scalable,
maintainable apps. It includes curated tools for development, debugging, refactoring, testing, and frontend
productivity — all preconfigured so you can start building immediately.

> [!IMPORTANT]
> This is an opinionated Laravel starter kit created by [somoscuatro team](https://somoscuatro.es).
> While PRs are welcome, this is designed to fit the needs of one specific team.

## Included Packages

This starter kit includes a curated selection of packages to enhance development productivity and code quality.

**Core Framework & Environment**

- [Laravel 12](https://laravel.com/)
- [Laravel Sail](https://laravel.com/docs/sail) — Docker-based local development
- [Sail SSL](https://github.com/ryoluo/sail-ssl) — Local HTTPS for Sail

> [!TIP]
> Please notice that since we are using [Sail SSL](https://github.com/ryoluo/sail-ssl) for local development, it might
> be necessary to trust the self-signed certificate in your OS/browser.

**Debugging & Productivity**

- [Laravel Telescope](https://laravel.com/docs/telescope) — Debugging and insight for local environments
- [Laravel Horizon](https://laravel.com/docs/horizon) — Queue management with Redis
- [Laravel Debugbar](https://github.com/barryvdh/laravel-debugbar) — Debugging toolbar
- [Laravel IDE Helper](https://github.com/barryvdh/laravel-ide-helper) — Improved IDE support
- [Laravel Boost](https://laravel.com/ai/boost) — AI-assisted development

**Code Quality & Refactoring**

- [Rector](https://getrector.com/) — Automated code refactoring
- [Laravel Pint](https://laravel.com/docs/pint) — PHP code style enforcement
- [Prettier](https://prettier.io/) — JS/CSS code style enforcement
- [Larastan](https://github.com/larastan/larastan) — Static analysis for Laravel
- [Peck](https://github.com/peckphp/peck) — Typos checking

**Testing**

- [Pest](https://pestphp.com/) — Elegant PHP testing framework
- Pest
  Plugins — [Browser Testing](https://pestphp.com/docs/browser-testing), [Type Coverage](https://pestphp.com/docs/type-coverage), [Stress Testing](https://pestphp.com/docs/stress-testing), [Profanity](https://pestphp.com/docs/profanity)
- [Laravel Nightwatch](https://nightwatch.laravel.com/) — First-class monitoring for Laravel applications

**Frontend**

- [Tailwind CSS](https://tailwindcss.com/) — Utility-first CSS framework
- [Vite](https://vitejs.dev/) — Fast frontend build tool

## Installation

> [!TIP]
> This starter kit uses Laravel Sail, So Docker is required. We recommend [Orbstack](https://orbstack.com/) on macOS for
> the best Docker experience.

> [!TIP]
> For convenience, we suggest you to set up this alias in your shell: `alias sail='bash vendor/bin/sail'`.

### Option 1: Laravel Installer (Recommended)

Use the Laravel installer to create a new project:

```sh
laravel new --using=somoscuatro/tetra-starter-laravel
```

### Option 2: Manual Setup

1. Clone the repository:

    `git clone https://github.com/somoscuatro/tetra-starter-laravel.git && cd tetra-starter-laravel`

2. Install Composer dependencies:

    ```shell
        docker run --rm \
        -u "$(id -u):$(id -g)" \
        -v "$(pwd):/var/www/html" \
        -w /var/www/html \
        laravelsail/php84-composer:latest \
        composer install --ignore-platform-reqs
    ```

3. Create .env file:

    `cp .env.example .env`

4. Setup the project:

    `sail composer run setup`

5. Build assets

    `sail bun run build`

6. Run migrations and seed the database

    `sail artisan migrate:fresh --seed`

## Composer Commands

- `composer run setup` — Install dependencies, setup environment, migrate, build assets, generate IDE helpers
- `composer run lint` — Run Pint and JS lint
- `composer run format` — Format PHP and JS code
- `composer run refactor` — Run Rector for code upgrades
- `composer run test` — Run all tests (unit, type coverage, profanity)
- `composer run dev` — Start development servers (PHP, queue, logs, Vite)

Have a look at [`composer.json`](https://github.com/somoscuatro/tetra-starter-laravel/blob/main/composer.json) for the
full list of commands.

## License

This starter kit is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

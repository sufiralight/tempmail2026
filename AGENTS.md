# Temp Mail SaaS

## Phase 0 baseline

This checkout contains the Laravel starter. Product capabilities described in the area guides are planned unless verified in the checkout. Start with [Architecture](docs/architecture.md), [Coding standards](docs/coding-standards.md), and the [Implementation plan](docs/implementation-plan.md).

Use [Design system](docs/design-system.md), [Color system](docs/color-system.md), [Components](docs/components.md), [Accessibility](docs/accessibility.md), and [Installation flow](docs/installation-flow.md) as the Phase 0 standards. Obtain approval before implementing application changes.


Installer finalization owns the schema, founder transaction and durable lock. See [Installation](docs/installation-flow.md).

Keep Admin Console links and route access aligned with the Laravel admin.access Gate. See the [authentication](agents/authentication.md) and [security](agents/security.md) rules.

Use the shared appearance dropdown and keep the default installer form within the desktop viewport. Allow natural scrolling at narrow widths and zoom.

All applicable password fields must use x-ui.password-field. Layouts offering appearance selection must reuse x-appearance and the shared theme initialization.

Use the planned shared Blade auth layout and appearance selector for authentication forms. See the [authentication rules](agents/authentication.md).

Build a maintainable temporary email SaaS as a Laravel 13 modular monolith. PHP 8.5 is the development and CI target. Use the configured MySQL, MariaDB, PostgreSQL, SQLite or SQL Server connection, Blade, reusable Blade components, Alpine, Tailwind CSS 4, and Vite. Check the manifests, lockfiles, and installed versions before changing dependencies. Preserve working behavior and Laravel conventions.

## Workflow

1. Inspect the relevant existing code, this file, and any matching .ai/rules instructions when present. Read the relevant guides below and the linked technical documentation.
2. Identify affected modules, data, and dependencies. Implement the smallest complete change. Reuse existing components, keep controllers thin, and keep business logic outside views.
3. Add or update module-owned migrations when needed and add or update tests for changed behavior. Run applicable checks and record actual results and gaps.
4. Update existing documentation where contracts or operational procedures change. Mark features Implemented, Planned, Under development, or Deprecated according to repository evidence. Use relative links and avoid per-task reports.

## Rules by area

| Area | Read before changing it |
| --- | --- |
| Module boundaries and server code | [Architecture](agents/architecture.md), [Backend](agents/backend.md) |
| Templates and interaction | [Frontend](agents/frontend.md), [Blade components](agents/blade-components.md) |
| Visual design and accessibility | [Design system](agents/design-system.md), [Accessibility](agents/accessibility.md) |
| Installation and data | [Installer](agents/installer.md), [Database](agents/database.md) |
| Accounts and privileged operations | [Authentication](agents/authentication.md), [Security](agents/security.md) |
| Uploads and branding | [Media Library](agents/media-library.md) |
| Verification and operations | [Testing](agents/testing.md), [Shared hosting](agents/shared-hosting.md) |

Use the [Linear-led product design system](docs/design-system.md#product-wide-visual-direction), the shared Blade catalog documented in [Components](docs/components.md), and WCAG 2.2 AA as the accessibility target. Require server-side authorization for privileged and ownership-sensitive operations. Protect secrets and preserve CSRF. Keep schema changes explicit and initial boot independent of a configured database. Support Apache and cPanel with public/ as document root and Vite assets built locally or in CI. Production must run without Node.js, npm, or persistent queue workers.

## Product experience and definition of done

Use the [design system](docs/design-system.md) as the product UX reference. Extend the shared Blade shell, semantic tokens and existing component APIs. Each screen should put its main task first. Forms need visible labels, inline errors, pending and completion feedback, and safe submission behavior. Keep current-page selection explicit and use confirmations for irreversible operations.

A change is done when the normal entry point, authorization boundary, validation and failure path are verified, applicable tests and build checks have run, and the affected contracts and release steps are documented. Check changed interfaces by keyboard and at representative mobile and desktop widths in both themes using isolated data. Record untested cases explicitly. Keep production data and files out of test fixtures.

Future phase and step prompts must reference this file and the applicable guides. For multilingual work, define locale, direction, slug uniqueness and inactive-language visibility before exposing content. Add locale-keyed translations when required by an implemented module.

### Functional UX Before Decorative UX

Define a measurable [primary-task contract](docs/design-system.md#primary-task-contract) for every new or revised user-facing screen. Track implementation and release blockers in the [implementation plan](docs/implementation-plan.md). A rendered page alone does not establish readiness.

## Git and releases

Keep changes focused and commits descriptive. Preserve Git history and unrelated files. Obtain explicit authorization before rewriting history or force-pushing. Explain deployment configuration changes in the change summary. Keep .env, secrets, sensitive database dumps, runtime caches, and generated release assets out of Git. Use .env.example for non-sensitive settings and package public/build with releases.

Start with the [implementation plan](docs/implementation-plan.md) and [architecture and hosting baseline](docs/architecture.md#development-and-hosting).

Before implementing localization, define the language registry, public locale rules, integration contracts, and release gates.

Document font catalog policy, locale typography, and deployment checks when adding font management.

Document key registration, status workflow, escaping and deployment checks when adding UI translations.

Keep the Roles & permissions matrix aligned with the authorization contracts. Verify role counts, direct URL access, and user assignment protections after changes.

Preserve the installer-recorded Founder Super Admin and the independent last active Super Admin invariant in every account lifecycle change. See the [authentication](agents/authentication.md) and [security](agents/security.md) rules.

Use the [navigation contexts](docs/components.md#navigation-contexts) and [hosting checks](docs/architecture.md#development-and-hosting) when changing console access or schema-backed features.

Apply the Branding primary-task contract when changing brand assets or their public delivery.

Keep homepage publishing separate from public locale resolution. Preserve canonical English, authorization and explicit visitor preferences.

Use the typography contract for script defaults, language overrides and technical LTR text.

Keep /admin/fonts as the authoritative Typography Studio.

Keep language availability and homepage publishing in Localization Studio. Link to Typography Studio for locale font settings.

===

<laravel-boost-guidelines>
=== foundation rules ===

# Laravel Boost Guidelines

## Foundational Context

This application is a Laravel application running on PHP 8.5. Always use the APIs that match the installed major version of each package — do not assume a version.

Before relying on a package's API, confirm its installed version:
- PHP packages: run `composer show --direct` to list direct dependencies with versions, or `composer show <vendor/package>` for a single package.
- JS packages: check `package.json` for the installed versions.

## Skills Activation

This project has domain-specific skills available in `**/skills/**`. You MUST activate the relevant skill whenever you work in that domain—don't wait until you're stuck.

## Conventions

- You must follow all existing code conventions used in this application. When creating or editing a file, check sibling files for the correct structure, approach, and naming.
- Use descriptive names for variables and methods. For example, `isRegisteredForDiscounts`, not `discount()`.
- Check for existing components to reuse before writing a new one.

## Verification Scripts

- Do not create verification scripts or tinker when tests cover that functionality and prove they work. Unit and feature tests are more important.

## Application Structure & Architecture

- Stick to existing directory structure; don't create new base folders without approval.
- Do not change the application's dependencies without approval.

## Frontend Bundling

- If a frontend change doesn't show in the UI or you get a "Unable to locate file in Vite manifest" error, run `npm run build` or ask the user to run `npm run dev` or `composer run dev`.

## Documentation Files

- You must only create documentation files if explicitly requested by the user.

=== boost rules ===

# Laravel Boost

## Tools

- Laravel Boost is an MCP server with tools designed specifically for this application. Prefer Boost tools over manual alternatives like shell commands or file reads.
- Use `database-query` to run read-only queries against the database instead of writing raw SQL in tinker.
- Use `database-schema` to inspect table structure before writing migrations or models.
- Use `get-absolute-url` to resolve the correct scheme, domain, and port for project URLs. Always use this before sharing a URL with the user.
- Use `browser-logs` to read browser logs, errors, and exceptions. Only recent logs are useful, ignore old entries.

## Searching Documentation (IMPORTANT)

- Use `search-docs` before changes that depend on Laravel ecosystem APIs, behavior, configuration, or version-specific syntax. Skip it for copy-only edits and other changes where package documentation is irrelevant. Reuse sufficient results already in context instead of searching again.
- Pass a `packages` array to scope results when you know which packages are relevant.
- Use multiple broad, topic-based queries: `['rate limiting', 'routing rate limiting', 'routing']`. Expect the most relevant results first.
- Do not add package names to queries because package info is already shared. Use `test resource table`, not `filament 4 test resource table`.

### Search Syntax

1. Use words for auto-stemmed AND logic: `rate limit` matches both "rate" AND "limit".
2. Use `"quoted phrases"` for exact position matching: `"infinite scroll"` requires adjacent words in order.
3. Combine words and phrases for mixed queries: `middleware "rate limit"`.
4. Use multiple queries for OR logic: `queries=["authentication", "middleware"]`.

## Project Rules

- This project contains committed, area-grouped rules in `.ai/rules` when that directory exists, including path-scoped framework guidelines under `.ai/rules/boost`. Before you enter plan mode or create/edit any file, you MUST first: open @.ai/rules/index.md (it maps file globs to rule files), read every rule file whose globs cover the path(s) in scope, and run `grep -rin 'keyword' .ai/rules` to catch what a path match alone misses. Do not write code until you have read and are following every matching rule. If `.ai/rules` does not exist, continue without it.

## Artisan

- Run Artisan commands directly via the command line (e.g., `php artisan route:list`). Use `php artisan list` to discover available commands and `php artisan [command] --help` to check parameters.
- Inspect routes with `php artisan route:list`. Filter with: `--method=GET`, `--name=users`, `--path=api`, `--except-vendor`, `--only-vendor`.
- Read configuration values using dot notation: `php artisan config:show app.name`, `php artisan config:show database.default`. Or read config files directly from the `config/` directory.

## Tinker

- Execute PHP in app context for debugging and testing code. Do not create models without user approval, prefer tests with factories instead. Prefer existing Artisan commands over custom tinker code.
- Always use single quotes to prevent shell expansion: `php artisan tinker --execute 'Your::code();'`
  - Double quotes for PHP strings inside: `php artisan tinker --execute 'User::where("active", true)->count();'`

=== php rules ===

# PHP

- Always use curly braces for control structures, even for single-line bodies.
- Use PHP 8 constructor property promotion: `public function __construct(public GitHub $github) { }`. Do not leave empty zero-parameter `__construct()` methods unless the constructor is private.
- Use explicit return type declarations and type hints for all method parameters: `function isAccessible(User $user, ?string $path = null): bool`
- Use TitleCase for Enum keys: `FavoritePerson`, `BestLake`, `Monthly`.
- Prefer PHPDoc blocks over inline comments. Only add inline comments for exceptionally complex logic.
- Use array shape type definitions in PHPDoc blocks.

=== deployments rules ===

# Deployment

- Laravel can be deployed using [Laravel Cloud](https://cloud.laravel.com/), which is the fastest way to deploy and scale production Laravel applications.
- Activate the `deploying-to-cloud` skill whenever deploying to Laravel Cloud, configuring Cloud environments or resources, using the Cloud CLI, or troubleshooting Cloud deployments.

=== laravel/core rules ===

# Do Things the Laravel Way

- Use `php artisan make:` commands to create new files (i.e. migrations, controllers, models, etc.). You can list available Artisan commands using `php artisan list` and check their parameters with `php artisan [command] --help`.
- If you're creating a generic PHP class, use `php artisan make:class`.
- Pass `--no-interaction` to all Artisan commands to ensure they work without user input. You should also pass the correct `--options` to ensure correct behavior.

### Model Creation

- When creating new models, create useful factories and seeders for them too. Ask the user if they need any other things, using `php artisan make:model --help` to check the available options.

## APIs & Eloquent Resources

- For APIs, default to using Eloquent API Resources and API versioning unless existing API routes do not, then you should follow existing application convention.

## URL Generation

- When generating links to other pages, prefer named routes and the `route()` function.

## Testing

- When creating models for tests, use the factories for the models. Check if the factory has custom states that can be used before manually setting up the model.
- Faker: Use methods such as `$this->faker->word()` or `fake()->randomDigit()`. Follow existing conventions whether to use `$this->faker` or `fake()`.
- When creating tests, make use of `php artisan make:test [options] {name}` to create a feature test, and pass `--unit` to create a unit test. Most tests should be feature tests.

=== pint/core rules ===

# Laravel Pint Code Formatter

- If you have modified any PHP files, you must run `vendor/bin/pint --dirty --format agent` before finalizing changes to ensure your code matches the project's expected style.
- Do not run `vendor/bin/pint --test --format agent`, simply run `vendor/bin/pint --format agent` to fix any formatting issues.

=== phpunit/core rules ===

# PHPUnit

- This project uses PHPUnit. Create tests with `php artisan make:test --phpunit {name}`.
- Do not include the test suite directory in `{name}`. Use `SomeFeatureTest`, not `Feature/SomeFeatureTest`.
- Read the `testing-best-practices` skill for guidance on coverage, naming, structure, dependency isolation, and review.

## Running Tests

- Run the narrowest set of tests that covers the change. Pass a file path or `--filter=testName` to `php artisan test --compact`.
- Rerun a test after each change to it.
- Run `vendor/bin/phpunit` to call the test runner directly. It accepts the same file path and `--filter=testName` arguments.

</laravel-boost-guidelines>

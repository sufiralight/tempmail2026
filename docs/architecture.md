# Architecture

## Checkout baseline

The application is a Laravel starter. PHP CLI is 8.5.12, Composer declares PHP ^8.3 and Laravel ^13.17, and the locked and installed framework is 13.42.0. PHP 8.5 is the development and CI target. PHPUnit 12.5.44 is installed. Verify the production PHP version and extensions against the release artifact on the target host.

The web route renders the starter welcome view. Bootstrap registers /up, the console route file and JSON exception rendering. The route table also includes framework local-storage routes. The app has a User model and starter migrations for users, sessions, cache and jobs. Laravel config declares SQLite, MySQL, MariaDB, PostgreSQL and SQL Server connections. The sample environment defaults to SQLite with database-backed session, cache and queue. Configured drivers and installer support have separate verification requirements.

Vite takes resources/css/app.css and resources/js/app.js as inputs using the Laravel and Tailwind plugins. The CSS uses Tailwind 4 CSS-first configuration with pagination and compiled-view sources. The JS entry is empty apart from a comment. The manifest declares Vite ^8.0.0, Tailwind ^4.0.0 and Laravel Vite plugin ^3.1. This checkout has no npm lockfile, installed JS dependencies or production build manifest. The existing Vite font provider is Bunny Fonts for Instrument Sans. Google Fonts is the product target, with provider migration pending.

## Modular monolith

Keep one Laravel application, one deployment and Laravel's existing directory conventions. Use routes and middleware for entry points, controllers for coordination, Form Requests for validation, Gates and policies for authorization, focused services for domain operations, Eloquent for persistence and Blade for presentation. Group code by product capability within those conventions as the code grows.

| Planned capability | Owns |
| --- | --- |
| Installation | Operator access, verified configuration, initial schema, founder and durable completion |
| Identity and administration | Account lifecycle, policy enforcement, roles, console and audit trail |
| Mailboxes | Address issuance, domain configuration, ownership and expiration |
| Messages | Authenticated ingress, deduplication, safe rendering, attachment authorization and retention |

Modules own their data invariants and migrations. Cross-module writes use the owning operation. Dispatch side effects after commit where appropriate. Keep inbound transport behind an explicit boundary so a provider choice need not leak into mailbox views. Render navigation and forms on the server, with scoped Alpine or vanilla JavaScript for progressive enhancement. Keep authorization and business state server-side.

## Development and hosting

Use isolated databases for localhost development, tests and fresh installer runs. The starter composer setup script migrates automatically, so use a dedicated empty database and a separate bootstrap sequence when testing the installer. Keep pre-install session, cache and locking independent of the target database.

For Apache or cPanel, point the document root at public/, keep rewrite rules, secrets and private files in their intended locations, and grant only the required writable paths. Prepare production Composer dependencies and compile Vite assets on a compatible build machine or in CI. Include public/build and its matching manifest, verify the release without a Vite hot file, and run with HTTPS and production debug disabled. Use bounded, non-overlapping cron for scheduled work when supported by the host. Production requires no Node.js, npm or persistent queue worker. Back up database and private state before upgrades, run schema changes through controlled release procedures, and verify health plus normal application entry points after deployment. [Laravel deployment](https://laravel.com/docs/13.x/deployment)

See [architecture rules](../agents/architecture.md), [shared hosting rules](../agents/shared-hosting.md) and the [implementation plan](implementation-plan.md).

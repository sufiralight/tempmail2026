# Testing

Run the opt-in installer finalization test against an empty disposable MariaDB instance on a separate loopback port.

Exercise direct console access, role rejection, filtered pagination, and safe schema warnings in AdminConsoleTest.

Measure installer document size at 1440 × 900 and check natural reflow at 390 px and 320 px. Exercise theme selection and Escape with keyboard input.

Cover password masking, reveal and conceal, keyboard activation, preserved input and shared appearance behavior with installer and authentication checks.

Authentication tests run on isolated SQLite and cover rendering, privilege-field rejection, login, logout and reset expiry and reuse.

Add focused tests for changed behavior and regressions. Use PHPUnit unit tests for isolated rules and Laravel feature tests for routes, validation, authorization, and persistence. Use isolated test data and factories. Prove negative paths at the actual action boundary.

Use the [coverage matrix and commands](../docs/testing.md) for installer retries, authentication, ownership, migrations, Blade components, upload validation, accessibility, and Vite release builds as each capability lands. Execute the relevant commands and report actual results, skipped checks, and environment limits.

Use the [browser QA matrix](../docs/testing.md#browser-qa-matrix) for changed interactions. Prefer actual pointer and keyboard input when investigating a click failure. Confirm the request, persisted result and feedback independently.

See [Localization](../docs/localization.md) for the language registry, public locale rules, integration contracts, and release gates.

For font catalog policy, locale typography, and deployment checks, see [Fonts Management](../docs/localization.md#fonts-management).

See [UI Translations](../docs/localization.md#ui-translations) for key registration, status workflow, escaping and deployment checks.

Keep the Roles & permissions matrix aligned with the [authorization contracts](../docs/authorization.md). Verify role counts, direct URL access, and user assignment protections after changes.

Require evidence for the [primary-task contract](../docs/design-system.md#primary-task-contract). Record skipped, blocked and untested cases separately. Sequential tests do not establish concurrency behavior.

Exercise locale precedence, zero-weight ranges, per-field fallback and stale publishing revisions in isolated tests.

Verify script inheritance, language overrides, reset and incompatible assignments. Browser checks must verify loaded font assets and mixed-direction controls.

Exercise the Studio deep links and verify loaded font faces with representative text in a real browser.

# Security

Preserve the private installed and initializing files. Restore configuration under operator control and keep partially initialized schemas locked against automatic retries.

Apply the admin.access Gate at the route boundary. Keep lifecycle writes unavailable until founder identity and last-active-Super-Admin protections are implemented.

Never populate a password input from flashed data. Keep connection testing read-only and restrict it to the private gate authorized endpoint.

Reset email is disabled for non-delivery transports. Keep responses generic across account existence and keep reset tokens out of flashed input.

Authorize administrative and ownership-sensitive actions on the server. Use deny-by-default policies, scoped queries, validated input, and CSRF on browser writes. Escape output with Blade, treat inbound HTML as untrusted, and require a vetted sanitization path before rendering rich content. Rate-limit sensitive actions and retain production-safe errors.

Keep keys and credentials in private configuration. Redact passwords, tokens, cookies, credential-bearing URLs, and sensitive SQL bindings from diagnostics. Log sensitive state changes with actor, action, target, result, and request identifier while limiting access and retention. Use least privilege for database, filesystem, and service credentials.

Keep installer errors redacted and credential fields out of logs and flashed input. Preserve the database operation ID and filesystem checkpoint during recovery. Use the configured application origin for reset links and keep reset tokens out of logs. Preserve secure cookie settings and apply the [installer](installer.md) and [upload](media-library.md) rules at their respective entry points. Check the [security model](../docs/security.md) before adding trust boundaries.

Keep recoverable Trash separate from permanent cleanup. Serialize media lifecycle changes with reference updates and recheck ownership and active references before removing private files.

See [Localization](../docs/localization.md) for the language registry, public locale rules, integration contracts, and release gates.

For font catalog policy, locale typography, and deployment checks, see [Fonts Management](../docs/localization.md#fonts-management).

See [UI Translations](../docs/localization.md#ui-translations) for key registration, status workflow, escaping and deployment checks.

Keep the Roles & permissions matrix aligned with the [authorization contracts](../docs/authorization.md). Verify role counts, direct URL access, and user assignment protections after changes.

Serialize role and account lifecycle changes and enforce [founder and last-admin protection](../docs/authorization.md#founder-super-admin) at the mutation boundary.

Keep homepage draft preview behind verified settings.manage authorization with private no-store responses.

Font mutations require verified settings.manage access and catalog compatibility checks. Build remote font URLs from the fixed provider and allowed families.

Keep Typography Studio mutations behind the existing font administration boundary. Accept only catalog identifiers and validated settings.

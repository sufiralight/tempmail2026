# Installer

Follow the current flow and planned milestones in [Installation](../docs/installation.md). Keep Database Configuration first. List MariaDB first and select it by default. Preserve the submitted engine after an error. Treat Database Engine and Database Host as separate inputs. MySQL and MariaDB use PDO MySQL with editable host, port, database name, username and password. Keep PostgreSQL and SQLite disabled until their full installer paths are verified.

Require the private operator gate on every installer request. Preserve direct peer, raw Host, HTTPS, forwarded-header rejection and pinned endpoint checks. Allow localhost and 127.0.0.1 for direct loopback development. Keep connection tests bounded and read-only. Reject nonempty databases and engine mismatches, clear earlier verification before a retest, and never flash or log passwords.

Use x-appearance in the installer layout and x-ui.password-field for all password entry. For future finalization, preserve existing database data and application keys, verify the schema under an exclusive lock, and record the founder and completion durably. Keep configuration recovery under operator control.

Identify server products using server metadata and the MariaDB Aria engine capability. PDO MySQL is shared transport. Preserve the selected engine and fail safely when product identity is unclear.

Keep runtime checks inline with Test Connection. Show failed checks on Database Configuration and advance directly to First Super Admin when they pass.

Reuse x-temp-mail-mark for installer branding in the header and connection diagram. Group connection fields separately from credentials and place verification feedback by the primary action.

Keep the installer progress rail focused on current and completed steps. Use the shared setup surface and control tokens and keep connection feedback by the submit action.

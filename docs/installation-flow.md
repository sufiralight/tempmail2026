# Installation flow

Status **Planned**. Use the shared installer layout, appearance preference and password field. The installer begins with database-independent runtime services. Apply the private operator gate on every step, including verification and finalization. Validate the direct peer, raw Host, direct TLS, forwarded-header rejection and pinned database endpoint requirements from the [installer rules](../agents/installer.md) and keep the gate closed when the host cannot meet them. Use CSRF for browser writes and keep credentials out of URLs, logs, flash data and rendered values.

## 1. Database Configuration

Present Database Engine separately from host, port, database name, username and password. Default to MariaDB, then offer MySQL after verification. Enable further drivers only after the full flow is verified. Check runtime capabilities and connection in a bounded, read-only operation. Confirm the engine identity and target schema suitability. Require an empty target for fresh setup. On failure, retain the draft and show a redacted, actionable error. Clear stale verification before testing again and require new verification when settings change. Successful verification unlocks Administrator Account. Direct navigation cannot bypass this check.

## 2. Administrator Account

Use visible account fields and shared masked controls for the password and confirmation. Create the first account as the installer-recorded Founder Super Admin and mark its initial email verified through the authorized setup flow. Back restores the draft and verification while it is valid. Keep passwords out of ordinary flash data and HTML. Within a live step transition, preserve a typed secret only if the design can keep it safely in memory. Across server round trips, retain database credentials in short-lived private server-side state when needed, show that the verified credential is retained, and require re-entry when it is edited or expires. Decide equivalent safe handling for an unsubmitted administrator password before implementing cross-step draft restoration.

Acquire an exclusive initialization lock and recheck the verified draft, target connection and schema under that lock before any writes. Own schema preparation, founder transaction and durable completion in finalization. Preserve application keys and existing data. Track progress durably across filesystem and database boundaries because DDL and configuration changes may not share one transaction. Guard against partial schemas, double submit and concurrent installs. For interruption, keep a private checkpoint and require operator-controlled recovery before retrying.

## 3. Installation Complete

Display success only after the founder transaction and durable installation state are confirmed. Clear transient credentials and close setup permanently. Allow the completing session to reach a safe completion receipt, then link to sign-in. Back, refresh and direct setup requests cannot reopen finalization.

Verify connection rejection, stale verification, Back navigation, expired drafts, redacted errors, duplicate submission, concurrent finalization and interrupted recovery on disposable data. Run an end-to-end check on each enabled database engine and on the supported shared-host setup.

## Durable state and configuration recovery

- Fresh setup requires explicit operator authorization and an eligible empty target. A missing .env is a configuration condition and does not establish fresh install eligibility.
- Verification is private, session-bound and expires. Finalization creates a durable private initializing marker before side effects. Record the operation identifier and target so interrupted database and filesystem steps can be reconciled.
- The durable installed marker blocks installer writes independently of application configuration, cookies and database connectivity. An initializing marker, unreadable state or inconsistent evidence fails closed. Restore or reconcile state through an operator-controlled recovery procedure.
- When an installed deployment loses .env, keep setup locked and return a generic maintenance response where the application can serve one. The operator restores private configuration from backup or the hosting environment, including the original APP_KEY, database settings and installation markers. Verify the target and founder record, rebuild configuration cache from the restored settings, then restore service. Never treat loss of configuration or a key as permission to initialize a new schema or founder.
- Before enabling the installer, test missing .env with both installed and initializing markers, missing or unreadable state, stale config cache and interrupted finalization. Verify that none can create a second founder or reopen setup.
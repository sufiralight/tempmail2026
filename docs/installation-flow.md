# Installation flow

Status **Planned**. Use the shared installer layout, appearance preference and password field. The installer begins with database-independent runtime services. Apply the private operator gate on every step, including verification and finalization. Validate the direct peer, raw Host and TLS requirements from the [installer rules](../agents/installer.md) and keep the gate closed when the host cannot meet them. Use CSRF for browser writes and keep credentials out of URLs, logs, flash data and rendered values.

## 1. Database Configuration

Present Database Engine separately from host, port, database name, username and password. Default to MariaDB, then offer MySQL after verification. Enable further drivers only after the full flow is verified. Check runtime capabilities and connection in a bounded, read-only operation. Confirm the engine identity and target schema suitability. Require an empty target for fresh setup. On failure, retain the draft and show a redacted, actionable error. Clear stale verification before testing again and require new verification when settings change. Successful verification unlocks Administrator Account. Direct navigation cannot bypass this check.

## 2. Administrator Account

Use visible account fields and shared masked controls for the password and confirmation. Create the first account as the installer-recorded Founder Super Admin and mark its initial email verified through the authorized setup flow. Back restores the draft and verification while it is valid. Keep passwords out of ordinary flash data and HTML. Within a live step transition, preserve a typed secret only if the design can keep it safely in memory. Across server round trips, retain database credentials in short-lived private server-side state when needed, show that the verified credential is retained, and require re-entry when it is edited or expires. Decide equivalent safe handling for an unsubmitted administrator password before implementing cross-step draft restoration.

Recheck the verified connection and acquire an exclusive initialization lock. Own schema preparation, founder transaction and durable completion in finalization. Preserve application keys and existing data. Track progress durably across filesystem and database boundaries because DDL and configuration changes may not share one transaction. Guard against partial schemas, double submit and concurrent installs. For interruption, keep a private checkpoint and require operator-controlled recovery before retrying.

## 3. Installation Complete

Display success only after the founder transaction and durable installation state are confirmed. Clear transient credentials and close setup permanently. Allow the completing session to reach a safe completion receipt, then link to sign-in. Back, refresh and direct setup requests cannot reopen finalization.

Verify connection rejection, stale verification, Back navigation, expired drafts, redacted errors, duplicate submission, concurrent finalization and interrupted recovery on disposable data. Run an end-to-end check on each enabled database engine and on the supported shared-host setup.

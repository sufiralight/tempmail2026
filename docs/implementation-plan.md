# Implementation plan

| Phase | Status | Scope and exit criteria |
| --- | --- | --- |
| 0. Standards | Under development | Review the baseline and approve these contracts. Recover the authoritative palette and settle the decisions needed for Phase 1. |
| 1. Shared UI foundation | Planned | Establish reproducible Vite builds, token mappings, shared appearance, shell, core controls, icons and progress. Verify contrast and keyboard behavior across themes and widths. |
| 2. Installer | Planned | Deliver the three-step flow, private access, verified drafts, guarded finalization and recovery. Pass disposable engine and shared-host tests. |
| 3. Identity and console | Planned | Deliver sign-in, recovery, account lifecycle and administration. Verify direct URL authorization, founder protection and the independent last-active-Super-Admin invariant. |
| 4. Mailboxes and messages | Planned | Deliver address issuance, authenticated ingress, inbox and expiry. Verify isolation, replay handling, safe content delivery, abuse limits and bounded retention work. |
| 5. Release readiness | Planned | Rehearse deployment, upgrades, backups and recovery on shared hosting. Verify the production build, accessibility and critical flows with isolated data. |

## Open decisions and release blockers

- Recover the authoritative 16 palette names and values, then approve both theme mappings against the contrast matrix.
- Confirm the Google Fonts families, script coverage and delivery strategy. The starter currently uses Bunny Fonts. Confirm a shared icon source before implementing components.
- Establish a reproducible npm lockfile and supported build runtime during Phase 1. Confirm the production PHP and extension matrix for nominated hosts.
- Confirm the launch database support matrix, including which drivers appear in the installer. Define draft lifetime and safe administrator password behavior on Back and expiration.
- Confirm inbound mail provider, domain provisioning, retention, abuse controls and the host scheduling capability before the mailbox release.

Phase 0 is documentation only. Obtain approval before application implementation. See [architecture](architecture.md), [design system](design-system.md) and [installation flow](installation-flow.md).

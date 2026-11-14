# Frontend

Use the installer layout and shared password controls on First Super Admin and preserve the shared appearance preference through completion.

Reuse x-admin-layout for console pages and x-appearance in its topbar. Preserve logical spacing and current-page navigation state.

The shared appearance dropdown shows the active icon and label. Close it on selection, Escape, or outside click. Return focus to the trigger after selection or Escape.

Use x-ui.password-field for password entry and confirmation. Its Eye and Eye-off buttons share one script, preserve the entered value, and keep keyboard focus.

Reuse the appearance selector and the early external initialization script for any page that offers appearance controls.

Render pages and forms in Blade. Use native navigation and form submission where possible. Add Alpine for small interactive behaviors with explicit keyboard and focus handling. Preserve readable content and usable core flows if JavaScript fails. Use semantic HTML, mobile-first layouts, and test reflow before widening containers.

Use the existing Laravel Vite plugin, Tailwind CSS 4 CSS-first config, and app CSS and JS entry points. Keep Tailwind class names discoverable as complete strings. Add explicit source coverage only when placing templates outside the current globs. Compile assets locally or in CI. Livewire, React, Vue, and Inertia are outside the selected stack.

Use x-layouts.app for shared page structure and load its theme bootstrap before Vite styles. Follow [component reuse](blade-components.md), [visual rules](design-system.md), and [accessibility](accessibility.md).

Use the global page progress controller for opt-in async work. Keep upload progress tied to measurable bytes and preserve native navigation.

Use the [product patterns](../docs/design-system.md#product-patterns) for action placement, form feedback, overlays and collection state. Keep desktop and mobile navigation driven by the same items.

See [Localization](../docs/localization.md) for the language registry, public locale rules, integration contracts, and release gates.

For font catalog policy, locale typography, and deployment checks, see [Fonts Management](../docs/localization.md#fonts-management).

See [UI Translations](../docs/localization.md#ui-translations) for key registration, status workflow, escaping and deployment checks.

Keep the Roles & permissions matrix aligned with the [authorization contracts](../docs/authorization.md). Verify role counts, direct URL access, and user assignment protections after changes.

Follow the [workspace and console navigation contexts](../docs/components.md#navigation-contexts).

Use the [primary-task contract](../docs/design-system.md#primary-task-contract) to prioritize the main action, preserve task context and define failure recovery.

Use native language names and registry direction. Keep the homepage source and editable localized fields visible together where space permits.

Preview the effective font in localized controls and isolate addresses and identifiers with LTR Geist Mono.

Keep language editing and the sampled appearance together. Scope preview width and theme controls to the sample.

Keep [Typography Studio](../docs/localization.md#typography-studio) centered on language editing and font comparison. Show active compatible families with the same locale sample. Place catalog mutations under Family settings.

Use the shared language navigation for Localization Studio Overview and Homepage. Keep locale typography in Typography Studio. See [Localization](../docs/localization.md#homepage-publishing).

Follow the product-wide design direction on every screen. Preserve working behavior and verify responsive layouts, both themes and interactive states.

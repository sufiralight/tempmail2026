# Blade components

Search resources/views/components and its callers before introducing shared UI. Centralize recurring controls, layout patterns, and feedback in Blade components. Extend an existing API when variants share the same semantics. Preserve existing consumers or migrate them together.

Use x-ui.* for the shared catalog, with kebab-case names such as x-ui.button, x-ui.input, x-ui.password-field, x-ui.modal, and x-ui.dropdown. Prefer anonymous components until server-side behavior justifies a class. Define props and defaults, slots, forwarded attributes, variants, and required accessible names. Merge consumer classes deliberately and keep state styling central.

Use the [component catalog](../docs/components.md) to track actual APIs and planned patterns. Update it alongside each component change and verify the [accessibility contract](accessibility.md).

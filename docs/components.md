# Blade component catalog

Status for each API below is **Planned**. The starter checkout has a welcome view. Use anonymous Blade components when props, slots and attribute forwarding are sufficient. Document the rendered element, props and defaults, slots, label requirements and events when an API is implemented. Allow caller attributes such as id, name, autocomplete and aria-describedby where applicable, while keeping component state and styling centralized.

| Proposed API | Contract |
| --- | --- |
| x-layouts.app | Shared document, skip link, landmarks, early theme initialization and Vite entries |
| x-appearance | Light, Dark and System choices with active label and icon, dismissal and focus restoration |
| x-ui.button | Visible default slot, primary/secondary/quiet/danger variants, explicit submit type, default type button, native disabled and pending state |
| x-ui.icon-button | Native button, required accessible name and decorative icon hidden from assistive technology |
| x-ui.input | Labeled input with associated hint, invalid state and error |
| x-ui.password-field | Shared initially masked input and Eye/Eye-off toggle for entry and confirmation |
| x-ui.alert and x-ui.spinner | Shared severity, meaningful status text and reduced-motion progress |
| x-ui.dropdown and x-ui.modal | Dismissal, keyboard operation, appropriate focus placement and restoration |

Use consistent arrow-back, close, Eye/Eye-off and chevron icons. Pair navigation with text where space permits and use real links with hrefs. The password toggle uses a type=button control, updates its accessible name between Show password and Hide password, retains focus, and preserves the input value and autocomplete. Password managers and paste remain available.

## Navigation contexts

The public shell exposes public destinations. The authenticated workspace exposes account and mailbox destinations. The Admin Console link and direct routes must share the admin.access Gate, and privileged mutations need their own server-side checks. Use aria-current="page" on the current leaf link. Derive mobile and desktop navigation from the same route and permission definitions. Use buttons for disclosures and links for navigation.

See [Blade rules](../agents/blade-components.md), [design states](design-system.md#product-patterns) and [keyboard and ARIA requirements](accessibility.md).

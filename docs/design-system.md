# Design system

## Product-wide visual direction

Use Linear as the lead reference for hierarchy, density and quiet navigation. Use Vercel as a reference for typography and spacing, GitHub for predictable controls and Raycast for concise action labels and icon placement. Use a neutral surface hierarchy, restrained accent usage, compact but readable controls and generous space around the main task. Use shared spacing, radius, elevation and type scales across public, setup, authentication and console pages. Prefer a system fallback for every font. Decide families, script coverage, delivery and fallback behavior before integrating Google Fonts.

## Appearance

Offer Light, Dark and System through x-appearance. Store one explicit preference, default to System, and resolve it before first paint where possible. Follow OS changes in System mode. Tolerate unavailable storage and keep the page usable with CSS system defaults when initialization fails. Set the document color scheme for native controls. Both themes expose identical [semantic tokens](color-system.md).

## Primary-task contract

For each new or revised screen, document the actor, entry point, required data, primary action, success outcome, failure recovery and measurable acceptance checks. For Database Configuration, a verified valid connection advances directly to Administrator Account, a failed verification stays on the step with actionable feedback, and Back restores the verified draft. At default zoom the installer fits a 1440 × 900 viewport. At narrow widths or zoom it scrolls naturally.

## Product patterns

Place one clear primary action in task context. Group fields by purpose and put recovery guidance next to the affected control. Use explicit current-page state, a readable empty state and confirmation for irreversible actions. Use the same navigation items at all widths. Keep keyboard reading order aligned with visual order.

| State | Required treatment |
| --- | --- |
| Default | Visible label and recognizable control boundary where needed |
| Hover | Semantic surface or foreground change with the label still readable |
| Focus-visible | Clear ring with spacing from the edge and visibility above sticky content |
| Active | Distinct pressed treatment during activation |
| Selected/current | Persistent visual marker and appropriate semantic state |
| Disabled | Native disabled where available, muted treatment and nearby reason when needed |
| Error | Visible explanation, associated invalid field and semantic error roles |
| Loading | Shared progress treatment, stable label/geometry, duplicate-submit protection and announced outcome |

Use one loading indicator family and shared timing. Provide a static indicator and meaningful status text with reduced motion. For measurable uploads, report real progress. See the [component catalog](components.md) and [accessibility standard](accessibility.md).

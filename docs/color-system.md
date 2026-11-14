# Color system

## Approved palette

The product specifies 16 official colors. The source design decisions and exact values are absent from this checkout. Palette registration and theme assignments are pending receipt of the authoritative record. Copy all 16 values exactly, including the original names where supplied. Record each semantic assignment and approved pairing before implementing component colors.

## Semantic mappings

Both themes expose the same token names. Assign the following roles to the approved primitives independently for each theme. Multiple roles may share a primitive where their rendered pairings pass. Keep primitive values and theme mappings centralized in the app stylesheet or an imported token stylesheet. Expose semantic utilities through Tailwind's CSS-first theme. Reusable components consume those utilities and variables. Keep literal colors and arbitrary Zinc, Slate, Gray, black and white utilities out of reusable components.

| Semantic roles | Component usage | Verify against |
| --- | --- | --- |
| canvas, surface, surface-raised | Page, card, menu and dialog backgrounds | Foreground text and required boundaries |
| text, text-muted | Body, labels, helper copy and placeholders | Each actual surface |
| border, control-border | Decorative divider and identifying control boundary | Adjacent surfaces where the boundary conveys information |
| accent, on-accent, accent-hover, accent-active | Primary buttons, links and pressed surfaces | Button labels or surrounding surface for links |
| interaction-hover, interaction-active, selected | Quiet buttons, navigation and selection fills | Content and selected-state marker |
| focus-ring | Keyboard focus on any interactive surface | Surrounding colors, including on accent surfaces |
| disabled-surface, disabled-text | Unavailable controls | Readability in context |
| error, success, warning, info and corresponding status surfaces | Inline errors, alerts and completion | Text, icons and actual status backgrounds |

## Contrast verification

Require at least 4.5:1 for normal text, 3:1 for large text (18 pt regular or 14 pt bold), and 3:1 for visual information needed to identify controls and states against adjacent colors. Use 3:1 against adjacent colors as the project focus-ring target. Inactive controls have WCAG contrast exceptions. Retain readable status and instructions outside disabled controls. Check actual rendered pairs in both themes, including overlays, opacity and interaction states. Communicate meaning with text, shape or iconography as well as color. [WCAG 2.2](https://www.w3.org/TR/WCAG22/)

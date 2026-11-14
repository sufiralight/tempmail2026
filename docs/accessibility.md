# Accessibility

Target WCAG 2.2 AA. Use semantic landmarks and headings, a skip link, meaningful page titles and visible labels where applicable and accessible names for every control. Use native controls and their normal Tab, Shift+Tab, Enter and Space behavior. Add ARIA where native HTML cannot express the relationship or state. [WCAG 2.2](https://www.w3.org/TR/WCAG22/)

- Give icon-only controls an action-specific accessible name and hide decorative icons from assistive technology. Use a native button for an action and a named link for a destination.
- Associate labels, hints and errors with their fields. Set aria-invalid when validation fails and preserve input according to the form's security rules. For a failed form submission, move focus to the error summary or first invalid field so recovery is discoverable.
- Use aria-expanded and aria-controls on disclosure triggers. Keep disclosure contents in normal tab order. Implement arrow-key behavior when adopting an ARIA menu or another composite widget with that expectation. Escape closes overlays and returns focus to the trigger when it still exists.
- Give modal dialogs accessible names. Move focus inside on open, keep it within while modal, and restore it to the invoking control or a logical successor. Keep focused controls visible above sticky regions.
- Announce asynchronous updates through a persistent polite status region. Reserve alerts for urgent errors. Use aria-busy on the affected region where appropriate. Keep visible status text available during reduced motion.
- Provide 24 × 24 CSS px targets or qualifying spacing under WCAG 2.2 AA. Favor larger targets for primary touch actions. Verify normal reading and operation at 320 CSS px width and with 200% text resizing. Avoid content clipping and horizontal scrolling except for content that requires two-dimensional layout.
- Respect prefers-reduced-motion. Remove nonessential animation and keep a static loading cue. Check forced-colors support and verify all [contrast pairings](color-system.md#contrast-verification).

For each changed interface, exercise the primary task and recovery with keyboard alone, verify announcements and labels with a screen reader, and check Light, Dark and System at 320 px, 390 px and 1440 × 900. Include zoom, reduced motion, focus order and failure states. Record tested browsers, assistive technology, and any gaps. Automated checks supplement manual interaction checks.

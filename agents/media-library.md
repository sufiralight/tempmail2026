# Media Library

Use the media.* routes under /media and the existing owner policy. Keep private files on the media disk and render them through the authorized delivery endpoint. Use x-ui.media-picker for image selection and revalidate ownership on submission. Global branding uses admin.settings authorization and only publishes generated previews. Preserve reference checks and the shared workspace lock when adding consumers. See [Media Library](../docs/media-library.md).

Branding writes use settings.manage and the workspace lock. Preview draft choices privately and publish only after the transaction succeeds.

# Profile design

The profile uses an original SVG banner, mint/lavender accents, numbered project sections, short introductions, and an expandable evidence section. The content remains readable without images. Assets are stored in this repository; the README needs no widget service, token, scheduled workflow, or visitor tracker.

## References reviewed

- [Sindre Sorhus](https://github.com/sindresorhus): concise introduction and strong use of native repository pins.
- [Anurag Hazra](https://github.com/anuraghazra): personal introduction followed by a clear project hierarchy.
- [DenverCoder1](https://github.com/DenverCoder1): distinct project/tool sections and explicit limits on what statistics represent.
- [GitHub writing quickstart](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github): responsive banners and expandable sections supported by GitHub Markdown.

These informed the structure; no artwork or profile wording was copied.

## Maintenance

- Edit both `assets/header-light.svg` and `assets/header-dark.svg` when changing banner text. Keep the visible identity in the image alt text and native README introduction.
- The `<picture>` sources follow `prefers-color-scheme`. GitHub theme overrides can differ from system preference; both variants have their own complete background and legible contrast.
- Keep the main project summaries brief and the verification notes accurate. Update test counts only when supported by the linked evidence.
- Keep relative images and write-up links inside this repository so branch previews work.
- The public LinkedIn URL matches the existing profile social link.

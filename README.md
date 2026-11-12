# sazeri.fyi – Static Link-in-Bio & Protected Landing Pages

Lightweight, fast static landing pages designed for creators.  
Built for **Cloudflare Pages** with optional Turnstile protection and multi-profile support via folders/subpaths.

## Features

- Pure static HTML / CSS / JS (no build step required)
- Mobile-first responsive design
- Cloudflare Turnstile human verification on protected pages
- Multiple independent profiles via simple folders (e.g. `/sarysaz`, `/sazrylesson`)
- Optimized assets for fast load times
- Easy to clone and customize per creator

## Project Structure

```
/
├── index.html              # Main / default landing page
├── unlock.html             # Protected unlock / redirect page (Turnstile)
├── images/
│   ├── profile.jpg
│   └── more-of-me.jpg
├── sarysaz/                # Example profile
│   ├── index.html
│   ├── unlock.html
│   └── images/
├── sazrylesson/            # Another profile
│   ├── index.html
│   ├── unlock.html
│   └── images/
├── LICENSE
└── README.md
```

## Quick Start

1. Clone or download this repository
2. Deploy to **Cloudflare Pages** (connect the Git repo or upload the folder)
3. Set your custom domain in Cloudflare
4. Add your Cloudflare Turnstile site key in each `unlock.html`
5. Replace images and links per profile

### Cloudflare Pages Settings (recommended)

- Framework preset: **None**
- Build command: *(leave empty)*
- Build output directory: `/` (root)

## Customization

Per profile folder you typically change:

| File          | What to edit                                      |
|---------------|---------------------------------------------------|
| `index.html`  | Name, bio, Instagram / Twitter links, images      |
| `unlock.html` | `OF_LINK` (or any destination URL), Turnstile key |
| `images/`     | `profile.jpg`, `more-of-me.jpg`                   |

## Security / Bot Protection

Protected pages use [Cloudflare Turnstile](https://www.cloudflare.com/products/turnstile/).  
Replace the `data-sitekey` value with your own site key from the Cloudflare dashboard.

## Performance Notes

- Keep profile images ≤ ~150 KB and “more of me” images ≤ ~250 KB
- Prefer 500×500 (profile) and max-width ~1000 px (content images)
- The templates already use system fonts and minimal CSS for fast first paint

## License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

## Credits

Built as a simple, privacy-friendly alternative to heavy link-in-bio platforms.  
Optimized for deployment on Cloudflare Pages + Cloudflare DNS.

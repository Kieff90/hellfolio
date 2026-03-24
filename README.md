# AI Portfolio Template

A single-file personal portfolio with an **AI voice assistant** powered by [Deepgram](https://deepgram.com) + Claude (Anthropic).

**Zero build step. No Node. No npm. Pure HTML/CSS/JS.**

> **Live demo** → coming soon &nbsp;|&nbsp; **Clone & customize in ~20 min**

## Features

- **AI Voice Assistant** — visitors can talk to an AI that answers questions about you
- **Zero dependencies** — single `index.html`, works on any static host
- **Dark design** — neon accent, monospace typography, smooth animations
- **Stats counter** — animated count-up on scroll
- **SEO ready** — JSON-LD Person schema, OG tags, IndexNow, sitemap
- **Fully responsive** — mobile-first, works on all screen sizes
- **Accessible** — ARIA labels, reduced-motion support, keyboard navigation

## Quick Start

### 1. Clone the repo
```bash
git clone https://github.com/Kieff90/hellfolio.git
cd hellfolio
```

### 2. Get a Deepgram API key
1. Sign up at [console.deepgram.com](https://console.deepgram.com)
2. Create a **restricted** API key with scope `usage:write`
3. Set a budget cap (recommended: $20/month)

### 3. Customize `index.html`

Open `index.html` and find the `CONFIG` block at the top of the `<script>` section. Fill in your details:

```javascript
var CONFIG = {
  name:        { first: 'Jane', last: 'Doe' },
  title:       'Product Manager & AI Strategist',
  email:       'jane@example.com',
  deepgramKey: 'YOUR_DEEPGRAM_KEY',
  // ... see full config in the file
};
```

### 4. Add your photo
Place a square photo (400×400px min) at `assets/your-photo.jpg`.
See `assets/PLACE_YOUR_PHOTO_HERE.md` for full specs.

### 5. Create your OG social image
Design a 1200×628px image and save as `og-image.png` in the root folder.
See `assets/OG_IMAGE_GUIDE.md` for tools and tips.

### 6. Update the meta tags and JSON-LD
In the `<head>` section, replace all remaining placeholders.
Search for `YOUR_NAME` in `index.html` — there are ~15 occurrences across the `<head>` block (title, meta tags, JSON-LD schema). Also search `yourdomain.com` (~10 occurrences) and `YOUR_JOB_TITLE` (~5 occurrences).

> **Tip**: A find-and-replace in your editor (Cmd+Shift+H / Ctrl+H) covers all instances at once.

### 7. Deploy
Works on **GitHub Pages**, **Netlify**, **Vercel**, **IONOS**, or any static host.

For GitHub Actions auto-deploy via SFTP, see `.github/workflows/deploy.yml`.

## AI Voice Assistant

The voice assistant uses:
- **Deepgram** for speech-to-text + text-to-speech (model: `aura-2-aries-en`)
- **Anthropic Claude** as the reasoning engine (via Deepgram's "think" provider)

Visitors click the mic button, speak, and the AI answers using ONLY the facts you defined in `CONFIG.aiPersona`.

**Security note**: The Deepgram API key is exposed client-side. Always use a restricted key with a monthly budget cap.

## CONFIG Reference

All personal data lives in the `CONFIG` object at the top of the `<script>` block:

| Key | Description |
|-----|-------------|
| `name.first` / `name.last` | Your first and last name |
| `title` | Your job title |
| `tagline` | Short hero tagline |
| `location` | City, Country |
| `email` | Contact email (used for copy-to-clipboard) |
| `phone` | Phone number — set `''` to hide from footer |
| `linkedin` | Full LinkedIn profile URL |
| `github` | Full GitHub profile URL |
| `orcid` | ORCID identifier — set `''` to hide |
| `siteUrl` | Your full site URL |
| `gaId` | Google Analytics 4 ID — set `''` to disable |
| `deepgramKey` | Deepgram restricted API key |
| `voiceGreeting` | First sentence the AI speaks |
| `aiPersona` | System prompt defining what the AI knows about you |
| `stats` | Array of 4 stat objects `{ number, label }` |

## SEO Setup

### Google Search Console
1. Verify ownership via `<meta name="google-site-verification">` in `<head>`
2. Submit your sitemap at Search Console → Sitemaps: `https://yourdomain.com/sitemap.xml`

### Bing / IndexNow
1. Get your IndexNow key from [Bing Webmaster Tools](https://www.bing.com/webmasters)
2. Rename `YOUR_INDEXNOW_KEY.txt` to match your actual key (e.g. `abc123.txt`)
3. Add the key to GitHub Secrets as `INDEXNOW_KEY` and `SITE_URL`
4. See `INDEXNOW_SETUP.md` for full instructions

### JSON-LD Structured Data
Edit the `<script type="application/ld+json">` block in `<head>` to replace all placeholder values with your real data. This helps search engines understand who you are.

## Deployment Options

### GitHub Pages (free)
1. Push to a public repo
2. Go to Settings → Pages → Source: Deploy from branch `main`
3. Your site will be at `https://YOUR_USERNAME.github.io/repo-name`

### Netlify (free)
1. Connect your GitHub repo at [netlify.com](https://netlify.com)
2. Build command: leave empty
3. Publish directory: `/` (root)

### SFTP hosting (IONOS, Bluehost, etc.)
Use the included `.github/workflows/deploy.yml` GitHub Actions workflow.
Configure `SFTP_HOST`, `SFTP_USER`, `SFTP_PASSWORD` as GitHub Secrets.

### Vercel (free)
1. Import your GitHub repo at [vercel.com](https://vercel.com)
2. Framework: Other (static)
3. No build command needed

## License

MIT — free to use, modify, and distribute. Attribution appreciated but not required.

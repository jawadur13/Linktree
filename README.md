# Linktree — Personal Connect Page

A clean, minimal, and fully self-contained **link-in-bio** landing page for **Md. Jawadur Rafid**. It aggregates portfolio, professional, and social profiles into a single, elegant page hosted at **[connect.jawadurrafid.com](https://connect.jawadurrafid.com)**.

Built as a single static HTML file with no build step, framework, or dependencies — just open it in a browser or serve it from any static host.

---

## ✨ Features

- **Zero dependencies** — no npm install, no bundler, no JavaScript framework. Pure HTML, CSS, and vanilla JS.
- **Fully responsive** — mobile-first layout that adapts gracefully from phones to desktops.
- **Dark, ambient design** — Apple/Linear-inspired aesthetic with subtle radial gradient glows and glassmorphic cards (`backdrop-filter` blur).
- **Staggered entrance animations** — cards fade and slide up sequentially using CSS variables (`--delay`) for a polished load.
- **Interactive spotlight hover** — a mouse-tracking radial glow follows the cursor on each card.
- **Brand-colored hover states** — each link (LinkedIn, GitHub, WhatsApp, etc.) lights up in its own brand color on hover.
- **Accessible** — semantic markup, `aria-label` attributes on every link, and `rel="noopener noreferrer"` on external links.
- **Social sharing ready** — Open Graph meta tags for rich link previews on social platforms.
- **Custom favicon** — bundled inline SVG icon (`favicon.svg`).

---

## 📂 Project Structure

```text
.
├── index.html      # The entire site — markup, styles, and behavior
├── profile.png     # Profile photo shown in the header
├── favicon.svg     # Custom site icon
├── CNAME           # Custom domain for GitHub Pages (connect.jawadurrafid.com)
└── README.md       # This file
```

Everything lives in `index.html` — the `<style>` block holds the design system, and a small `<script>` powers the spotlight cursor effect.

---

## 🚀 Getting Started

### Local preview

Because this is a static page, you can preview it instantly:

```bash
# Option 1 — just open the file
open index.html                 # macOS
start index.html                # Windows
xdg-open index.html             # Linux

# Option 2 — serve it locally (recommended for accurate paths)
python3 -m http.server 8000
# then visit http://localhost:8000
```

No installation or compilation is required.

### Deployment

The page is designed to be served as a static site. It is configured for **GitHub Pages** via the `CNAME` file, which points the custom domain to:

```text
connect.jawadurrafid.com
```

To deploy on GitHub Pages (or any static host such as Netlify, Vercel, Cloudflare Pages):

1. Push the repository to GitHub.
2. In **Settings → Pages**, set the source to the `main` branch (root).
3. The `CNAME` file automatically binds the custom domain.
4. Add/verify the domain's DNS records as instructed by GitHub.

> Any static file host works — just upload `index.html`, `profile.png`, `favicon.svg`, and `CNAME`.

---

## 🔗 Included Links

Links are grouped into three labeled sections:

| Section | Links |
| --- | --- |
| **Portfolio & Work** | Website, LinkedIn, GitHub, Kaggle, Business Email |
| **Contact** | Personal Email, Backup Email, WhatsApp, Telegram |
| **Social** | Facebook, Instagram, X / Twitter, Threads, Discord |

---

## ✏️ Customization

All visual tuning happens through CSS custom properties at the top of the `<style>` block in `index.html`:

```css
:root {
  --bg-color: #070709;
  --card-bg: rgba(255, 255, 255, 0.035);
  --card-border: rgba(255, 255, 255, 0.07);
  --text-primary: #F5F5F7;
  --text-secondary: #86868B;
  --accent-color: #FFFFFF;
  --transition: all 0.35s cubic-bezier(0.16, 1, 0.3, 1);
}
```

Common edits:

- **Profile name & subtitle** — update the `<h1 class="name">` and `<p class="subtitle">` in the `<header>`.
- **Profile photo** — replace `profile.png` (or change the `src` on the `.profile-photo` `<img>`).
- **Add / remove a link** — copy an existing `<a class="link-card ...">` block, set its `href`, `aria-label`, icon SVG, and `--delay` value.
- **Reorder / regroup** — move cards between the `<div class="section-label">` dividers.
- **Animation timing** — adjust the `style="--delay: 0.04s"` on each card for stagger speed.
- **Meta / SEO** — edit the `<title>`, `<meta name="description">`, and Open Graph tags in the `<head>`.

### Brand hover colors

Each platform has a dedicated `.card-<brand>:hover` rule (e.g. `.card-linkedin`, `.card-whatsapp`). Add or tweak these to match new services — see lines ~276–382 in `index.html`.

---

## 🛠️ Tech Stack

| Concern | Choice |
| --- | --- |
| Markup | Semantic HTML5 |
| Styling | Hand-written CSS (CSS variables, Flexbox, animations) |
| Interactivity | Vanilla JavaScript (cursor spotlight) |
| Fonts | [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts |
| Hosting | GitHub Pages (custom domain) |

---

## 📄 License

This is a personal project. All linked profiles and assets belong to their respective owners.

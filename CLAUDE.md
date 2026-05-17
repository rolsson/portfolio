# Portfolio — Project Briefing for Claude Code

## What this is
A personal portfolio site for Robert Olsson, a full-stack software consultant.
Built with SvelteKit and deployed to Cloudflare Pages.

## Live URL
- **Frontend**: Cloudflare Pages (auto-deploys from GitHub on push to main)
- Configure the Pages project at: https://dash.cloudflare.com → Workers & Pages

## Architecture
```
Browser
  ↓
Cloudflare Pages
  ↓
SvelteKit (adapter-cloudflare)
```

## Repo structure
```
portfolio/
├── src/
│   ├── routes/
│   │   ├── +layout.svelte   ← Google Fonts loaded here
│   │   └── +page.svelte     ← All portfolio content and styles
│   └── app.html             ← HTML shell
├── static/                  ← Static assets (favicon, images)
├── svelte.config.js         ← Uses adapter-cloudflare
├── vite.config.js
├── wrangler.toml
└── package.json
```

## Customising content

All content lives in `src/routes/+page.svelte`. Key areas to edit:

### Personal info
- **Name / tagline**: Update `<h1>` in the hero section
- **Hero subheading**: The `<p class="hero-sub">` paragraph
- **About text**: Two `<p>` tags inside `.about-text`
- **Contact email**: The `mailto:` link at the bottom (currently `robert.olsson@pure.se`)
- **Footer year**: Update the `© 2026` line as needed

### Projects
Edit the `projects` array at the top of the `<script>` block:

```js
const projects = [
  {
    title: 'My Project',
    description: 'What it does and why it matters.',
    tech: ['SvelteKit', 'TypeScript'],
    url: 'https://example.com'  // shown as a link if you add one to the card
  },
  ...
];
```

### Focus areas (About section)
The three cards (Performance, Usability, Quality) are hardcoded in the template.
Edit the `.focus-card` blocks directly in the HTML to change icons, headings, or descriptions.

### Design tokens (CSS custom properties)
All colour and spacing decisions are plain CSS in the `<style>` block.
Key values to tweak:
- Accent colour: `#2563eb` (blue-600) — appears on eyebrow text and focus icons
- Dark text / button: `#0f172a` (slate-900)
- Muted text: `#475569` (slate-600)
- Background alt: `#f8fafc` (slate-50) — used for the Projects section

## Development
```bash
cd ~/dev/claude/portfolio
npm install
npm run dev        # http://localhost:5173
npm run build      # build for Cloudflare
npm run preview    # preview the build locally
```

## Deployment

### First time setup
1. Push this repo to GitHub
2. Go to Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git
3. Select the repo
4. Build settings:
   - **Framework preset**: SvelteKit
   - **Build command**: `npm run build`
   - **Build output directory**: `.svelte-kit/cloudflare`
5. Save — Cloudflare will auto-deploy on every push to `main`

### Ongoing deploys
Just `git push` — Cloudflare Pages picks it up automatically.

## Key decisions
- No framework extras (no Tailwind, no component library) — plain scoped CSS for full control
- Single-page layout with smooth-scroll anchor links
- Svelte 5 with `$props()` rune syntax
- Inter font from Google Fonts (loaded in `+layout.svelte`)
- Sticky frosted-glass header via `backdrop-filter`

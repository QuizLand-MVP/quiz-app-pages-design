# Quiz Land UI Guidelines & Page Designs

This repository contains the current Quiz Land UI brand guideline book and a static HTML/CSS page archive for the app experience.

Quiz Land is a cozy live browser quiz game for families and friends. The UI direction is playful, warm, rounded, colorful, and simple: soft cream backgrounds, friendly pill labels, rounded cards, coral/blue/teal/yellow accents, and short punchy copy.

## Repository structure

```text
.
├── assets/
│   └── media/
│       └── content loaded here
├── quiz-land-pages/
│   ├── index.html
│   ├── pages.html
│   ├── maintenance.html
│   ├── 404.html
│   ├── assets/
│   ├── css/
│   │   ├── admin/
│   │   ├── game/
│   │   ├── general/
│   │   ├── host/
│   │   ├── landing/
│   │   └── login/
│   ├── admin/
│   ├── game/
│   ├── host/
│   └── login/
├── .gitignore
├── quiz-land-brand-ui-guidelines-v2.docx
├── quiz-land-brand-ui-guidelines.md
└── README.md
```

## What is included

### Brand guideline files

| File | Purpose |
| --- | --- |
| `quiz-land-brand-ui-guidelines-v2.docx` | Full visual brand guideline book with screenshots and UI component references |
| `quiz-land-brand-ui-guidelines.md` | Markdown version of the guideline book for quick reading in GitHub |

Use these files as the source of truth before creating or changing app screens.

### Designed pages

The static pages are stored in `quiz-land-pages/`.

| Area | Files |
| --- | --- |
| Landing | `quiz-land-pages/index.html` |
| Page index | `quiz-land-pages/pages.html` |
| General | `quiz-land-pages/maintenance.html`, `quiz-land-pages/404.html` |
| Admin | `quiz-land-pages/admin/` |
| Host | `quiz-land-pages/host/` |
| Login | `quiz-land-pages/login/` |
| Game/player flow | `quiz-land-pages/game/` |

The CSS is stored separately in `quiz-land-pages/css/`, with folders matching the page areas.

## Preview locally

Use any static web server from the repository root.

### Option 1: Python

```bash
python3 -m http.server 8080
```

Open:

```text
http://localhost:8080/quiz-land-pages/
```

### Option 2: Node

```bash
npx serve .
```

Then open the local URL shown in the terminal.

## Design source of truth

When adding or updating pages, follow the current guideline book and existing page styles.

Core visual tokens:

```css
--bg: #fbf5ef;
--panel: #fffdf9;
--ink: #12324a;
--muted: #667689;
--line: #eadfd5;
--blue: #375ea3;
--blue-action: #2f70e6;
--blue-soft: #e8f0ff;
--coral: #ef8d6b;
--coral-dark: #df6f4f;
--coral-soft: #fff0e8;
--yellow: #f4c95f;
--yellow-soft: #fff5cf;
--teal: #35a6a2;
--teal-soft: #c3f8f5;
--radius: 24px;
--radius-sm: 14px;
```

Typography:

```css
font-family: "Baloo 2", "Nunito Sans", "Inter", sans-serif;
```

## UI rules

Use these rules when changing the designs:

1. Use the latest transparent Quiz Land logo from `quiz-land-pages/assets/`.
2. Keep page backgrounds warm cream, not cold gray or white-only.
3. Use rounded panels and cards with 20–24px radius.
4. Use coral pills/eyebrows for section labels.
5. Use blue for primary app actions when the screen is functional/admin-like.
6. Use coral gradient for marketing-style CTAs.
7. Keep copy short, friendly, and playful.
8. Avoid old blue-outline card styles or sharp admin dashboards.
9. For mobile, stack dense grids into one column.
10. Keep shared assets in `quiz-land-pages/assets/`; do not duplicate images inside every page folder.

## Adding a new page

Recommended process:

1. Create the HTML file inside the correct area folder:
   - `quiz-land-pages/admin/`
   - `quiz-land-pages/host/`
   - `quiz-land-pages/game/`
   - `quiz-land-pages/login/`

2. Create a matching CSS file inside:

```text
quiz-land-pages/css/<area>/
```

3. Link CSS with a relative path from the HTML file:

```html
<link rel="stylesheet" href="../css/game/example-page.css" />
```

4. Reference the shared logo like this:

```html
<img class="logo" src="../assets/quiz-land-logo.png" alt="Quiz Land" />
```

5. Add the page to `quiz-land-pages/pages.html` so it is easy to preview.

## Current page groups

### Admin

Admin pages use a wider layout with a sidebar, soft panels, metric cards, filters, review cards, and draft/status labels.

Expected files:

```text
quiz-land-pages/admin/index.html
quiz-land-pages/admin/questions.html
quiz-land-pages/admin/users.html
quiz-land-pages/admin/analytics.html
quiz-land-pages/admin/generate-questions.html
```

### Host

Host pages cover quiz setup, lobby, and host final leaderboard.

Expected files:

```text
quiz-land-pages/host/setup.html
quiz-land-pages/host/lobby.html
quiz-land-pages/host/final-leaderboard.html
```

### Login

Login pages should stay focused and simple, with a clear title, short explanation, and two login paths where needed.

Expected files:

```text
quiz-land-pages/login/index.html
```

### Game

Game pages are mobile-first because players usually join and answer from phones.

Expected files:

```text
quiz-land-pages/game/player-join.html
quiz-land-pages/game/in-game.html
quiz-land-pages/game/answer-reveal.html
quiz-land-pages/game/leaderboard.html
quiz-land-pages/game/final-leaderboard-player.html
```

## Media assets

Use `assets/media/` for source images, screenshots, social visuals, or other content that is not directly referenced by the static page archive.

Use `quiz-land-pages/assets/` for images required by the static HTML pages.

## Git hygiene

Recommended `.gitignore` entries:

```gitignore
.DS_Store
node_modules/
dist/
build/
.cache/
.vite/
.env
.env.*
```

Do not commit private API keys, generated secrets, or production environment files.

## Notes for implementation

These static pages are visual references, not the final React app. When implementing them in the app:

- Convert page sections into reusable React components.
- Keep class names close to the static files where practical.
- Reuse the same CSS tokens.
- Preserve responsive behavior.
- Replace static values with real data from the app state/API.
- Keep generated questions in Draft until reviewed and approved.

## Quick checklist before merging UI changes

- [ ] Page matches the brand guideline book.
- [ ] Logo uses the latest transparent asset.
- [ ] CSS lives under the matching `quiz-land-pages/css/` area folder.
- [ ] HTML links use correct relative paths.
- [ ] Mobile layout checked at 360px width.
- [ ] Desktop layout checked at 1280px width.
- [ ] No old blue-outline/generated component styles were reintroduced.
- [ ] New page is linked from `quiz-land-pages/pages.html`.

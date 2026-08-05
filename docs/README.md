# Quiz Land Pages — GitHub Pages site

## Folder structure

```text
docs/
├── index.html
├── pages.html
├── landing.html
├── maintenance.html
├── 404.html
├── assets/
│   ├── quiz-land-logo.png
│   └── logo.png
├── css/
│   ├── admin/
│   │   └── admin.css
│   ├── host/
│   │   ├── setup.css
│   │   ├── lobby.css
│   │   └── final-leaderboard.css
│   ├── login/
│   │   └── host-login.css
│   ├── game/
│   │   ├── player-join.css
│   │   └── in-game.css
│   └── general/
│       └── status.css
├── admin/
│   ├── index.html
│   ├── questions.html
│   ├── generate-questions.html
│   ├── themes.html
│   ├── users.html
│   └── analytics.html
├── host/
│   ├── setup.html
│   ├── lobby.html
│   ├── leaderboard.html
│   └── final-leaderboard.html
├── login/
│   └── index.html
└── game/
    ├── player-join.html
    ├── in-game.html
    ├── leaderboard.html
    └── final-leaderboard-player.html
```

## Notes

- `maintenance.html` and `404.html` are kept at the root level as general pages.
- CSS is stored in a root-level `css/` folder.
- CSS folder structure mirrors the HTML page groups.
- Shared images are stored in root-level `assets/`.
- The latest transparent Quiz Land logo is used across the archive.
- `index.html` redirects to `pages.html`, the page index used as the site's entry point.
- `landing.html` contains the Quiz Land beta landing page.
- GitHub Pages serves this directory when the repository's Pages source is set to `main` and `/docs`.
- Every design screen includes an archive-only link back to `pages.html`. Elements marked `data-preview-only` must be ignored when implementing the product UI.


## v11 fixes

- Host setup: questions/difficulty/timer use segmented controls; selected state is blue.
- Host lobby: Theme, Questions, Timer labels use coral eyebrow style.
- Final leaderboard host/player: player rows are cards instead of divider rows.
- Player join: title moved above game code, color spacing increased, waiting label removed.
- In-game: question type reduced one level; answer options are 2 columns desktop and 1 column mobile.
- Game leaderboard: player rows are cards; scoring shown as inline capsules; rank circles use guideline colors.
- Maintenance: message split into two lines; try-again button removed.


## v12 fixes

- Host setup: questions, difficulty, and timer remain segmented controls; selected state changed to light coral.
- Host setup: Create game button changed to blue.
- Player join: Join Movie Night is above game code; icon color spacing increased; waiting label removed.
- In-game: mobile answer options forced to one-column layout while desktop stays two columns.


## v13 update

- Added the uploaded landing page as `landing.html`.
- The site entry point, `index.html`, redirects to the page-preview index at `pages.html`.
- Added landing CSS at `css/landing/landing.css`.
- Landing page images are stored in shared root `assets/`.

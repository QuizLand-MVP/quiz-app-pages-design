# CLAUDE.md — Quiz Land UI Repository Instructions

You are working on the Quiz Land UI repository.

Quiz Land is a cozy live browser quiz game for families and friends. The design must feel playful, warm, rounded, simple, and a little chaotic in a friendly way.

## Source of truth

Before changing UI, read these files:

```text
quiz-land-brand-ui-guidelines.md
quiz-land-brand-ui-guidelines-v2.docx
quiz-land-pages/
```

The Markdown guideline file is the primary quick reference. The DOCX is the full visual reference.

## Repository structure

Expected structure:

```text
.
├── assets/
│   └── media/
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

## Design tokens

Use these tokens unless the guideline book is intentionally updated:

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
--shadow: 0 18px 40px rgba(31, 44, 58, 0.08);
--shadow-soft: 0 8px 20px rgba(31, 44, 58, 0.05);
--radius: 24px;
--radius-sm: 14px;
```

Typography:

```css
font-family: "Baloo 2", "Nunito Sans", "Inter", sans-serif;
```

## Visual direction

Use:

- Warm cream background: `#fbf5ef`
- Soft cream panels: `#fffdf9`
- Rounded cards: 20–24px radius
- Coral pill labels / eyebrows
- Blue for functional primary app actions
- Coral gradient for marketing CTAs
- Gentle shadows only
- Short, punchy, playful copy

Avoid:

- Old blue-outline card styles
- Sharp rectangular enterprise dashboards
- Cold gray backgrounds
- Dense admin layouts
- Invented visual systems that are not in the guideline book
- Duplicate logo files inside every page folder

## Logo rule

Always use the latest transparent Quiz Land logo from:

```text
quiz-land-pages/assets/quiz-land-logo.png
```

Do not use old non-transparent logo images.

## Static page structure rules

HTML pages belong in area folders:

```text
quiz-land-pages/admin/
quiz-land-pages/host/
quiz-land-pages/game/
quiz-land-pages/login/
```

General pages stay at root:

```text
quiz-land-pages/maintenance.html
quiz-land-pages/404.html
```

CSS must be stored under root-level `quiz-land-pages/css/` and mirror the page area:

```text
quiz-land-pages/css/admin/
quiz-land-pages/css/host/
quiz-land-pages/css/game/
quiz-land-pages/css/login/
quiz-land-pages/css/general/
quiz-land-pages/css/landing/
```

Example:

```html
<link rel="stylesheet" href="../css/game/in-game.css" />
<img class="logo" src="../assets/quiz-land-logo.png" alt="Quiz Land" />
```

## Page-specific conventions

### Host setup

- Page title: `Quiz setup`
- Question count options: `5, 10, 15, 20`
- Difficulty options: `Easy, Medium, Hard`
- Timer options: `10, 15, 30, 45, 60`
- These controls should be segmented controls
- Selected segmented state should be light coral
- `Create game` button should be blue
- No age group section

### Host lobby

- Theme, Questions, Timer labels should use coral eyebrow style
- Game summary values should be centered

### In-game

- Timer should not be inside a card
- Timer progress should be coral
- Timer number should be inside a blue circle
- `seconds` label should sit under the number
- Answer option letters should be blue circles
- Answer options: 2-column grid on desktop, 1-column grid on mobile
- Theme eyebrow should align trailing/right

### Answer reveal

- Match in-game element sizing
- Show question, correct answer, explanation
- No timer
- No question/explanation eyebrow labels if current design says so
- Correct answer should use a non-gradient color block

### Between-question leaderboard

- Each player should be a card
- Do not use divider-only rows
- Score details should be inline capsules
- Example capsules:
  - `Correct answer 800 points`
  - `Speed bonus +120 points`
- Rank circles should use guideline colors: blue, coral, teal, yellow

### Final leaderboard

- Each player should be a card
- Host version: `New quiz` button redirects to host setup
- Player version: `Want to host?` button redirects to host login

### Player join

- Title above game code
- Name input
- Icon color picker
- Join button
- After Join click, button text changes to `Update`
- Do not show a waiting label unless explicitly requested

### Maintenance

- Message split into two lines:
  - `We are polishing the quiz chaos.`
  - `Your next game night is not cancelled.`
- No `Try again` button

## React implementation rules

Static HTML pages are visual references. When implementing in React:

- Preserve visual hierarchy and tokens
- Convert repeated structures into components
- Keep CSS tokens in one shared stylesheet or theme file
- Keep generated questions in Draft until reviewed
- Use real app state/API data instead of hardcoded examples
- Do not change backend behavior unless explicitly requested

## Quality checklist

Before finishing any UI task:

- Confirm the page uses current guideline colors
- Confirm logo path uses shared transparent logo
- Confirm CSS lives in the correct mirrored folder
- Confirm page works at 360px mobile width
- Confirm page works at 1280px desktop width
- Confirm buttons and form controls have visible focus states
- Confirm no old blue-outline/generated component styles were reintroduced
- Confirm any new page is linked from `quiz-land-pages/pages.html`

# Berry Vibes Studio × CCD — Final Fixed GitHub Website

A multi-page HTML/CSS/JavaScript website with an optional Node.js backend for real accounts and server-side uploads. The visual site is designed for GitHub Pages; secure cross-device authentication requires deploying the included Node backend and pointing `config.js` at it.

## Final page set

- `index.html` — authenticated Today dashboard
- `foods.html` — food + drink logging, food photo upload, recipe-card image upload, exact scroll-wheel time
- `recipes.html` — 212 recovered CCD recipes + recipe builder lab + unit calculator + recipe-card gallery
- `sotd.html` — 17 SOTD presets
- `exercise.html` — movement selection + START time + FINISH time; duration and burn auto-calculate
- `fasting.html` — preset fasting windows + start/break time selectors
- `restaurants.html` — recovered restaurant presets + manual new restaurant food nutrition/photo entry
- `battle.html` — playable Food Comparison Battle
- `facts.html` — rotating recipe/movement one-liners
- `calendar.html` — full 42-cell monthly calendar with log dots and selected-day detail
- `profile.html` — editable profile photo, height, weight, reason, and full-site themes
- `about.html`
- `login.html`, `signup.html`, `forgot-password.html`, `reset-password.html`, `forgot-username.html`

There is **no shop**, **no Berry Burst game**, and **no separate accent-color chooser**.

## Authentication/menu behavior

Authentication pages intentionally contain **no top navigation**. Private pages redirect to Sign In if no valid session exists. The complete horizontal navigation appears only after a session is present.

On GitHub Pages, the front end automatically uses its browser-local account mode because GitHub Pages cannot run Node.js. For secure server accounts, deploy `server.js` (for example with the included `render.yaml`) and set the HTTPS backend URL in `config.js`.

## Exercise timing

Movement is logged as a real time range, not a typed duration. Example:

- Started: `11:00 AM`
- Finished: `11:30 AM`
- Auto duration: `30 minutes`
- Estimated burn: calculated from the movement MET preset, auto duration, and profile weight

Time ranges that pass midnight are supported.

## Food + drinks

Food logging supports an optional drink paired with the meal. Built-ins include water, hot cinnamon coffee, orange juice, and skim milk, plus a custom drink field. Known drink nutrition is added automatically to the combined food log. Custom drinks can be named and have an amount noted.

## Data included

- 212 recovered CCD recipe cards
- 8 recovered food-log entries (220 searchable food/recipe entries total)
- 17 SOTD presets
- 11 movement presets
- restaurant preset groups plus custom restaurant entry
- 2,100–2,150 kcal maintenance reference; movement burn remains separate

## Validation

The final build was checked for JavaScript syntax, CSS parsing, duplicate IDs, missing local references, browser initialization across all 17 HTML pages, calendar rendering, food+drink persistence, movement start/finish math, and backend authentication/log routes. See `TEST_REPORT.md`.

## GitHub Pages

Upload the full project contents to your repository. In GitHub open **Settings → Pages → Deploy from a branch → main → /(root)**.

For the backend, deploy the same repository to a Node host with `npm start`, then set `API_BASE` in `config.js` to that HTTPS backend URL.

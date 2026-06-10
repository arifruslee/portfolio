# Portfolio Site Plan

GitHub Pages project site for Arif Ruslee's developer portfolio.
Live URL once deployed: `https://arifruslee.github.io/portfolio`

---

## File structure to build

```
portfolio/
  index.html                   ← developer homepage (product grid)
  css/
    main.css                   ← all shared styles (CSS custom properties)
  products/
    leaftimer/
      index.html               ← LeafTimer product landing page
      privacy.html             ← privacy policy (Play Store + Stripe require this)
  assets/
    leaftimer/
      icon.png                 ← copy from ../plant-app/assets/icon/icon.png
```

**Adding a future product** = create `products/<name>/index.html` + add one card to `index.html`. Nothing else changes.

---

## Design tokens (LeafTimer brand)

```css
--color-primary:    #4C662B;   /* moss-olive */
--color-bg:         #F7F4EF;   /* warm cream */
--color-surface:    #FFFFFF;
--color-text:       #1C1B1A;
--color-text-muted: #5C5A57;
--color-water:      #CDE7F6;
--color-fertilise:  #F8E3BD;
--color-cleanup:    #F6DDD2;
```

---

## Pages

### `index.html` — Developer homepage
- Top nav: "Arif Ruslee" wordmark + GitHub icon link
- Hero: name, tagline ("Building clean, local-first mobile apps"), 1–2 sentence bio
- **Apps** section: CSS Grid product cards (responsive 1 → 2 → 3 cols)
  - Each card: icon, app name, one-line description, "Learn more →" link
  - Currently 1 card: LeafTimer
- Footer: email, GitHub

### `products/leaftimer/index.html` — LeafTimer landing page
- Breadcrumb: ← Back to portfolio
- Hero: icon + "LeafTimer" + tagline ("Never forget to water your plants.")
- **Features** section: 4 highlight cards
  1. Schedule — see what needs care today
  2. Plants & Areas — organise your collection
  3. Smart Notifications — reminders that repeat until done
  4. Local-first + Drive Backup — your data, your device
- **Download** section: "Coming to Google Play" badge placeholder (swap in real URL when live)
- **Privacy** section: short paragraph + link to `privacy.html`

### `products/leaftimer/privacy.html` — Privacy policy
- App is local-first; no data leaves the device except optional Google Drive backup the user initiates
- No analytics, no third-party SDKs that collect data
- Required by both Play Store and Stripe

---

## Technology

- **Pure HTML5 + CSS3** — no npm, no build step, no frameworks
- Responsive via CSS Grid + `clamp()` for fluid type
- Works locally by opening `index.html` directly in a browser

---

## GitHub Pages deployment (once ready)

1. `git init` in this folder
2. Create public repo `portfolio` at github.com/arifruslee
3. `git remote add origin https://github.com/arifruslee/portfolio.git`
4. `git push -u origin main`
5. Repo → Settings → Pages → Source: branch `main`, folder `/`
6. Site live at `https://arifruslee.github.io/portfolio` within ~1 minute

# MSINGI TRADERS DEN

**TRADE • LEARN • BUILD • TOGETHER**

The official website for **Msingi Traders Den**, a trading community built on a strong foundation (*msingi*). It is a dark, futuristic crypto/trading design in the brand's navy, electric blue and gold, with glassmorphism cards, glowing accents and subtle animation.

It is a **single, self-contained HTML file** with no build step, no framework and no dependencies to install. Open it in a browser and it works.

---

## Features

- **Hero:** full-width brand banner image, tagline, short intro, and the *Join Community* (opens the Telegram group) / *Explore Traders* buttons
- **Live background:** softly glowing green and red candlesticks that drift across the page (static if the visitor prefers reduced motion)
- **Trader Data:** animated counters that count up when scrolled into view
- **Community:** four cards (Trade, Learn, Build, Grow)
- **Partners:** active exchange partners with logos, linking to the community's referral links
- **Contact:** *Join Telegram Group* button, social links, email and a *Become a Partner* button (no data-collection form)
- **Footer:** logo, tagline, navigation and an auto-updating copyright year
- Fully responsive, with sticky glass navigation, safe-area support for phones and `prefers-reduced-motion` support

---

## Project structure

```
index.html        # Home: hero, explore tiles, exchange partners
data.html         # Data: animated community stats
founder.html      # Meet the Founder: track record and Sodex PnL cards
community.html    # Community: Trade / Learn / Build / Grow
tools.html        # Tools: trading bots (Trigger Bot, Spoiler Trading Bot)
contact.html      # Contact: Telegram, socials, email, Become a Partner
assets/logo.webp  # shared logo used in the nav and footer
favicon/          # favicon files (copy favicon.ico to the site root)
README.md
```

Each page has the same navigation: **Home, Data, Meet the Founder, Community, Tools, Contact**. On screens under about 1060px the menu collapses into a burger button.

Where to edit: stats in `data.html` (`data-target` values), partners in the `PARTNERS` list in `index.html`, bots in `tools.html`, track record in `founder.html`, social links and email in `contact.html`.

---

## How to edit things

### Branding colours

Find `:root{...}` at the top of the `<style>` block:

```css
--bg:#04070f;   /* page background */
--blue:#1e90ff; /* electric blue */
--cyan:#38c8ff; /* glow / highlights */
--gold:#ffc83d; /* accent / buttons */
```

### Stats (animated counters)

In the **Trader Data** section, change the `data-target` values:

```html
<div class="num" data-target="200" data-suffix="+">0</div>
<div class="num" data-target="1.3" data-dec="1" data-prefix="$" data-suffix="M">0</div>
```

| Attribute | What it does |
|-----------|--------------|
| `data-target` | the final number |
| `data-dec` | decimal places (for example `1` for 1.3) |
| `data-prefix` | text before the number (for example `$`) |
| `data-suffix` | text after the number (for example `+`, `M`) |

**Current figures:** 200+ total traders, $1.3M trading volume, 90+ active traders, 4 exchange partners. Please keep these honest and up to date.

### Settings block (bottom of the file)

Look for the `// ===== EDIT ME =====` block inside `<script>`:

```js
const LOGO_SRC = "...";            // logo (URL or data: URI)
const CONTACT_EMAIL = "...";       // used by the Become a Partner button
const PARTNERS = [ ... ];          // partner cards
```

### Partners

Each partner is one entry:

```js
{ name:"Bitunix", url:"https://...", bg:"#121212", logo:"data:image/png;base64,..." }
```

| Field | Meaning |
|-------|---------|
| `name` | partner name (shown if no logo is set) |
| `url` | link the card opens (the referral link) |
| `bg` | colour of the plate behind the logo, so the logo's own background blends in |
| `logo` | the logo as a data URI |

To add a partner, copy an entry and change the fields. The grid adjusts automatically.

> **Tip:** to turn a logo file into a data URI, run
> `base64 -w0 logo.png` and prefix the result with `data:image/png;base64,`.

### Social links

Find `<div class="soc">` in the Contact section. Each button is a normal link:

```html
<a href="https://t.me/..." target="_blank" rel="noopener">Telegram</a>
```

Copy a line to add a platform, or delete a line to remove one.

---

## Join buttons

The nav **JOIN**, hero **JOIN COMMUNITY** and contact **JOIN TELEGRAM GROUP** buttons all open the Telegram group. To change the destination, search the HTML for `t.me/` and replace the link in those three places.

---

## Deploying

Because it's a single static file, any static host works. Upload the whole folder, keeping `assets/` next to the pages.

| Host | Steps |
|------|-------|
| **GitHub Pages** | Push to a repo, then *Settings → Pages → Deploy from branch* |
| **Netlify** | Drag and drop the folder onto the Netlify dashboard |
| **Cloudflare Pages** | Connect the repo or upload the folder directly |
| **Any web host** | Upload `index.html` to the `public_html` folder |

---

## Notes and responsible use

- **Referral links:** the partner links are affiliate/referral links and are marked `rel="sponsored"`. A short disclosure sits beneath the partner grid. Keep it, and check the disclosure rules in the regions you serve.
- **Risk warning:** trading carries risk. Nothing on this site is financial advice.
- **Partner logos:** logos belong to their owners (Gate, BingX, Sodex, Bitunix) and are shown to identify active partnerships. Check each exchange's brand guidelines. Higher-resolution or SVG versions from their press kits will look crisper.
- **Mascot artwork:** the current mascot resembles well-known cartoon characters. Before scaling commercially, consider an original mascot to avoid copyright or trademark trouble.
- **Fonts:** Orbitron and Inter are loaded from Google Fonts, with system fallbacks if they're blocked.

---

## Roadmap ideas

- Higher-resolution partner logos, and a full Sodex wordmark
- Instagram or Discord buttons (when the accounts exist)
- A short "How it works" or "Learning path" section
- Community events or schedule

---

## Contact

📧 msingicryptoacademy@gmail.com

📲 [Telegram](https://t.me/+tEVLXfkrP6xmNzE0) • [WhatsApp](https://chat.whatsapp.com/EQC607C13TV0hNvsHeAzt8) • [YouTube](https://www.youtube.com/@MSINGIACADEMY) • [X](https://x.com/msingiacademy)

---

© Msingi Traders Den. All rights reserved.

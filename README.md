# Free HTML accounting firm website template with GSAP scroll animations — Evenkeel

**One-page website for an accounting and bookkeeping firm that works for small businesses: a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02)

**[Live demo](https://8bsite.github.io/accounting-firm-website-template/)** · **[Use this template](https://github.com/new?template_name=accounting-firm-website-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/accounting-firm-website-template/archive/refs/heads/main.zip)**

<a href="https://8bsite.github.io/accounting-firm-website-template/"><img src="previews/desktop.png" alt="Evenkeel, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/accounting-firm-website-template/"><img src="previews/phone.png" alt="Evenkeel, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/accounting-firm-website-template/"><img src="previews/scroll.gif" alt="Evenkeel, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page site for a small firm of accountants in Bristol: services, a month of work, clients, fixed fees, team, reviews and a booking form. Swiss and strict: black type on white hung on one hairline rule like a ledger, a turning sphere of client cards, a month drawn as a ruler with a red marker, and the brand's two halves meeting in the footer.

Good for: accounting or bookkeeping firm; tax adviser or payroll bureau; small professional practice with fixed fees (lawyer, consultant, financial planner); any service business that wants a calm, typographic, black-and-white look. Free for personal and commercial use (MIT), made by [8B](https://8b.com/).

## Quick start

Pick one:

- **With an AI coding agent** (Claude Code, Codex, Cursor, Windsurf…). Download the files into your project (in Windows PowerShell type `curl.exe`):
  ```bash
  curl -LO https://raw.githubusercontent.com/8bsite/accounting-firm-website-template/main/index.html
  curl -LO https://raw.githubusercontent.com/8bsite/accounting-firm-website-template/main/AGENTS.md
  curl -LO https://raw.githubusercontent.com/8bsite/accounting-firm-website-template/main/LICENSE
  curl -LO https://raw.githubusercontent.com/8bsite/accounting-firm-website-template/main/CREDITS.md
  ```
  Then give your agent this prompt:
  ```text
  Read AGENTS.md, then edit index.html. Use this template as the base for a website for <your firm: what you do (accounts, tax, payroll…), for whom, where, your fees, opening hours and how clients book a call>. Keep the layout, the motion and the single-file format; replace the brand name, copy, client list, team, reviews, prices, photos, links and contacts, adapt the UK tax terms to your country, and recolour it through the CSS variables if needed.
  ```
  Give the agent the downloaded file, not a link: an agent reads a link as a summary and would rebuild a different page.
- **No code.** Download the ZIP, unzip it, replace the contacts and texts in `index.html`, put `index.html` into an empty folder and drag that folder onto [Netlify Drop](https://app.netlify.com/drop). The page is online in a minute.
- **On GitHub.** Click **[Use this template](https://github.com/new?template_name=accounting-firm-website-template&template_owner=8bsite)** to get your own copy, then **Settings → Pages → Deploy from a branch → main**. Your site appears at `https://<you>.github.io/<repo>/`.

## What's on the page

- **Navigation** — round logo mark top-left and a Menu button; full-screen menu with section links, address and phone
- **Evenkeel Accountants** — two screens: big type hung on a vertical hairline rule with a booking button, then a black screen with a statement, a paragraph and four photos
- **Four things we keep for you.** — ledger of four services: what the client sends left of the rule, what the firm returns right of it, how often
- **A month on the books** — a month drawn as a ruler: a red marker sweeps across and four dated tasks turn from grey to black
- **Clients since 2009** — turning 3D sphere of 28 client cards (names and photos) between the two halves of the title
- **Fixed fees, paid monthly.** — fee table: four plans in hairline rows with who each is for, what is included and the monthly fee
- **Moving to us takes one afternoon.** — three steps of moving from another accountant, each tile completing with a closing red ring
- **Four people, one desk.** — four team portraits with names, roles and one line each
- **Principle** — one large staggered quote on the rule, ending in a red full stop
- **Questions we hear every week.** — questions and answers (native &lt;details&gt;)
- **What our clients say.** — four client reviews on sheets that stack as you scroll
- **Book a free first call.** — opening hours set large in brackets with a small photo, phone, email, address and a call-booking form (placeholders)
- **Footer** — tagline, links, call/email/map icons, the full-width wordmark in two halves, copyright and the Design: 8B credit

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, phone, email, form, map) and the invented demo facts — prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The contact form does not send anything yet: connect it to a form service (Formspree, Netlify Forms) or remove it; [AGENTS.md](AGENTS.md) shows both.

## Customize

- **Colours and fonts**: CSS variables in the `:root` block at the top of `<head>`.
- **Text**: edit it in place.
- **Photos**: replace `src`, delete `srcset` and `sizes` (they list Unsplash sizes) and update the `alt` texts.
- **Animations**: each section's animation is one `<script data-8b-part="scene:<id>">` block at the end of the file. For native scroll, delete the Lenis block in `page-init`.

## For developers

- **Stack.** HTML and CSS (custom properties, cascade layers) with GSAP 3.13.0, ScrollTrigger, Lenis 1.3.27 from jsDelivr. No build step, no framework, no npm. 86 KB.
- **Layout of the file.** `<head>`: CSS variables, shared classes, then one style block per section. Then the markup, one element per section with a one-line comment above it. End of `<body>`: small behaviour scripts, the libraries, smooth scroll (`page-init`), the effects, one animation script per section.
- **Browsers.** Chrome and Edge 108+, Safari 15.4+, Firefox 121+ (it uses :has(), cascade layers, small/dynamic viewport units).
- **Accessibility.** Motion runs only when the visitor's system allows it; with "reduce motion" the page is complete and still. FAQ answers use native `<details>` and open without JavaScript. Every photo has alt text.
- **External requests.** fonts.gstatic.com, images.unsplash.com, cdn.jsdelivr.net. No analytics, no cookies. To self-host everything (offline use, or Google Fonts and GDPR in the EU), download those files and change the URLs.
- **Licences of the parts.** GSAP is free, commercial use included, under its own standard licence (not MIT); Lenis is MIT; fonts are SIL OFL; photos are under the Unsplash License. See [CREDITS.md](CREDITS.md).

## FAQ

**Can I use it for a client or a commercial site?** Yes. The code is MIT: use it, change it, sell the site you build with it.

**Do I have to keep the "Design: 8B" link?** No. It is welcome, not required.

**Can I use it in React, Next.js, Astro or Vue?** Yes. Move each section's markup and style block into a component and run its animation script in `useGSAP()` (React) or `onMounted` (Vue); start Lenis once. Or keep it as a separate static landing page next to your app (`example.com` for the landing, `app.example.com` for the app).

**Why doesn't the contact form send?** It is a demo. Connect it to Formspree, Netlify Forms or your backend; AGENTS.md has the steps.

**Where are the photos from?** Unsplash; they load from Unsplash's servers. Replace them with your own when you can.

## More free templates

[More 8B templates on GitHub](https://github.com/8bsite) · [8b.com](https://8b.com/)

## License

The template code is MIT licensed — see [LICENSE](LICENSE). Photos, fonts and libraries keep their own licences — see [CREDITS.md](CREDITS.md).

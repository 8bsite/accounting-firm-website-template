# Evenkeel — notes for AI coding agents

One HTML file: markup, inline CSS and inline scripts; GSAP with ScrollTrigger, Lenis smooth scroll, all from jsDelivr. No build step, no framework.

## Files
Work from the files: a page read through a link comes back as a summary, and a page rebuilt from it would differ.
```bash
curl -LO https://raw.githubusercontent.com/8bsite/accounting-firm-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/accounting-firm-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/accounting-firm-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/accounting-firm-website-template/main/CREDITS.md
```
In Windows PowerShell type `curl.exe`. Publish `index.html` with LICENSE and CREDITS.md; this file, README.md and `previews/` are not part of the site.

## Do not break
- Keep it one file unless the user asks otherwise; no framework or bundler for copy, colour or photo changes.
- Keep the ids and the `data-8b-section` / `data-8b-motion` attributes. Each section has its styles in `<style data-8b-part="section:<id>">` and its animation, if any, in `<script data-8b-part="scene:<id>">`.
- The scripts find these classes and attributes; when you change a section's markup, keep them or update the script:
  - `section-script:nav`: `.nav__menu` `.menu__close`
  - `section-script:opening`: `.op-level`
  - `section-script:contact`: `.ct-form` `.ct-thanks`
  - `scene:opening`: `.op-two` `.op-rule` `.op-one` `.op-a` `.ln__i` `.op-h1` `.op-sub` `.l-b` `.op-say` `.l-a` `.op-tile` `.op-para`
  - `scene:month`: `.mo-board` `.mo-fill` `.mo-marker` `.mo-task`
  - `scene:clients`: `.cl-title` `.cl-globe` `.cl-half--a` `.cl-half--b`
  - `scene:switch`: `.sw-tile` `.sw-ring__arc`
  - `scene:team`: `.tm-row` `.tm-card`
  - `scene:principle`: `.pc-l` `.pc-dot`
  - `scene:reviews`: `.rv-stack` `.rv-sheet`
  - `scene:footer`: `.ft-word` `.ft-a` `.ft-b` `.ghost__a` `.ghost__b`
- Colours, fonts, radii and shadows are CSS variables in the `:root` block (`data-8b-part="tokens"`); change them there and keep body text at 4.5:1 contrast or more.
- Animations run only when the visitor allows motion (`prefers-reduced-motion: no-preference`); the page must stay readable without them.
- Keep the header comment and `<meta name="generator">`; the "Design: 8B" footer link is optional.

## Replace before publishing
- Everything marked `data-8b-placeholder` (og-image, favicon, phone, email, form, map); remove the attribute once the real value is in. With no real value: no preview image — delete the `og:image` tag and set `twitter:card` to `summary`; no phone, email or address — remove that link or row.
- Book a free call button in the first screen: link to #contact now; point them to your booking calendar URL (Calendly, Cal.com) if you take bookings there, or keep it on the contact form.
- The map icon in the footer: link to an OpenStreetMap search for Bristol now; point them to the map URL of your office.
- **The form sends nothing.** `section-script:contact` checks the fields and shows a thank-you message without sending. Pick one:
  - Formspree: set `action="https://formspree.io/f/<id>"` on the form; in the script, before the thank-you message, `await fetch(form.action, { method: 'POST', body: new FormData(form), headers: { Accept: 'application/json' } })` and show it only if the response is ok.
  - Netlify Forms (site on Netlify): add `name="contact" data-netlify="true"` and `<input type="hidden" name="form-name" value="contact">`; send with `fetch('/', { method: 'POST', headers: { 'Content-Type': 'application/x-www-form-urlencoded' }, body: new URLSearchParams(new FormData(form)) })`.
  - No form service: remove the `<form>` together with the script that handles it (it would fail without the form) and keep the email link.
- Invented demo facts (ask the user for the real ones; do not make up prices, dates or addresses):
  - Founding year and size: "since 2009" (opening caption, clients title, team, principle caption), "Accountants to 340 small firms" / "340 shops, studios and trades" / "340 businesses" (opening, clients note, meta description).
  - Promises in the meta description: "Fixed monthly fees, one named accountant, every deadline met."
  - Fees: Sole trader £60 a month, Small company £140 (limited companies up to £500k turnover, payroll for up to five), Growing team £260 (payroll for up to twenty-five, a monthly call), Catch-up from £480 once; "Prices exclude VAT. No set-up fee and no notice period" (prices, FAQ "Can I leave?").
  - Service promises and deadlines: report "you can read in two minutes", self-assessment "filed by December", hours "by the 20th", payroll "on the same day every month", questionnaire "in month eleven", accounts "signed off a month before the deadline" (services).
  - The monthly schedule: Day 1, Day 8, Day 15, Day 22 (month) and "On the 22nd I get one page" (reviews).
  - Switching: "takes one afternoon", letter "signed on your phone in a minute", feeds "linked by the end of the day" (switch); "Most clients join mid-year", books up to date "in the first month", one named accountant with a direct number (FAQ).
  - UK-specific terms: HMRC, VAT, Making Tax Digital, self-assessment, corporation tax, statutory accounts (services, prices, FAQ, team): change them for another country.
  - Client list: 18 invented businesses on the sphere (Hollis & Daughter, Marlow Cycles, Fern Street Flowers, Quayside Barbers, Kiln Lane Pottery, Albion Books, Second Shot, Redland Motors, Pressed, Northfield Hardware, Totterdown Physio, Cole & Pike, Harbour Yoga, Little Wren, Halfpenny Deli, Linden Opticians, Gable Roofing, Southville Vets) and the stock photos captioned as client businesses (clients).
  - People: Maya Lindqvist (founder, chartered accountant, "started Evenkeel in 2009 with two clients"), Tom Hale ("nineteen hundred payslips a month"), Ann Whitcombe ("thirty years of self-assessment"), Sami Rahman; the portraits are stock photos (team).
  - Reviews: Priya Nair (Fern Street Flowers, "three years in"), Dan Cole (Cole & Pike Joinery, "four thousand pounds of expenses", "filed a month early"), Lewis Marsh (Redland Motors), Hana Wells (Second Shot Coffee, "payroll for nine people") (reviews).
  - Hours and place: 08:30–17:30, Monday to Friday, "1 Example Street, Bristol BS1 0ZZ" (contact, menu), the photo captioned "our office door" (contact).
  - Service: "Twenty minutes, free" first call (contact) and "we will call you within one working day" (the form's thank-you line).
  - Footer: "© 2026 Evenkeel Accountants Ltd · Company no. 00000000" — put in your legal name and registration number.
- `<title>`, the meta description and the og tags; photos (Unsplash, see CREDITS.md) when the user has their own.

## Notes
- The spirit-level vial, the logo mark, the vertical rule and the rings in the switch section are CSS and SVG, not images: recolour them through the CSS variables.
- Client cards sit on the sphere by their inline --lat and --lon angles. To add a card, give it its own pair (spread them evenly); a card without them sits on the pole on top of another.
- The brand name is split in two halves in two places: the footer wordmark (.ft-a, .ft-b; its style="--len:8" is the number of characters of the whole word and sizes it to fill the width) and the grey corner halves (.ghost__a, .ghost__b). Split your name the same way, or put the whole name in the first half and leave the second empty.
- Lighthouse lists gsap and ScrollTrigger as render-blocking; they sit at the end of body and the motion scripts after them need them loaded.
- Without JavaScript the Menu button cannot open the overlay; the footer links stay reachable.
- The grey corner halves are mid grey (about 3.2:1 on white) so they stay visible; they sit behind the content.
- Review sheets keep some empty space under short quotes, so the stack keeps its rhythm.

## Common edits
- Rebrand: search the old name (`Evenkeel`) in any letter case and replace every match; change the favicon letter and colours in `<link rel="icon">`.
- Photos: replace `src` and delete `srcset` and `sizes` (they list Unsplash sizes), keep `width`/`height` to the new photo's ratio, update `alt` and CREDITS.md.
- Remove a section: delete its markup, its `section:<id>` and `scene-style:<id>` styles, its `scene:<id>` and `section-script:<id>` scripts, and links to `#<id>`.
- Native scroll instead of smooth scroll: delete the Lenis block in `page-init` and the Lenis `<script>` tag.

## Check and publish
- Open the page at 375 and 1440 px, with reduced motion on, with the console open.
- Search `data-8b-placeholder` and the old name: nothing should be left but class names.

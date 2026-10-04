# BookIt Website — Claude Context

Static marketing / support site for the BookIt iOS app (source: `../bookit`).
To be published as GitHub repo **BookIt-Website** with GitHub Pages →
https://azbarks.github.io/BookIt-Website — `../app_web/apps.html` links to `help.html`,
so keep that repo name and `help.html` filename.
Same structure as the GrillIt (`../grillIt_website`), PrayIt (`../prayer_website`) and
RememberIt sites — plain HTML + one shared `style.css`, no build step, no JavaScript.

## Pages
- `index.html` — hero (phone mockup of the Library tab), trust bar, feature grid, how-it-works, iCloud band
- `help.html` — full guide, sidebar of sections; keep in sync with the app's behavior
- `privacy.html` — App Store privacy-policy URL
- `support.html` — App Store support URL (email azbarks@gmail.com)
- `style.css` — tokens + nav/footer/buttons. Colors from the app icon: navy `#0F2A5E`
  (nav, icon background) and the app's brown accent `#8A5A2B`; Bitter (headings) +
  Source Sans 3. Light + dark. Token names (`--ember`, `--flame`) are kept from the GrillIt
  stylesheet so the page styles copy across unchanged.
- `images/` — `icon.png` (256), `favicon.png` (64), `apple-touch-icon.png` (180), all
  resized from `../bookit/BookIt/Assets.xcassets/AppIcon.appiconset/bookit.png`

## At release (TODO)
- `index.html` `#download`: swap the "Coming soon" badge for the real App Store button
  (commented template is right there), and change the hero tag to "Available now on the App Store".

## Keep accurate
- **Privacy page must match the app.** BookIt's only network call is **Scan Barcode**:
  the ISBN goes to Open Library, then Google Books as a fallback (no key, nothing else sent).
  **Scan Cover** is on-device Vision OCR — nothing leaves the phone, the image isn't saved.
  Permission: camera only. If the app adds any network call or permission, update
  `privacy.html` — and the App Store privacy labels.
- Help describes: the five statuses (On the Shelf / Want to Read / Reading / Finished /
  Gave Up) and the per-status buttons on a book's page, Library scopes + per-scope sort,
  Want to Read swipe-to-Start, Stats sections, "I have a date" toggles, Read It Again /
  Log a Past Read / ×N badge, Ownership + Source, Archive + Show Archived, CSV import
  columns + synonyms (mirror `CSVColumnGuideView.swift`), Delete-All-then-import for edits,
  JSON backup merge-by-id, export filenames `yyyy-MM-dd_HHmm_BookIt_Backup.json` / `_Books.csv`.

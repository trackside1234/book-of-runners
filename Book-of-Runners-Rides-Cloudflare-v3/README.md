# Book of Runners & Rides v3 — LF + FF

Single-file Cloudflare Worker; no npm install, build step, KV or assets binding.

Choose **FF — Full Page** (`FF_BookOfRides_1_Page`) or **LF — Compact** (`LF_FixedOdds`) in the app before exporting. Both use the supplied Trio template files and retain the same TAB race scanning, jockey/trainer collation and editable runner/price list. Six runner slots are populated per graphic; books are split into additional graphics by venue.

Deploy by replacing `worker.js` in your GitHub repository. Keep your existing command:
`npx wrangler deploy worker.js --name book-of-runners --compatibility-date=2026-11-18`

Test both output formats in Viz Trio before production use.

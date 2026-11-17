# Book of Runners & Rides — Cloudflare Dashboard Edition

This edition is a **single Cloudflare Worker file**. It does not require npm, Node.js, Wrangler, a build process, an assets binding, or KV storage.

## Deploy directly in Cloudflare

1. Open the Cloudflare dashboard.
2. Go to **Workers & Pages** → **Create** → **Create Worker**.
3. Give it a name, e.g. `book-of-runners-rides`.
4. Choose **Edit code**.
5. Replace the starter code with the complete contents of `worker.js`.
6. Select **Deploy**.
7. Open the Worker URL.

The HTML interface, supplied Viz Trio XML template, and TAB API proxy are all embedded in `worker.js`.

## What it does

- Loads NZ, Australian, or combined thoroughbred race programmes for a selected date.
- Scans selected races through the TAB API.
- Lets you choose a jockey (Book of Rides) or trainer (Book of Runners).
- Collates their runners, allows editing of headings, runner text, and fixed-win prices.
- Exports the supplied Viz Trio `LF_FixedOdds` XML format.
- Keeps all editing in the browser; no database or secrets are configured.

## Notes

- This uses the TAB affiliate racing API endpoints from the source project. Access and response shape depend on the API.
- Fixed-win odds may be missing from some event responses; verify and edit them before export.
- Test the generated XML in Viz Trio before using it on air.
- The supplied template's show GUID and `LF_FixedOdds` master-template reference are retained.

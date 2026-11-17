# Book of Runners & Rides — Cloudflare Worker v4

This is the updated single-file Cloudflare Worker. It retains the existing deployment approach and adds the corrected Full Page associated-person field:

- Jockey book: the Full Page `Trainer` data column receives each runner's trainer.
- Trainer book: the Full Page `Jockey` data column receives each runner's jockey.

The supplied Viz Trio Full Page XML template exposes runner fields 201–204, with field 204 holding the associated person's name. The visible column heading is not exposed as a separate field in the supplied XML, so changing that heading between Trainer and Jockey requires a corresponding change to the Viz Trio graphic/template (or a template that exposes a heading field).

Deploy from the repository root containing `worker.js` using:

```bash
npx wrangler deploy worker.js --name book-of-runners --compatibility-date=2026-11-18
```

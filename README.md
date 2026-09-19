# Lucky Stars public data

Public, machine-readable records for the [Lucky Stars Family](https://github.com/fahimc/lucky-stars-family) rewards app.

## Privacy boundary

This repository intentionally contains only opaque family/child/ticket IDs, earned dates, ticket numbers, draw numbers, timestamps, match counts, and reward values. Multiple tickets may share the same earned date. Never commit names, email addresses, passwords, access tokens, notes about children, or any other personal data.

Files in `families/` follow `schema/family-data.schema.json`. Writes come from the app's authenticated Netlify Function, which requires a linked parent account and validates the payload before using a repository-scoped GitHub token.

The demo record is synthetic and may be reset at any time.

## Current draw rules

Tickets contain 4 unique numbers from 1–12. Friday draws reveal 4 main numbers and one Lucky Ball. The chance of any reward is 285 in 495 (about 57.6%); matching all 4 main numbers for the £10 reward is 1 in 495.

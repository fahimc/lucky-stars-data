# Lucky Stars public data

Public, machine-readable records for the [Lucky Stars Family](https://github.com/fahimc/lucky-stars-family) rewards app.

## Privacy boundary

This repository intentionally contains only opaque family/child/ticket IDs, earned dates, ticket numbers, draw numbers, timestamps, match counts, and reward values. Multiple tickets may share the same earned date. Never commit names, email addresses, passwords, access tokens, notes about children, or any other personal data.

Files in `families/` follow `schema/family-data.schema.json`. The app writes validated anonymous lottery state to a site-wide Netlify store. The `Sync family data` workflow copies the latest public record into `families/demo-family.json` every five minutes and can also be run manually. It commits with GitHub's built-in workflow token, so the app does not need a personal GitHub token.

The demo record is synthetic and may be reset at any time.

## Current draw rules

Tickets contain 4 unique numbers from 1–12 plus a Jackpot Star from 1–10. Friday draws reveal 4 main numbers, one Lucky Ball, and one Jackpot Star. The chance of any reward is 34 in 55 (about 61.8%); matching the Jackpot Star or all 4 main numbers gives a £10 chance of 28 in 275 (about 10.18%, or 1 in 9.82).

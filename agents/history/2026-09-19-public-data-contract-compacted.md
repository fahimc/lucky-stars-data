# Lucky Stars public data contract

## Purpose

Public, non-sensitive data repository for the Lucky Stars Family static PWA.

## Decisions

- `config/lottery.json` is the public reward configuration and odds record.
- Schema v2 stores a `tickets` array with opaque ticket IDs, earned dates, numbers, and issue timestamps. Multiple tickets can share an earned date and individual tickets may be revoked before the draw.
- Draw records store one shared draw, per-ticket outcomes, and the total reward.
- `schema/family-data.schema.json` documents the JSON contract.
- Names, emails, credentials, tokens, and free-text notes are prohibited.
- Production writes are accepted by the app's Netlify Function after strict family/payload validation and persisted in a site-wide Netlify Blobs store. Login is an identity selector, not a security boundary, by explicit product decision.
- `.github/workflows/sync-family-data.yml` mirrors the latest public Netlify record into `families/demo-family.json` every five minutes using GitHub's built-in workflow token; no personal GitHub token or repository secret is required.
- Current rules use 4 unique ticket numbers from 1–12, a 1–10 Jackpot Star, 4 main draw numbers, one Lucky Ball, and one drawn Jackpot Star. Any-prize odds are 34/55 (~61.8%); the £10 top-prize odds are 28/275 (~10.18%, 1 in 9.82).

## Current state

- Synthetic `families/demo-family.json` exists for connectivity and schema checks.
- The schema and app-side Netlify validator both cap stored numbers at 12.
- Schema-v2 records accept optional 1–10 `jackpotStar` and `jackpotMatch` fields for backward compatibility; all newly issued tickets and draws include them.
- The repository is intended to remain public.

## Resume point

Schema v2 is published at `fahimc/lucky-stars-data`. Keep the app validator, this JSON Schema, and the demo record aligned when ticket or draw fields change.

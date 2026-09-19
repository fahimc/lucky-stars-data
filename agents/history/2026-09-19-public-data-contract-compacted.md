# Lucky Stars public data contract

## Purpose

Public, non-sensitive data repository for the Lucky Stars Family static PWA.

## Decisions

- `config/lottery.json` is the public reward configuration and odds record.
- Schema v2 stores a `tickets` array with opaque ticket IDs, earned dates, numbers, and issue timestamps. Multiple tickets can share an earned date and individual tickets may be revoked before the draw.
- Draw records store one shared draw, per-ticket outcomes, and the total reward.
- `schema/family-data.schema.json` documents the JSON contract.
- Names, emails, credentials, tokens, and free-text notes are prohibited.
- Production writes are performed only by the app repository's authenticated Netlify Function after parent-role and payload validation.

## Current state

- Synthetic `families/demo-family.json` exists for connectivity and schema checks.
- The repository is intended to remain public.

## Resume point

Schema v2 is published at `fahimc/lucky-stars-data`. Keep the app validator, this JSON Schema, and the demo record aligned when ticket or draw fields change.

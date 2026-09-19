# Lucky Stars public data contract

## Purpose

Public, non-sensitive data repository for the Lucky Stars Family static PWA.

## Decisions

- `config/lottery.json` is the public reward configuration and odds record.
- `families/<opaque-family-id>.json` stores only opaque IDs, ticket/draw numbers, timestamps, match counts, and rewards.
- `schema/family-data.schema.json` documents the JSON contract.
- Names, emails, credentials, tokens, and free-text notes are prohibited.
- Production writes are performed only by the app repository's authenticated Netlify Function after parent-role and payload validation.

## Current state

- Synthetic `families/demo-family.json` exists for connectivity and schema checks.
- The repository is intended to remain public.

## Resume point

Publish to `fahimc/lucky-stars-data`, then configure the app's raw URL and Netlify's repository-scoped write token.

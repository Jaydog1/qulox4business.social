# Qulox + Z-Wolf

A polished, responsive front-end prototype for the dual-platform media system:

- `/` — Qulox creator-first social hub and business conversion landing experience.
- `/zwolf.tv` — visually separate premium VOD experience.
- `/admin` — front-end-only content control center mockup.

## Architecture notes

The requested production boundary should be implemented server-side, not trusted to this static demo:

- `user_content`: public creator uploads only.
- `zwolf_premium_catalog`: admin/distributor ingest only.
- Enforce ownership and roles using Supabase Row Level Security policies and server-side Edge Functions.
- Keep signed playback URLs and DRM license URLs out of client-visible catalog writes.
- Add a DMCA report relation linked to `user_content`, moderation queues, repeat-infringer enforcement, and audit logs.
- Add COPPA/mixed-audience age gating, parental consent, private-by-default minor profiles, and location minimization before production launch.

## Run locally

Serve this directory with any static server, for example:

```bash
npx serve .
```

This commit intentionally contains no secrets, OAuth credentials, SMTP keys, or passwords.

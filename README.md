# ConectaGrupos — Ready-to-Deploy Build

WhatsApp group directory (Spanish market) — Next.js 16 App Router + MariaDB (mysql2/promise pool) + Tailwind 4 + shadcn/ui + zustand + framer-motion. Teal/emerald theme, light/dark mode, fully responsive.

## Latest build (2026-10-08 QA pass)

`conectagrupos-ready-to-deploy-2026-10-08-qa.zip` — includes the sitewide QA round:

- **Verify-page related groups**: most-recent groups from the SAME category, always within the same content silo (adult ↔ adult, clean ↔ clean). RTA-5042 label on adult verify pages.
- **Adult-content safety (clean-by-default)**: random-group button, recent-groups feed, and related-groups API no longer serve adult rows to clean surfaces.
- **Anti-abuse**: ratings identified per-IP (one review per group per IP, updates in place) + 15/h rate limit; share counter rate-limited 5/h; image proxy serves images only + nosniff.
- **SEO**: RSS autodiscovery (`<link rel="alternate">`) + footer feed link; og:image / twitter:image on every page; out-of-range `?page=N` URLs 307-redirect to the clamped canonical; SERP-safe titles and meta description lengths; JSON-LD XSS-hardened serializer.
- **UX/mobile**: header icon touch targets 44px on mobile; verify-page breadcrumb 404 fixed.
- 16 bugs fixed total; full verification log in `worklog.md` inside the project.

## Deploy

See `DEPLOYMENT.md` inside the zip (Hostinger VPS notes):
1. Unzip, `bun install`
2. Set env vars: `DB_HOST/DB_PORT/DB_USER/DB_PASSWORD/DB_NAME`, `ADMIN_USER`, `ADMIN_PASS`, `SESSION_SECRET`
3. `bun run build && bun start`
4. Schema self-creates on first request (idempotent schema guard in `src/lib/db.ts`).

Admin: `/admin` (credentials from `ADMIN_USER`/`ADMIN_PASS` env).

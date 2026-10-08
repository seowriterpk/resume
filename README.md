# ConectaGrupos — Ready to Deploy 🚀

**Tu directorio de grupos de WhatsApp en español** — production-ready package of the ConectaGrupos site (Next.js 16 + TypeScript + MariaDB).

📦 **Latest package:** `conectagrupos-ready-to-deploy-2026-10-08.zip`

## What's inside the zip

| Path | Contents |
|---|---|
| `src/` | Full application source (App Router pages, APIs, components, libs) |
| `public/` | Static assets (icons, robots, manifest) |
| `scripts/` | MariaDB bootstrap (`setup-mariadb.sh`), seed data (`seed.sql`), date-stagger utility |
| `.env.example` | All required environment variables (DB, admin creds, session secret) |
| `package.json` / `bun.lock` | Dependencies (install with `bun install` or `npm install`) |
| `next.config.ts` etc. | TypeScript / ESLint / Tailwind / shadcn config |
| `DEPLOYMENT.md` | **Step-by-step Hostinger/VPS deployment guide** |
| `GROUPIZO_MANUAL.md`, `VIP_LOGIC.md` | Product & feature documentation |

## Quick start

```bash
unzip conectagrupos-ready-to-deploy-2026-10-08.zip -d conectagrupos
cd conectagrupos
bun install                 # or npm install
cp .env.example .env        # fill in DB_*, ADMIN_USER/PASS, SESSION_SECRET
bun run build && bun run start
```

The DB schema self-creates on first request; run `scripts/seed.sql` + `scripts/stagger-dates.py` for demo data.

## Highlights (Oct 8, 2026 build)

- 🟢 Launch-ready: 29 routes verified, 0 lint/tsc errors, clean console
- 🔞 Strict 18+ adult-content separation (clean-by-default, opt-in age gate)
- ⭐ Favorites, compare tool (footer + group-page entry points, no global popups), recently-viewed
- 🛠️ Admin panel: bulk tools, smart-suggest pickers, moderation, SEO overrides
- 📈 Movers/trending stats, daily view tracking
- 🌐 Sitemap, JSON-LD, cookie consent, mobile-first responsive

# NestIQ

**NestIQ** is an AI-assisted real estate intelligence platform focused on the Indian market (Mumbai-centric demo data). It combines a **Next.js 14** web app, a **FastAPI** backend, and **Supabase** (Postgres + optional local stack) for listings, legal/fraud signals, negotiations, and AI-powered tools (price estimation, chat, mediation, fair listing copy).

This repository’s application code lives under **`nestiq-core/`**.

## Features

- **Property discovery** — Search, maps (Leaflet), and detail pages with image galleries (Unsplash-backed URLs; invalid URLs are normalized client-side).
- **Fair price & signals** — RandomForest-style price model (see `nestiq-core/backend/data/mumbai_cleaned.csv`), fraud/legal context, and badges on cards.
- **AI (Gemini)** — Chat, sell advisor, mediation, and related endpoints when `GEMINI_API_KEY` is set.
- **Fair listing narrative (OpenRouter)** — Optional `POST /api/v1/ai/fair-description` when `OPENROUTER_API_KEY` is set.
- **Negotiations** — API + UI flows for buyer/seller negotiation with AI mediator support.
- **Scraper pipeline** — Optional scheduled ingest into Supabase (Housing-style sources, MahaRERA helpers); disabled if Supabase is not configured.
- **Utilities** — Image verification, deed/OCR-related endpoints (see OpenAPI docs).

## Repository layout

```text
nestiq-core/
  backend/          # FastAPI app (uvicorn entry: backend/main.py)
  frontend/         # Next.js 14 App Router
  supabase/         # Migrations + seed.sql for local/remote Supabase
```

## Prerequisites

- **Node.js** 18+ (for the frontend)
- **Python** 3.10+ (for the backend)
- **Supabase CLI** (optional, for local DB: `supabase start`)

## Configuration

### Backend (`nestiq-core/backend`)

1. Copy the example env file:

   ```bash
   cd nestiq-core/backend
   cp .env.example .env
   ```

2. Edit **`.env`**. At minimum, set **`GEMINI_API_KEY`** for AI routes. For database-backed properties and the scraper, set **`SUPABASE_URL`** and **`SUPABASE_SERVICE_ROLE_KEY`**. For fair-listing copy via OpenRouter, set **`OPENROUTER_API_KEY`** (see `.env.example` for optional model/referrer keys).

3. Never commit real API keys. **`.env.example`** must stay placeholder-only.

### Frontend (`nestiq-core/frontend`)

Create **`.env.local`** (not committed) with:

- **`NEXT_PUBLIC_API_URL`** — Backend base URL, e.g. `http://localhost:8000/api/v1`
- **`NEXT_PUBLIC_SUPABASE_URL`** and **`NEXT_PUBLIC_SUPABASE_ANON_KEY`** — If you use Supabase from the browser (auth/client queries)

Use the values printed by `supabase start` for local development.

## Database (Supabase)

From **`nestiq-core/supabase`**:

```bash
supabase start          # local stack
supabase db reset       # apply migrations + seed (when configured)
```

Migrations live in `supabase/migrations/`; sample data in `supabase/seed.sql`.

## Run locally

### 1. API server

```bash
cd nestiq-core/backend
python -m venv .venv
# Windows: .venv\Scripts\activate
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```

- **OpenAPI docs:** [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- **Health:** [http://127.0.0.1:8000/health](http://127.0.0.1:8000/health)

### 2. Web app

```bash
cd nestiq-core/frontend
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000). The dev server expects the API at the URL in **`NEXT_PUBLIC_API_URL`**.

### Scraper scheduler

If **`NESTIQ_SCRAPER_ENABLED`** is true (default) and Supabase is configured, the API starts a periodic scraper task. Set **`NESTIQ_SCRAPER_ENABLED=false`** to skip it. You can also trigger a run via **`POST /api/v1/scraper/trigger`** (see backend `app/main.py`).

## API surface (high level)

Routers are mounted under **`/api/v1`**:

| Area | Typical routes |
|------|------------------|
| Properties | `GET /properties`, property by id |
| Price | Price estimation endpoints |
| AI | Chat, sell advisor, fair description, etc. |
| Mediation | Buyer/seller mediation |
| Negotiations | Negotiation CRUD / flows |
| Image / deed | Verification and deed-related utilities |

Use **`/docs`** for the authoritative list of paths and request bodies.

## Tech stack

| Layer | Stack |
|-------|--------|
| Frontend | Next.js 14, React 18, Tailwind CSS, Framer Motion, Leaflet, Supabase JS client |
| Backend | FastAPI, Pydantic, scikit-learn, pandas, Google GenAI (Gemini), httpx, Supabase Python client |
| Data | Supabase Postgres + SQL migrations |

## Scripts

| Location | Command | Purpose |
|----------|---------|---------|
| `nestiq-core/frontend` | `npm run dev` | Next.js dev server |
| `nestiq-core/frontend` | `npm run build` | Production build |
| `nestiq-core/backend` | `uvicorn main:app --reload` | API with hot reload |

## Troubleshooting

- **CORS** — Backend allows `http://localhost:3000` and `http://127.0.0.1:3000` by default (`app/core/config.py`). Add origins there if you use another host/port.
- **Images broken in UI** — Use full Unsplash photo URLs (path must include the id **and** hash segment). The frontend normalizes bad Unsplash URLs to safe defaults when mapping API data.
- **Scraper not running** — Confirm `SUPABASE_SERVICE_ROLE_KEY` (and URL) are set; check logs on startup.

## Additional docs

- **`nestiq-core/frontend/README.md`** — Frontend-specific notes and file layout (may be partially historical as the app grows).

---

*PCCE Avishkar / NestIQ — property intelligence with legal and pricing context.*

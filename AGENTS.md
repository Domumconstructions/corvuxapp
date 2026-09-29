# AGENTS.md

## Project Overview
Single-file static landing page for **Corvux** (SaaS for construction/industry management). No backend, no build step, no dependencies — just `index.html` with inline CSS and vanilla JS (Portuguese language). Only external resource is Google Fonts.

## Running the App
- Served via `docker-compose.base44.yml` using `nginx:alpine`, bind-mounting `index.html` into the container.
- `docker compose -f docker-compose.base44.yml up -d` — starts on port 3000.
- Healthcheck: `wget --spider http://localhost:80/` inside the container.
- No secrets, no env vars, no database required.

## Editing
- Edit `index.html` directly; changes appear on reload (nginx serves the mounted file, so a browser refresh is enough — call `reload_preview` to force the preview iframe to refresh).

# CLAUDE.md — dragon-portfolio

## Project Context

dragon-portfolio is a full-stack portfolio site: Vite + React Three Fiber frontend (deployed on GitHub Pages) and a Node/Express API backend (deployed on a Node host such as Render or Railway).

## Development Commands

```bash
npm ci                # install all dependencies
npm run dev           # start frontend + backend concurrently (ports 5173 + 8080)
npm run dev:client    # frontend only
npm run dev:server    # backend only
npm run build         # production Vite build
npm run lint          # ESLint
npm test              # Vitest unit tests (run once)
npm run test:coverage # coverage report
```

## Key Directories

- `src/` — React frontend (components, pages, hooks, utils, data, config)
- `server/` — Express API proxy (GitHub, Medium, Anthropic, EmailJS)
- `public/` — static assets
- `docs/` — architecture, outcomes, and deployment documentation

## Environment Variables

Copy `.env.example` to `.env` and fill in values. Never commit `.env`. Required for full functionality:
- `ANTHROPIC_API_KEY`, `ANTHROPIC_MODEL`, `ANTHROPIC_FAST_MODEL`
- `EMAILJS_PUBLIC_KEY`, `EMAILJS_SERVICE_ID`, `EMAILJS_TEMPLATE_ID`
- `GITHUB_USERNAME`, `GITHUB_TOKEN` (read-only, optional but recommended)
- `CORS_ORIGINS` (comma-separated; set to exact GitHub Pages origin in production)

## Code Style

- ESLint is enforced. Fix all warnings before committing.
- Keep components small and single-purpose.
- Use the existing `getCachedOrCompute` helper for all external API calls in the backend.
- Do not add client-side secrets. All third-party keys must remain in the Express server.

## Deployment Notes

- The Vite build is static and deployed via the `.github/workflows/pages.yml` GitHub Actions workflow.
- The backend is not deployed automatically; follow the README deploy steps for the Node API.
- Set `CORS_ORIGINS` to the GitHub Pages URL before deploying the backend to production.

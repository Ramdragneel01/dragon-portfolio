---
applyTo: "src/**/*.jsx"
---

# Config-Driven UI Guidance

- Source text, toggles, and section metadata from `src/config/siteConfig.js` instead of hardcoding in components.
- Keep sections declarative by using registry-style mappings in `src/App.jsx`.
- Prefer explicit component props (`config`, `apiBaseUrl`) over direct `import.meta.env` reads in leaf components.
- Route remote API interactions through backend endpoints (`/api/chat`, `/api/contact`).
- Keep UI interactions accessible: labels, semantic buttons, and `aria-live` feedback for async status.

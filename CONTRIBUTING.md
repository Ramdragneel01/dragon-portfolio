# Contributing

This is a personal portfolio project. External contributions are welcome for bug fixes,
accessibility improvements, and documentation corrections.

## Workflow

1. Fork the repository.
2. Create a feature branch: `git checkout -b fix/your-topic`.
3. Make the smallest change that addresses the issue.
4. Run the validation suite before opening a pull request:

   ```bash
   npm ci
   npm run lint
   npm test
   npm run build
   ```

5. Open a pull request against `main` with a concise title and description.

## What to Contribute

- Bug fixes and cross-browser compatibility improvements.
- Accessibility improvements (WCAG 2.1 AA targets).
- Documentation corrections or clarifications.
- Performance improvements with before/after measurements.

## What Not to Contribute

- Feature additions or design changes without prior discussion.
- Changes to the curated portfolio case studies or impact metrics.
- Dependency bumps without a justification note.

## Code Style

- ESLint is configured for this project. Fix all lint warnings before submitting.
- Keep commits small and focused. Each commit should pass lint and tests.

## Questions

Open a GitHub Discussion or email `ramprakashdhulipudi@gmail.com`.

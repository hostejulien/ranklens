# Commands

```bash
pnpm build        # Build all workspace packages
pnpm dev          # Dev mode across all packages
pnpm lint         # Lint all packages
pnpm typecheck    # TypeScript checking across all packages
```

Run single-package commands from the package directory, not the root — `pnpm -r` is slow for targeted work.

# Tooling

- Package manager is `pnpm` (v10). NEVER use npm or yarn.
- Monorepo: apps go in `apps/`, shared libs in `packages/`.
- Deployment target is Vercel — optimize for edge-compatible patterns.
- Use `pnpm add -w` for root-level dependencies, `pnpm add --filter <package>` for workspace packages.

# Code style

- Prefer linters and formatters over manual rules. Do not override what the linter enforces.
- TypeScript strict mode. No `any` unless explicitly justified with a comment.
- Use ES modules (`import/export`), not CommonJS.
- Prefer named exports over default exports.

# Git workflow

- Branch naming: `claude/<feature>-<id>` for AI-generated branches.
- Write concise commit messages focused on "why", not "what".
- Never commit `.env` files or secrets.

# Testing

- Always run the relevant test suite before considering a task done.
- Prefer running single-package tests over the full suite when possible.
- Write tests for edge cases, not just happy paths.

# Landmines

- The `.claude/get-shit-done/` directory is the GSD framework — do NOT modify files in it.
- `.turbo` is gitignored but may appear locally — don't reference it in code.
- When creating new workspace packages, always add the package to `pnpm-workspace.yaml` if the glob doesn't already match.

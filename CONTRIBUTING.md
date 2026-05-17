# Contributing to Calabash

Calabash is a local-first, manual case board for readers. Contributions are most useful when they protect that shape: no account system, no hosted reader database, no AI extraction or suspect ranking, and no unmarked story spoilers.

## Good Ways to Help

- Report reproducible bugs with the bug report issue form.
- Share beta reading-session feedback with the beta feedback form.
- Discuss early product ideas in GitHub Discussions before turning them into focused issues.
- Improve docs, translations, screenshots, preview cards, and README consistency.
- Contribute reusable `.calabash-template.json` files that contain original blank structure, not copyrighted story text.

## Local Development

The web app lives in `app/` and is expected to run on Node 24.

```bash
cd app
npm install
npm run dev
npm run typecheck
npm test
npm run build
```

For the desktop shell:

```bash
npm install
npm run desktop:dev
npm run desktop:build
```

Desktop builds require Rust and Tauri 2. Browser smoke tests and UI verification should use the local Playwright install from `app/node_modules/@playwright/test` when possible.

## Before Opening a Pull Request

- Keep changes scoped to the issue or discussion that motivated the work.
- Add or update tests when behavior changes.
- Run `cd app && npm run typecheck` and `cd app && npm test` for app changes.
- Run `cd app && npm run build` for production-impacting web changes.
- For public user-facing releases or updates, keep all READMEs in sync: `README.md`, `README.zh-CN.md`, `README.ja.md`, `README.es.md`, and `README.pt-BR.md`.
- Do not commit private reading notes, copyrighted story text, or unmarked spoilers.

## Product Fit

Calabash is for readers who want to do the detective work themselves. Strong proposals usually make manual note-taking clearer, safer, faster, or easier to resume after time away. Proposals that require cloud sync, accounts, server-side reader data, or AI-generated deductions are outside the current beta direction.

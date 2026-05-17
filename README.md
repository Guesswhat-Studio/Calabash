# Calabash

<p align="center">
  <img src="docs/assets/calabash-logo-detective-transparent.png" width="132" alt="Calabash detective pipe logo" />
</p>

> A spoiler-safe case board and relationship graph for mystery and detective fiction readers.

[Live demo](https://guesswhat-studio.github.io/Calabash/) · [Report an issue](https://github.com/Guesswhat-Studio/Calabash/issues/new/choose) · Version `0.5.2`

Languages: **English** · [简体中文](README.zh-CN.md) · [日本語](README.ja.md) · [Español](README.es.md) · [Português (Brasil)](README.pt-BR.md)

![Calabash private case board for reading mysteries](docs/assets/calabash-github-repo-card-en.png)

![Calabash spoiler-safe mystery reading notes and relationship board screenshot](docs/assets/calabash-demo.png)

## What It Is

Calabash is a local-first case-file board for tracking characters, aliases, clues, relationships, and theories while you read. It is named after Sherlock Holmes' calabash pipe: the tool does not solve the case for you, but it sits beside you while you think.

Use it as a mystery reading notes app, detective fiction relationship graph, clue tracker, or private case board for long novels, fair-play mysteries, manga cases, and puzzle competitions.

The current public demo runs entirely in the browser. There is no account system, no hosted reader database, and no server-side save file.

## No AI, By Design

Detective novels are not puzzles to outsource. They are puzzles to inhabit.

Calabash is deliberately manual. No AI extraction, no summaries, no automatic suspect ranking. Every character you add is someone you chose to notice; every relationship you draw is a hypothesis you are willing to test; every edge you change from suspected to confirmed is a small victory of attention.

## Highlights

- **Chapter slider**: move through the book and only see what you knew at that chapter.
- **Spoiler Shield**: cover reveal-heavy chapters until you choose to uncover them.
- **Character board**: track portraits, aliases, roles, occupations, introductions, and notes.
- **Board styles**: switch between compact text cards and large portrait case-file cards.
- **Relationship certainty**: mark connections as confirmed, suspected, or disproven.
- **Open text fields**: roles and relationship types are suggestions, not hard limits.
- **Sticky notes and groups**: keep clues near the board and draw colored group regions behind characters.
- **Illustrations**: pin floor plans, screenshots, and other visual references above or below the board.
- **Starter imports**: start a new book from a single-book JSON file, including an LLM-friendly template.
- **Local library**: save books in IndexedDB and back them up with Export/Import.
- **Built-in tutorials**: try *The Murder of Roger Ackroyd* or *Hida Trick House Murder Case*.
- **Multilingual UI**: English, Simplified Chinese, Japanese, Spanish, and Brazilian Portuguese.
- **Templates and chapter safety**: `v0.5.2` adds reusable book templates, current-book template export, GitHub preview cards, and guards chapter totals from shrinking below existing chapter content.

## Data And Privacy

Calabash is local-first:

- Your books are stored in your browser with IndexedDB.
- Theme, language, and onboarding preferences use localStorage.
- Other demo visitors cannot change your board, and you cannot change theirs.
- Clearing browser site data can delete your local library during beta.
- Use **Export Library** as your backup path and **Import Library** to move data to another browser.
- On desktop, full-library imports first create a local safety backup in the app data folder.

See [Privacy Policy](PRIVACY.md) for the full local-data and network-access statement.

## Quick Start

1. Open the [live demo](https://guesswhat-studio.github.io/Calabash/).
2. Choose the Ackroyd tutorial, the Kindaichi tutorial, or a blank book.
3. Press `N` to add a character.
4. Select a character, press `E`, then click another character to add a relationship.
5. Move the chapter slider as you read.
6. Export your library when you want a backup.

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `N` | New character |
| `E` | Connect edge from selected character |
| `F` | Fit board to view |
| `/` | Search |
| `Delete` / `Backspace` | Delete selected item |
| `Ctrl/Cmd + Z` | Undo |
| `Ctrl/Cmd + Shift + Z` | Redo |

## Who It Is For

Calabash is for readers who enjoy doing the detective work themselves:

- Classic mystery readers: Agatha Christie, Ellery Queen, John Dickson Carr, S. S. Van Dine.
- Manga and TV mystery fans tracking aliases, masked identities, and late reveals.
- Mystery puzzle and contest solvers who need a temporary case board for people, clues, locations, and hypotheses.
- Readers of character-dense fiction: fantasy, historical novels, family sagas, political thrillers.
- Anyone who wants a quiet, private, no-account tool for thinking with a story.

Calabash is not a book tracker, ebook reader, writing tool, AI summarizer, or social platform.

## Community

- Bugs, beta feedback, focused proposals, docs fixes, and template
  contributions: use the
  [issue chooser](https://github.com/Guesswhat-Studio/Calabash/issues/new/choose).
- Questions, setup help, early ideas, and show-and-tell posts: use
  [GitHub Discussions](https://github.com/Guesswhat-Studio/Calabash/discussions).
- Contribution setup and PR expectations: see
  [CONTRIBUTING.md](CONTRIBUTING.md).
- Security reports: follow [SECURITY.md](SECURITY.md) instead of opening a
  public issue.

## Development

The app lives in `app/` and runs as a Vite React project.

```bash
cd app
npm install
npm run dev       # http://localhost:5173
npm run typecheck # TypeScript check
npm test          # Vitest suite
npm run build     # production build
```

GitHub Pages build:

```bash
cd app
VITE_BASE_PATH=/Calabash/ npm run build
```

Desktop shell:

```bash
npm install
npm run desktop:dev
npm run desktop:build
```

Desktop builds require Rust and use the Tauri 2 shell in `src-tauri/`. The React app remains the single frontend for both web and desktop.

Release builds:

- Every public version should have an annotated `vX.Y.Z` tag and a GitHub Release.
- Pushing a `v*` tag runs the release workflow and uploads the web bundle.
- Starting with the `0.2` desktop shell, the same workflow also uploads unsigned plain Windows, Linux, and macOS desktop binaries.
- After all GitHub Release assets are ready, the workflow mirrors the latest release assets to CNB for domestic downloads while GitHub remains the full archive.

## Code Signing Policy

Calabash is preparing Windows desktop signing through the SignPath Foundation
open-source program. Free code signing provided by [SignPath.io](https://signpath.io),
certificate by [SignPath Foundation](https://signpath.org), for release artifacts
signed under the [Code Signing Policy](docs/CODE_SIGNING.md) after the project is
accepted into the program.

Optional local tutorial portraits:

```bash
cd app
npm run fetch:kindaichi-portraits
```

The public demo includes the Kindaichi tutorial portraits in `app/public/demo-portraits/`. The Ackroyd tutorial uses original generated case-file avatars.

## Roadmap

The product roadmap is intentionally not kept in the public repository. Public planning should live in [GitHub Projects](https://github.com/orgs/Guesswhat-Studio/projects); GitHub Issues are open for bugs, beta feedback, and feature proposals.

## Versioning

Calabash uses `0.x` beta versioning for now:

- `0.1.0`: first public web demo.
- `0.1.1`: public-facing repository cleanup, multilingual README split, issue templates, and beta docs polish.
- `0.1.2`: inspector localization polish and simplified character details panel.
- `0.1.3`: beta-readiness storage warnings, import/export fixture regression coverage, and release validation.
- `0.2.0`: desktop shell, cross-platform binary release setup, onboarding language selection, chapter-aware notes/groups, relationship rendering fixes, and adjustable board annotations.
- `0.2.1`: active update checks from Settings and single-book JSON imports for faster case setup.
- `0.2.2`: Japanese UI support, Japanese README/SEO metadata, and localized tutorial demo copy, especially the Kindaichi case.
- `0.3.0`: chapter-aware illustrations for floor plans/screenshots, clipboard paste, background layering, and the case-folder Settings redesign.
- `0.3.1`: compact toolbar fix so narrow boards keep the title and inspector toggle visible.
- `0.4.0`: desktop stability pass with native file dialogs, safety backups before full-library imports, and clearer import/export completion feedback.
- `0.5.0`: tablet-oriented interaction polish, effective board locking, duplicate case-title disambiguation, and smaller production chunks.
- `0.5.1`: iPad Safari safe-area fix for the bottom chapter slider and CNB release deployment coverage.
- `0.5.2`: reusable book templates, current-book template export, GitHub preview cards, and chapter-total guards for existing chapter content.

## License

MIT

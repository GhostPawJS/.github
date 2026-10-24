# Contributing to GhostPaw

Thanks for taking the time. This guide applies to every library in the GhostPawJS org: codex, questlog, affinity, souls, grimoire, email and telegram.

## Before you start

- For a bug, open an issue with the bug form first, ideally with a failing snippet.
- For a feature or an API change, open an issue with the feature form before writing code. Tool names, tool inputs and the public exports are contracts that agents depend on, so changes there are discussed first.
- Small fixes (typos, docs, an obvious bug with a test) can go straight to a pull request.

## Setup

You need Node.js 24 or newer; the libraries use the built-in `node:sqlite`. Each repo pins the exact version in `.nvmrc`, `mise.toml` and `.tool-versions`.

```bash
git clone https://github.com/GhostPawJS/<repo>.git
cd <repo>
npm ci
npm run check    # types, lint, tests, build and all guards
```

`npm run check` is the same gate CI runs. A pull request is ready for review when it passes locally.

## Conventions

- **Zero runtime dependencies.** Only Node.js built-ins at runtime. Dev dependencies are fine. `npm run check:deps` enforces this.
- **One function per file**, snake_case file names, tests next to the code as `*.test.ts`, run by Node's built-in test runner.
- **Formatting and lint** by Biome: `npm run lint:fix`.
- **Tool facade.** If you change a tool in `src/tools/`, update its `description`, `whenToUse`, `whenNotToUse` and input descriptions so an agent can still pick it correctly. `npm run check:api` fails when the public surface changes without an updated snapshot.
- **Changelog.** Add a line under `## [Unreleased]` in `CHANGELOG.md` for anything a user would notice.
- **Docs.** Keep `README.md` and `docs/` in sync with behaviour. Examples in docs should run as written.

## Pull requests

- Keep each pull request to one change. Small is easier to review and to revert.
- Pull requests are squash-merged; the title becomes the commit message, so write it as one.
- Releases are cut by the maintainer from `main` and published to npm with provenance by CI.

## Licence

By contributing you agree that your contribution is licensed under the MIT licence of the repository.

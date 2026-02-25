# AGENTS.md

## Cursor Cloud specific instructions

### Project overview

Hexo 4 static blog using the Minos theme. No backend, no database, no external services required.

### Node.js version

This project requires **Node.js 14** (`nvm use 14`). The `node-sass@4.14.1` dependency (used by `hexo-renderer-sass`) only has pre-built binaries for Node ≤14. Newer Node versions will fail during `npm install`.

### Key commands

See `package.json` scripts:
- `npm run build` — generate static site (`hexo generate`)
- `npm run server` — start dev server on port 4000 (`hexo server`)
- `npm run clean` — remove generated files (`hexo clean`)

### Gotchas

- The circular-dependency warnings about `lineno`/`column`/`filename` during build are harmless and come from `node-sass` internals on Node 14. They do not affect output.
- There is no linter or test suite configured in this project.
- The `cheerio` dependency must stay at `^1.0.0-rc.12` (not latest 1.x) because newer versions require Node ≥20, which is incompatible with `node-sass`.

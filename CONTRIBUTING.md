# Contributing to open-guide

Public Markdown library for Ai School workshops and how-tos.

This repo is **content only** (folders + Markdown). Structure matches **GitBook** conventions so the same tree can sync later:

| Convention | File |
|------------|------|
| Space / folder home | `README.md` |
| Sidebar | `SUMMARY.md` |
| GitBook config | `.gitbook.yaml` |

The VitePress site (private repo) reads this tree and maps each `README.md` to the folder URL.

## Layout

| Folder | What belongs here |
|--------|-------------------|
| `ai-building/` | Build loops, checklists, quality gates |
| `prompts/` | Copy-paste prompts |
| `partners/` | Partner quickstarts (e.g. Shipaton) |
| `examples/` | Worked product shapes |
| `events/` | Per-event public packs |

## Rules

- Name the main page in every folder `README.md` (not `index.md`).
- Write for participants and the public web.
- No internal ops, private QRs, mentor rosters, pricing, CRM, or unpublished strategy.
- Keep prompts in fenced `text` blocks.

## Contribute

1. Edit or add Markdown under the right folder.
2. If you add a page, also list it in `SUMMARY.md` (for GitBook).
3. Open a PR to `main`.

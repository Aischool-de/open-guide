# Open Guide

Public Markdown library for Ai School workshops and how-tos.

This repo is **content only** (folders + Markdown). The VitePress site that renders it lives in a separate private repository and reads this tree automatically (sidebar from folders, like GitBook).

## Layout

| Folder | What belongs here |
|--------|-------------------|
| `ai-building/` | Build loops, checklists, quality gates |
| `prompts/` | Copy-paste prompts |
| `partners/` | Partner quickstarts (e.g. Shipaton) |
| `examples/` | Worked product shapes |
| `events/` | Per-event public packs (agenda summaries, links) |

## Rules

- Write for participants and the public web.
- No internal ops, private QRs, mentor rosters, pricing, CRM, or unpublished strategy.
- Prefer topic-first paths; event folders only hold what is unique to that day.
- Keep prompts in fenced `text` blocks.

## Contribute

1. Edit or add Markdown under the right folder.
2. Open a PR to `main`.
3. The docs site picks up structure on the next deploy.

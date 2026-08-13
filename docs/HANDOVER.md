# Session handover — 2026-08-13

Valid while the open items below are unanswered. If you are reading this more
than two weeks on, check the open list against `git log` before trusting it.

This is a **backup snapshot** repo (built artifacts only, no source). The live
project it mirrors is `rfaleiros77/kkml-demo`, served from GitHub Pages. Both
share the same `origin` remote.

## Where the work stands

- **Operations Runbook v1.0 — done, verified, committed and pushed.**
  - Files: `tools/build_runbook.py` (source of truth) → `docs/OPERATIONS_RUNBOOK.docx` (generated).
  - Commit `9febdd0` on `main`, pushed to `origin` (`9761a31..9febdd0`).
  - Verified: script regenerates the .docx and prints all 9 section headings;
    live URL `https://rfaleiros77.github.io/kkml-demo/` returns HTTP 200;
    zero `*.map` / `*-dbg*` files in the working tree and in the published
    commit (this is the source-protection check, runbook section 4).
- Nothing in progress. Working tree clean except an untracked `.DS_Store`
  (ignored noise, not committed).

## Decisions and their reasons

- **Runbook lives in the backup repo, not a separate active repo.** The backup
  and the live site are the *same* GitHub repo (`kkml-demo`), so committing here
  already puts the runbook in the real repo. No second location needed.
- **No CLAUDE.md was created.** This is an archived backup; the durable
  operational facts (source-protection rule, backup-push-publishes trap,
  four-flavor structure) are already captured in the runbook prose, which is
  in-repo and versioned. Creating a CLAUDE.md to restate them would duplicate
  and risk drift. If this folder ever becomes an active project again,
  promote those facts into a CLAUDE.md then.

## Traps

- **A `git push` from this backup folder publishes the live site.** This folder
  shares `origin` with `kkml-demo`, which GitHub Pages serves (legacy build,
  `main` / root). Any push from here goes live within ~1–2 min. Do not push
  experimental edits from the backup unless you mean them to be public.
  (Also written as a NOTE in runbook section 6.)
- **Before any deploy, run the source-protection check.** `.gitignore` blocks
  `*.map`, `*-dbg.js`, `*-dbg.controller.js`, `*-dbg.view.xml` because those
  reconstruct the original source of a *public* demo. Rule set 12/08/2026.
  The check and the reasoning are in runbook section 4 + Quick Reference B.

## Where to look

- `docs/OPERATIONS_RUNBOOK.docx` — all operational procedures (preview, deploy,
  source-protection). Procedures belong there, not in this handover.
- `tools/build_runbook.py` — edit this to change the runbook; never hand-edit
  the .docx.
- `README.md` — one-paragraph description + live URL.
- `.gitignore` — the source-protection rule, with its dated reasoning inline.

## Open

- Nothing blocking. The session's work is complete. Rogério was choosing a next
  direction (close / return to ERP Local / extend the runbook) when this
  handover was requested — no direction picked yet (raised 2026-08-13).

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
- **CLAUDE.md created (2026-08-13).** The durable rules — backup-push-publishes,
  the source-protection `.gitignore` rule, four-flavor structure — now live in
  `CLAUDE.md`. (This reverses a decision earlier in the same session to skip it;
  Rogério asked for it explicitly, and the handover-skill convention is that
  durable rules belong in CLAUDE.md and get referenced from here.)

## Traps

The two operational traps — **a push from this backup publishes the live site**,
and **never commit `-dbg`/`.map` source-reconstructing files** — are durable, so
they live in `CLAUDE.md` (§ "Regras duráveis"), with the deploy/check procedures
in the runbook (section 4/6 + Quick Reference B). This session did not hit either;
they are recorded so the next one does not.

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

# KKML0 Costing Reports — Interactive Demo (backup)

Public, static showcase of the KKML0 cost component matrix reports (SAP Material
Ledger). All figures and labels are fictitious sample data. Served from GitHub
Pages. This folder is a **backup snapshot** — built artifacts only, no source.

## Regras duráveis deste projeto

- **Push daqui publica o site.** Este backup compartilha o `origin`
  (`github.com/rfaleiros77/kkml-demo`) com o site vivo, que o GitHub Pages serve
  (legacy build, branch `main`, path `/`). Qualquer `git push origin main` daqui
  vai ao ar em ~1–2 min. Nunca empurrar edição experimental do backup sem querer
  publicá-la.
- **Nunca commitar fonte legível.** É demo público. O `.gitignore` bloqueia
  `*.map`, `*-dbg.js`, `*-dbg.controller.js`, `*-dbg.view.xml` porque esses
  arquivos reconstroem o código original inteiro para qualquer um. Regra de
  12/08/2026. Rodar a checagem de proteção do fonte antes de todo deploy
  (runbook, Quick Reference B).
- **Backup arquivado.** Vive em `_arquivo/`. Não é projeto ativo; não há fonte
  de build aqui (sem `package.json`/`src`/`ui5.yaml`). O que produz os bundles
  está fora deste repo.

## Estrutura — as quatro versões

Landing (`index.html`) linka quatro sub-apps auto-contidos, em dois estilos:

- `costmatrix/` e `releasedmatrix/` — UI custom (build Vite, assets com hash)
- `fiori-actual/` e `fiori-released/` — SAP Fiori/UI5 (Component-preload)

Cada estilo tem a variante "actual" e "released" da cost matrix.

## Operação

**Todo procedimento operacional (preview local, deploy, checagem de fonte) está
no runbook**, não aqui: `docs/OPERATIONS_RUNBOOK.docx`, gerado por
`tools/build_runbook.py` (nunca editar o .docx à mão). Estado da sessão fica em
`docs/HANDOVER.md`.

## Idioma

Conversa em PT-BR; documentos e artefatos de produto em inglês (regra global).

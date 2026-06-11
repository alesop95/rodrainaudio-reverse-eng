---
generated-from-commit: 8a04bc2b2c00b21e10a210564581175e7a07f27d
generated-from-branch: main
generated-date: 2026-06-11
covers-paths:
  - rodrain_es9023_trattazione.tex
  - scripts/**
  - .latexmkrc
last-verified-commit: 8a04bc2b2c00b21e10a210564581175e7a07f27d
---

# Deployment

> In un progetto di documentazione il "deployment" e' la produzione del PDF dalla sorgente LaTeX.

## Livelli

Non c'e' infrastruttura ne' hosting. La sorgente e' `rodrain_es9023_trattazione.tex`; l'artefatto e'
il PDF, derivato e non versionato. Il lavoro avviene anche su Overleaf (vedi
`references/Progetto su overleaf.url`); in locale la build usa l'ambiente TinyTeX descritto in
`dev-testing.md`.

## Comandi

Bootstrap dell'ambiente la prima volta: `powershell -ExecutionPolicy Bypass -File
scripts\setup-tex.ps1` (Windows) oppure `sh scripts/setup-tex.sh` (Unix). Compilazione:
`powershell -ExecutionPolicy Bypass -File scripts\build.ps1` / `sh scripts/build.sh`, che invocano
`latexmk` sull'engine pdflatex fissato in `.latexmkrc`. Pulizia degli ausiliari:
`build.* -Clean` (lascia il PDF) o `-CleanAll` (rimuove anche il PDF). Gli ausiliari LaTeX e il PDF
sono ignorati da git.

## Variabili d'ambiente e segreti

Nessuna. Non si committano credenziali; il link Overleaf in `references/` e' un riferimento, non un
segreto.

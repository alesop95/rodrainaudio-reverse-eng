---
generated-from-commit: 8a04bc2b2c00b21e10a210564581175e7a07f27d
generated-from-branch: main
generated-date: 2026-06-11
covers-paths:
  - rodrain_es9023_trattazione.tex
last-verified-commit: 8a04bc2b2c00b21e10a210564581175e7a07f27d
---

# Deployment

> In un progetto di documentazione il "deployment" è la produzione del PDF dalla sorgente LaTeX.
> Scheda volutamente minimale.

## Livelli

Non c'è infrastruttura né hosting. La sorgente è `rodrain_es9023_trattazione.tex`; l'artefatto è il
PDF, derivato e non versionato. Il lavoro avviene anche su Overleaf (vedi `Progetto su
overleaf.url`).

## Comandi

Compilazione locale tipica con `pdflatex` o `latexmk` (il documento usa `siunitx` e riferimenti
incrociati, quindi conviene una doppia passata o `latexmk -pdf`). Su Overleaf la build è
automatica. Gli ausiliari LaTeX e il PDF sono ignorati da git.

## Variabili d'ambiente e segreti

Nessuna. Non si committano credenziali; il link Overleaf nel `.url` è un riferimento, non un
segreto.

---
generated-from-commit: 8a04bc2b2c00b21e10a210564581175e7a07f27d
generated-from-branch: main
generated-date: 2026-06-11
covers-paths:
  - scripts/**
  - tex-packages.txt
  - .latexmkrc
last-verified-commit: 8a04bc2b2c00b21e10a210564581175e7a07f27d
---

# Ambiente e verifica di build

> In un progetto di documentazione non c'e' un test runner software: il controllo automatizzabile
> e' la compilazione del documento. L'ambiente segue la sezione 13 di `PROJECT-SYSTEM.md`: manifesto
> versionato, distribuzione TeX esterna e non versionata, script di setup e build paralleli.

## Distribuzione e manifesto

L'engine e' TinyTeX (distribuzione TeX Live leggera), installata user-local e condivisa fra i
progetti (`%APPDATA%\TinyTeX` su Windows, `~/.TinyTeX` su Unix), quindi fuori dal repository. La
fonte riproducibile e' il manifesto `tex-packages.txt`: elenca i pacchetti `tlmgr` di primo livello
richiesti dal preambolo (`latexmk`, `siunitx`, `circuitikz`, `pgf`, `babel-italian`, `listings`,
`booktabs`, `hyperref`, `float`, `geometry`, `amsmath`, `amsfonts`, `xcolor`, `lm`, `cm-super`).

## Setup e build

Lo script `scripts/setup-tex.{ps1,sh}` localizza o installa TinyTeX, installa i pacchetti dal
manifesto con `tlmgr install` e verifica con una compilazione minima (un documento di prova che usa
`siunitx` e `circuitikz`). Lo script `scripts/build.{ps1,sh}` compila il `.tex` con `latexmk`
sull'engine pdflatex fissato in `.latexmkrc`. Entrambi invocano i binari dell'ambiente per percorso,
senza attivazione interattiva, cosi' local e CI si comportano identici. La procedura completa e'
incapsulata nella skill `latex-build`.

## Hook e controlli di qualita'

Prima di considerare conclusa una modifica al documento: compilazione senza errori
(`scripts/build.*`), e nessuna affermazione marcata "da verificare" presentata come fatto (vedi
`design-and-security.md`). La checklist operativa locale delle verifiche fisiche sul dispositivo
vive in `_notes/TEST-CHECKLIST.md`, ignorata da git.

---
generated-from-commit: PENDING-FIRST-COMMIT
generated-from-branch: main
generated-date: 2026-06-11
covers-paths:
  - rodrain_es9023_trattazione.tex
  - "*.png"
  - "*.jpg"
  - "*.txt"
  - "*.url"
last-verified-commit: PENDING-FIRST-COMMIT
---

# Stack del progetto: documento, dispositivo e toolchain

> Documento di recupero più importante: tracciato, perché chi clona deve vederlo. È un progetto di
> documentazione tecnica, non software: lo "stack" è la catena documento-dispositivo-strumenti.
> Popolato leggendo il contenuto attuale, senza inventare. La fonte di verità del contenuto tecnico
> è il file LaTeX; questa scheda lo indicizza e ne descrive il ruolo dei file.

## Deliverable e toolchain

Il deliverable è una trattazione tecnica in LaTeX, `rodrain_es9023_trattazione.tex` (circa 1150
righe), autore Alessio Sopranzi, dal titolo "Analisi ingegneristica aggiornata di un DAC Rod Rain".
Il documento usa pacchetti tipici di ingegneria (unità SI via `siunitx`, figure con `float`/`H`,
riferimenti incrociati con `label`/`ref`) e include immagini da una cartella `pictures/`. La
compilazione e il lavoro collaborativo avvengono anche su Overleaf (vedi `Progetto su
overleaf.url`). Il PDF e gli ausiliari LaTeX sono artefatti derivati e restano ignorati da git
(vedi `.gitignore`); il `.tex` è la sorgente versionata.

## Dispositivo sotto analisi

Un amplificatore per cuffie con telaio di tipo Beyerdynamic A1, rietichettato "Rod Rain audio", in
cui è stato integrato in Asia un modulo DAC USB. La catena del segnale modellata è
USB to SA9023 (ricevitore USB-audio) to I²S to ES9023 (DAC con driver integrato 2 Vrms) to filtro
RC to uscita line-level, da cui lo stadio cuffie discreto su dissipatore. Alimentazione lineare con
toroide YHDC PTC15 (2x12 V / 625 mA). Pannello posteriore con AUDIO IN, AUDIO OUT (RCA), USB-B e
rete 220 V. I dettagli, le correzioni rispetto alla stesura precedente e gli stati "da verificare"
sono in `decisions.md`.

## Mappa dei file e ruolo

```
rodrain_es9023_trattazione.tex   sorgente LaTeX del trattato (deliverable), tracciato
Notes.txt                        appunti iniziali e sintesi delle risposte a/b/c
DAC schematic.txt                puntatore URL allo schematico ES9023
audio science.txt                puntatore URL a misure indipendenti (AudioScienceReview)
ES9023_SCHEMATIC_DAC_AUDIO.png   schematico di riferimento sezione analogica (variante I²S)
scheda-dac.png                   foto del modulo DAC ES9023 (USB)
rear.png                         foto del pannello posteriore (connettori)
toroid.png                       foto del trasformatore toroidale
photo_2025-12-01_10-15-55.jpg    foto del dispositivo
Beyerdynamic A1.url              segnalibro al thread di riferimento sull'A1
Progetto su overleaf.url         segnalibro al progetto Overleaf del documento
```

## Struttura del trattato (sezioni principali)

Premessa metodologica e correzioni; introduzione e obiettivi; richiami teorici di segnali;
architettura del sistema (blocchi e percorsi del segnale); punto (a) instradamento RCA IN / RCA OUT
/ cuffie; punto (b) natura della customizzazione; stadio DAC ES9023; filtro RC e accoppiamento AC;
stadio cuffie discreto e impedenza d'uscita; carichi cuffia; rumore; alimentazione; punto (c)
impedenza pilotabile e scelta della cuffia; modello SPICE parametrico; conclusioni; appendici.

## Riferimenti esterni

Schematico AudioWorkshop ESS ES9023 (variante I²S), misure indipendenti su AudioScienceReview,
manuale e thread Beyerdynamic A1. I link puntuali sono nei `.url` e nelle note del `.tex`.

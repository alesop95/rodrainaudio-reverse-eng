---
generated-from-commit: 8a04bc2b2c00b21e10a210564581175e7a07f27d
generated-from-branch: main
generated-date: 2026-06-11
covers-paths: []
last-verified-commit: 8a04bc2b2c00b21e10a210564581175e7a07f27d
---

# Roadmap

> Direzione e priorità del progetto. Tracciata. Non è il work-log: qui sta dove si va, non cosa è
> già stato fatto.

## Direzione

Chiudere i punti aperti dell'analisi promuovendo le ipotesi correnti a fatti tramite misure fisiche
sul dispositivo, e consolidare gli esiti nel trattato LaTeX.

## Priorità

Prima la misura di Z_out dello stadio cuffie (ADR-005): è la verifica con il maggiore effetto a
valle, perché condiziona potenze, fattore di smorzamento e la scelta della cuffia. Poi la misura di
instradamento RCA OUT vs uscita DAC (ADR-004, punto a). Infine la conferma per ispezione delle
sigle dei componenti della catena USB to I²S (ADR-002, punto b).

## Idee e ipotesi da verificare

Tutte marcate come da verificare in `decisions.md`: catena del segnale via SA9023 (ADR-002),
attribuzione clone A1-like (ADR-003), AUDIO OUT come loop passivo (ADR-004), Z_out circa 100 ohm
(ADR-005). Il trattato include già un modello SPICE parametrico e una procedura di misura di Z_out
(tono 1 kHz, confronto a vuoto e con resistore noto) da eseguire.

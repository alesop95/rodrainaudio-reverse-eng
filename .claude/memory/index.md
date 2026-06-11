# Snapshot di sincronizzazione

> Da leggere per primo a inizio sessione. Fotografa lo stato del progetto al commit di
> riferimento e mappa ogni scheda al suo stato di verifica. È la fonte di verità su cosa è fatto,
> non le spunte del diario.

## Stato

```
Branch attivo:         main
Commit di riferimento: PENDING-FIRST-COMMIT
Data snapshot:         2026-06-11
```

## Stato di verifica delle schede

| Scheda | last-verified | Stato |
|---|---|---|
| STACK.md | PENDING-FIRST-COMMIT | popolata (in attesa del primo commit) |
| design-and-security.md | PENDING-FIRST-COMMIT | stub (non applicabile a progetto-doc) |
| deployment.md | PENDING-FIRST-COMMIT | stub (build LaTeX/Overleaf) |
| dev-testing.md | PENDING-FIRST-COMMIT | stub (non applicabile) |
| current-work.md | PENDING-FIRST-COMMIT | popolata (domande a/b/c) |
| roadmap.md | PENDING-FIRST-COMMIT | popolata (misure da fare) |

## Punto di ripresa

Asset riorganizzati in `pictures/` e `references/`; `Notes.txt` spostato nel privato `_notes/`. Le
immagini usate dal `.tex` ora risolvono. Da fare: committare la riorganizzazione, poi eseguire
`sync-context` per ancorare tutte le schede a `HEAD` (oggi ancora `PENDING-FIRST-COMMIT`).
L'indagine tecnica resta aperta sui tre punti in `current-work.md`; la verifica più importante è la
misura di Z_out (vedi `decisions.md` ADR-005).

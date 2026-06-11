# Snapshot di sincronizzazione

> Da leggere per primo a inizio sessione. Fotografa lo stato del progetto al commit di
> riferimento e mappa ogni scheda al suo stato di verifica. È la fonte di verità su cosa è fatto,
> non le spunte del diario.

## Stato

```
Branch attivo:         main
Commit di riferimento: 8a04bc2b2c00b21e10a210564581175e7a07f27d
Data snapshot:         2026-06-11
```

## Stato di verifica delle schede

| Scheda | last-verified | Stato |
|---|---|---|
| STACK.md | 8a04bc2 | aggiornata (popolata) |
| design-and-security.md | 8a04bc2 | aggiornata (stub, non applicabile a progetto-doc) |
| deployment.md | 8a04bc2 | aggiornata (stub, build LaTeX/Overleaf) |
| dev-testing.md | 8a04bc2 | aggiornata (stub, non applicabile) |
| current-work.md | 8a04bc2 | aggiornata (popolata, domande a/b/c) |
| roadmap.md | 8a04bc2 | aggiornata (popolata, misure da fare) |

## Punto di ripresa

Sistema adottato e schede ancorate al commit 8a04bc2 (primo ancoraggio eseguito): tutte
`aggiornate`, nessun drift. Gli asset sono organizzati in `pictures/` e `references/` e le immagini
del `.tex` risolvono. L'indagine tecnica resta aperta sui tre punti in `current-work.md`; la
prossima azione concreta è la misura di Z_out (vedi `decisions.md` ADR-005), che condiziona i punti
(a) e (c). Da qui in avanti il drift si gestisce con `sync-context` a ogni passo significativo.

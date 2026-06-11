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
| STACK.md | 8a04bc2 | da ribumpare dopo commit ambiente (covers-paths estese) |
| design-and-security.md | 8a04bc2 | aggiornata (stub, non applicabile a progetto-doc) |
| deployment.md | 8a04bc2 | da ribumpare dopo commit ambiente (comandi build) |
| dev-testing.md | 8a04bc2 | da ribumpare dopo commit ambiente (toolchain TinyTeX) |
| current-work.md | 8a04bc2 | aggiornata (popolata, domande a/b/c) |
| roadmap.md | 8a04bc2 | aggiornata (popolata, misure da fare) |

## Punto di ripresa

Ambiente LaTeX completato e verificato: TinyTeX user-local installato, manifesto `tex-packages.txt`,
script `scripts/setup-tex.*` e `scripts/build.*`, skill `latex-build`, gate di startup in
`init-project-system`, sillabazione italiana risolta (`hyphen-italian`). Il trattato compila pulito
(`scripts/build.ps1` -> `rodrain_es9023_trattazione.pdf`, 20 pagine). Tutto rispecchiato nel bundle
standard J: (vedi `decisions.md` ADR-007).

PRIMA AZIONE alla ripresa: committare il lavoro non ancora committato (ambiente LaTeX, schede
aggiornate, skill del motore), poi eseguire `sync-context` per ribumpare a `HEAD` i
`last-verified-commit` di `STACK`/`dev-testing`/`deployment` (le cui `covers-paths` sono cambiate).
PROSSIMA AZIONE TECNICA: la misura di Z_out (`decisions.md` ADR-005), che sblocca i punti (a) e (c)
dell'indagine in `current-work.md`.

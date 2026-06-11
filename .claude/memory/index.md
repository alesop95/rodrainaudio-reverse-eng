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

Aggiunto l'ambiente LaTeX (TinyTeX user-local, manifesto `tex-packages.txt`, script in `scripts/`,
skill `latex-build` — vedi ADR-007). Da fare subito: 1) installare l'ambiente con
`scripts/setup-tex.ps1` (rete, qualche minuto); 2) committare l'ambiente; 3) lanciare `/sync-context`
per ribumpare i `last-verified-commit` di STACK/dev-testing/deployment a HEAD; 4) promuovere lo
stesso layout nello standard (`.claude/templates/latex/`) e nel bundle J:. L'indagine tecnica resta
aperta sui tre punti in `current-work.md`; la prossima azione tecnica concreta è la misura di Z_out
(`decisions.md` ADR-005), che condiziona i punti (a) e (c).

# Work-log

> Append-only, in ordine cronologico inverso (la voce più recente in alto). Ogni passo
> significativo e ogni intervento manuale rilevante lascia una voce con data, file toccati, motivo
> e commit di riferimento. Qui confluisce anche il log di riconciliazione dei documenti sorgente,
> con nome del documento e esito, così la data di allineamento sopravvive a un clone.

## 2026-06-11 — Adozione del sistema di progetto su progetto preesistente

Commit: PENDING-FIRST-COMMIT
File toccati: import del motore in `.claude/` (`PROJECT-SYSTEM.md`, `rules/`, skill
`init-project-system`/`sync-context`/`git-sync`/`repo-status`, `templates/`); creazione di
`.gitignore`, `.claude/settings.json`, `CLAUDE.md`, `CLAUDE.local.md`, `_notes/`, `.claude/memory/`
e `.claude/context/` (schede con frontmatter ancorato a `PENDING-FIRST-COMMIT`).
Motivo: allineare retroattivamente allo standard portabile un progetto di reverse-engineering già
esistente (trattazione LaTeX su un DAC "Rod Rain audio") ma non ancora versionato.
Note di stato:
- Il progetto non aveva storia git: `git init` eseguito ora, identità locale personale (alesop95),
  remote `git@github-personal:alesop95/rodrainaudio-reverse-eng.git`. Primo commit e push restano
  manuali dell'utente. La memoria è stata bootstrappata dallo stato attuale del contenuto, non da
  una storia inesistente, senza inventare.
- Scansione segreti: pulita. Nessun `.env`, chiave o credenziale; i `.url` contengono solo link.
  Promemoria: `Progetto su overleaf.url` è un link a progetto Overleaf, non una credenziale.
- MCP: non configurato per scelta. Promemoria: se in futuro servisse integrare un servizio
  esterno, creare `.mcp.json` e `mcp/` in radice (mai sotto `.claude`) dal template
  `.claude/templates/mcp.json`.

## Prossimo passo

Dopo il primo commit manuale, eseguire la skill `sync-context` per sostituire ogni
`PENDING-FIRST-COMMIT` con l'hash di `HEAD` e ancorare il drift al contenuto.

# Work-log

> Append-only, in ordine cronologico inverso (la voce più recente in alto). Ogni passo
> significativo e ogni intervento manuale rilevante lascia una voce con data, file toccati, motivo
> e commit di riferimento. Qui confluisce anche il log di riconciliazione dei documenti sorgente,
> con nome del documento e esito, così la data di allineamento sopravvive a un clone.

## 2026-06-11 — Portabilità su Windows delle skill del motore

Commit: (incluso nel commit di manutenzione delle skill)
File toccati: `.claude/skills/{sync-context,repo-status,git-sync,init-project-system}/SKILL.md`,
`.claude/settings.json`.
Motivo: i comandi pre-iniettati (`` !`...` ``) delle skill usavano un ciclo `for` (bloccato dal
controllo permessi di Claude Code) e sintassi solo-bash (`cat | head`, `sed`, `||`, `2>nul`) non
portabile su Windows/PowerShell, per cui `/sync-context` falliva. Riscritti tutti come singoli
comandi git coperti dall'allowlist; la lettura di `index.md` e del frontmatter è spostata sullo
strumento Read. Aggiunto `Bash(git tag:*)` all'allowlist per `repo-status`. La stessa patch va
applicata al bundle di riferimento in J: per non far divergere lo standard (modifica manuale
dell'utente, non eseguita da qui).

Nota di riconciliazione: questo intervento tocca solo le skill e i permessi, non le `covers-paths`
delle schede, quindi nessuna scheda diventa stale e il `last-verified-commit` (8a04bc2) resta valido.

## 2026-06-11 — Primo ancoraggio delle schede (sync-context)

Commit: 8a04bc2
File toccati: frontmatter di tutte le schede in `.claude/context/` (`generated-from-commit` e
`last-verified-commit`), `memory/index.md` (commit di riferimento e tabella di verifica).
Motivo: primo ancoraggio previsto dal passo 0 di `sync-context`. Sostituito il segnaposto
`PENDING-FIRST-COMMIT` con l'hash di HEAD (8a04bc2) ora che il repo ha commit. Le sei schede
risultano `aggiornate`, nessun drift. Nota operativa: la skill `sync-context` non è eseguibile
direttamente in questo ambiente perché il suo comando bash pre-iniettato usa un ciclo `for` che il
controllo permessi blocca; l'ancoraggio è stato svolto applicando a mano la logica della skill.

## 2026-06-11 — Riorganizzazione degli asset in cartelle

Commit: 8a04bc2
File toccati: spostate le immagini in `pictures/`, i segnalibri e i puntatori-URL in `references/`,
e `Notes.txt` in `_notes/` (livello privato ignorato). Aggiornata `context/STACK.md` (mappa file e
`covers-paths` -> `pictures/**`, `references/**`).
Motivo: la root era dispersiva; inoltre il `.tex` referenzia le immagini come `pictures/...`, quindi
spostarle in `pictures/` ripara gli `\includegraphics` (prima rotti in locale). `Notes.txt` esce dal
repository al prossimo commit perché `_notes/` è ignorato; il suo contenuto tecnico è già in
`decisions.md` e `current-work.md`.

## 2026-06-11 — Adozione del sistema di progetto su progetto preesistente

Commit: 4f8a782
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

Schede ancorate: il drift d'ora in poi si gestisce con `sync-context` a ogni passo significativo. La
prossima azione tecnica concreta è la misura di Z_out dello stadio cuffie (ADR-005), che condiziona
i punti (a) e (c) dell'indagine.

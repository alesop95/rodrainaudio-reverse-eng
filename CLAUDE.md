# rodrainaudio-reverse-eng

> Istruzioni di team, versionate. Questo file è l'indice del progetto: indicizza i soli file
> satellite tracciati e descrive la procedura di ripresa. Le preferenze personali vivono in
> `CLAUDE.local.md`, ignorato da git, non qui.

## Cos'è questo progetto

Studio di reverse-engineering di un dispositivo audio etichettato "Rod Rain audio": un
amplificatore per cuffie con telaio di tipo Beyerdynamic A1 in cui è stato integrato in Asia un
modulo DAC USB (ricevitore USB SA9023 più convertitore ES9023 a ingresso I²S). Il deliverable è
una trattazione tecnica in LaTeX che documenta la catena del segnale, la customizzazione rispetto
al modello di base e i vincoli d'uso, distinguendo ciò che è verificato da ciò che resta da
misurare. Non è un progetto software.

## Procedura di ripresa in una sessione nuova

Lo stato del progetto è interamente recuperabile su disco. All'inizio di una sessione si segue
questo percorso fisso. Si legge per primo `.claude/memory/index.md`, che dà branch, commit di
riferimento, stato di verifica di ogni scheda e punto di ripresa. Si legge poi
`.claude/context/current-work.md` se c'è un'indagine attiva, per sapere cosa è in lavorazione e
quali sono le domande aperte. Si invoca la skill `sync-context` per verificare il drift tra schede
e contenuto, e si leggono solo le schede pertinenti al task, mai tutte insieme. Il work-log
`.claude/memory/progress.md` e il registro `.claude/memory/decisions.md` forniscono la storia e le
decisioni quando servono. Il materiale grezzo sotto `_notes/` si apre solo per verificare un
requisito originale.

## Indice dei file satellite tracciati

Memoria e meta-stato, sotto `.claude/memory/`, letti sempre a inizio sessione.

```
.claude/memory/index.md       snapshot e tabella di sincronizzazione, da leggere per primo
.claude/memory/progress.md    work-log append-only di passi e riconciliazioni
.claude/memory/decisions.md   registro ADR-lite delle decisioni e conclusioni d'analisi
```

Schede tecniche, sotto `.claude/context/`, con frontmatter di riconciliazione.

```
.claude/context/STACK.md                documento e dispositivo sotto analisi, toolchain, asset
.claude/context/design-and-security.md  metodo d'analisi (verificato vs inferito); stub
.claude/context/deployment.md           build del PDF (LaTeX/Overleaf); stub
.claude/context/dev-testing.md          non applicabile a un progetto di documentazione; stub
.claude/context/current-work.md         indagine attiva: le tre domande aperte (a/b/c)
.claude/context/roadmap.md              misure e verifiche ancora da fare
```

Regole modulari caricate su necessità, sotto `.claude/rules/`, e skill richiamabili, sotto
`.claude/skills/`. Lo standard di sistema completo è in `.claude/PROJECT-SYSTEM.md`.

## Vincoli di team

Le operazioni di `git add`, commit e push restano sempre manuali dell'utente: l'agente prepara i
file, non committa. L'identità git è impostata a livello locale del repo secondo
`.claude/rules/git-identity-and-repo.md` (profilo personale alesop95). Lo stile di documentazione
e di interazione è quello di `.claude/rules/interaction-style.md`: prosa discorsiva, niente elenchi
puntati né emoji, nulla di inferito presentato come fatto. Claude non scrive autonomamente nei file
di memoria e di contesto: li aggiorna solo su richiesta esplicita, così il versionamento resta
sotto controllo umano.

---
generated-from-commit: PENDING-FIRST-COMMIT
generated-from-branch: main
generated-date: 2026-06-11
covers-paths:
  - rodrain_es9023_trattazione.tex
last-verified-commit: PENDING-FIRST-COMMIT
stato: in corso
---

# Lavoro in corso

> La fonte di verità su cosa è fatto resta `memory/index.md` e il work-log, non le spunte di questo
> file. L'indagine ruota attorno alle tre domande originali (a/b/c). Le conclusioni provvisorie sono
> registrate in `decisions.md` con stato verificato o da-verificare.

## Indagine: reverse-engineering del DAC Rod Rain

Cosa fa: documentare la catena del segnale, la customizzazione e i vincoli d'uso del dispositivo,
distinguendo ciò che è verificato da ciò che resta da misurare, e consolidarlo nel trattato LaTeX.

### Punto (a) — Instradamento di RCA IN, RCA OUT e cuffie

Domanda: lo stesso ingresso viene dato su due uscite, oppure AUDIO OUT è solo un passthrough
passivo di AUDIO IN (RCA analogico)? Ipotesi corrente: AUDIO OUT è loop passivo di AUDIO IN, il DAC
alimenta lo stadio cuffie (ADR-004). "Stesso segnale su due uscite" è possibile solo se il DAC è
cablato anche all'RCA OUT.
Definition of done:

- [ ] Misura a multimetro che stabilisce se AUDIO OUT segue AUDIO IN o l'uscita del DAC
- [ ] Aggiornamento della sezione "Punto (a)" del trattato con l'esito

### Punto (b) — Natura della customizzazione

Domanda: in cosa consiste la customizzazione rispetto al modello di base. Ipotesi corrente:
sostituzione dell'ingresso analogico di un amp cuffie discreto (topologia A1-like) con un modulo
USB-DAC SA9023 + ES9023 cablato al nodo d'ingresso dello stadio cuffie; il loop RCA IN to OUT resta
com'era (ADR-002, ADR-003).
Definition of done:

- [ ] Conferma per ispezione delle sigle dei componenti (SA9023, ES9023, quarzo 12 MHz)
- [ ] Conferma che il punto di iniezione del DAC è il nodo d'ingresso dello stadio cuffie

### Punto (c) — Massima impedenza pilotabile e scelta cuffia

Domanda: qual è la massima impedenza di cuffia pilotabile e quale cuffia singola consigliare.
Risposta corrente: nessun tetto superiore pratico; il vincolo è verso il basso; fascia ottimale
>= 250 ohm, idealmente 300 o 600 ohm. Raccomandazione singola: Beyerdynamic DT 880 Edition 600 ohm
(ADR-006), con HD 600 come alternativa se Z_out risultasse basso.
Definition of done:

- [x] Raccomandazione singola motivata nel trattato
- [ ] Conferma condizionale dopo la misura di Z_out

## Domande aperte

La misura di Z_out (ADR-005) è la verifica trasversale più importante: condiziona (a) le potenze e
il fattore di smorzamento, e (c) la gerarchia di scelta della cuffia. Finché non è eseguita, le
voci ADR-003/004/005 restano "da verificare".

## Riconciliazione

Ultima verifica: 2026-06-11 al commit PENDING-FIRST-COMMIT (da ancorare con `sync-context` dopo il
primo commit).

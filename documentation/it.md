<!-- ELUCENIA technical documentation · tamanho-amostral-proporcao · it · no clinical/professional/rights approval -->

# Dimensione del campione per stimare una proporzione

[condizioni, fonti e autorizzazioni](https://elucenia.org/it/strumenti/tamanho-amostral-proporcao)

## Come usare

Usi lo strumento nel portale oppure apra index.html tramite un server HTTP locale. Selezioni la lingua, compili i campi ed esegua il calcolo.

## Dati di ingresso e unità

### Proporzione attesa (se sconosciuta, usare 50%)

`p`

% · intervallo: 1–99

### Margine di errore assoluto (precisione)

`d`

punti % · intervallo: 0,5–30

### Livello di confidenza

`conf`

- `90` — 90%
- `95` — 95%
- `99` — 99%

### Dimensione della popolazione (facoltativa, per popolazione finita)

`pop`

persone · facoltativo · intervallo: 10–100000000

### Perdite e rifiuti previsti (facoltativi)

`perdas`

% · facoltativo · intervallo: 0–50

## Edizione del metodo

OMS/Lwanga–Lemeshow 1991:proporzione singola, popolazione finita, perdite, eccesso;95% z1,959964

## Formula documentata

n0 = z² × p × (1 − p) / d²; z = 1,645 (90%), 1,96 (95%) o 2,576 (99%); d = margine di errore assoluto.

Popolazione finita (N): n = n0 / \[1 + (n0 − 1) / N\]. Perdite: nfinal = n / (1 − proporzione persa). Tutto arrotondato per eccesso.

Precisione numerica: Per 95%, z=1,959964;1,96 sopra è arrotondato. Correzione del caso di riferimento registrata nella provenienza del catalogo.

## Limiti e popolazione

Usare una proporzione attesa e un margine di errore assoluto, nelle unità indicate, per stimare una proporzione con campionamento semplice. Il livello di confidenza non è la potenza statistica di un confronto. La correzione per popolazione finita presuppone una popolazione definita; non include automaticamente cluster, stratificazione o effetto del disegno. L’inflazione per perdite aumenta il reclutamento ma non elimina la distorsione da mancata risposta. Questa interfaccia non ha validato l’approssimazione normale né l’intero manuale WHO 1991 per ogni disegno.

## Riferimenti

- [Lwanga SK, Lemeshow S. Sample size determination in health studies: a practical manual. Organização Mundial da Saúde, 1991.](https://iris.who.int/handle/10665/40062)

- [Charan J, Biswas T. How to calculate sample size for different study designs in medical research? Indian J Psychol Med, 2013.](https://doi.org/10.4103/0253-7176.116232)

- [Charan/Biswas2013 original article content](https://www.yoursearchevidence.com/sites/g/files/vrxlpx50391/files/2024-10/M2_ParticularidadesInvestigacion.pdf)

## Riprodurre i test tecnici

Esegua node test.cjs nella cartella principale di questo repository per ripetere i casi sintetici registrati. Gli input, i risultati attesi e le tolleranze originali sono conservati. I test tecnici non costituiscono validazione clinica.

```sh
node test.cjs
```

tool.json contiene le fonti, l’edizione e l’ambito della revisione. examples.json conserva gli input e i risultati attesi dei casi sintetici; results.json registra i risultati ottenuti.

[Scheda e riferimenti](../tool.json) · [Codice JavaScript](../calculator.js) · [Casi di riferimento](../examples.json) · [results.json](../results.json)

## Revisione e condizioni d’uso

Non è stata effettuata una revisione clinica indipendente.

Questa interfaccia è una traduzione realizzata dagli autori, non un’edizione ufficiale o certificata. Non sono state eseguite la revisione clinica indipendente, la revisione linguistica professionale né la verifica delle autorizzazioni relative ai diritti sugli strumenti.

Risultato della formula o classificazione. Interpretazione, condotta e applicabilità dipendono dalla valutazione professionale e dalla fonte selezionata.

## Licenza e attribuzione

Apache-2.0 si applica solo al codice di ELUCENIA. I diritti su strumenti, pubblicazioni, traduzioni e dati restano ai rispettivi titolari. Conservi LICENSE e NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

## Risultati documentati

Le informazioni seguenti conservano gli output del metodo per esempi sintetici. Non costituiscono una validazione clinica indipendente.

### 1

Campione necessario per stimare 20,0% ± 5,0 punti percentuali con 95% di confidenza

| Dettagli del risultato | |
| --- | --- |
| Campione senza correzione (popolazione infinita) | 246 |

Formula per campionamento casuale semplice. Nel campionamento a grappoli, moltiplicare per l’effetto del disegno (in genere 1,5 a 2).


### 2

Campione necessario per stimare 50,0% ± 5,0 punti percentuali con 95% di confidenza

| Dettagli del risultato | |
| --- | --- |
| Campione senza correzione (popolazione infinita) | 385 |
| Con correzione per popolazione finita (N = 1000) | 278 |

Formula per campionamento casuale semplice. Nel campionamento a grappoli, moltiplicare per l’effetto del disegno (in genere 1,5 a 2).


### 3

Campione necessario per stimare 50,0% ± 5,0 punti percentuali con 95% di confidenza

| Dettagli del risultato | |
| --- | --- |
| Campione senza correzione (popolazione infinita) | 385 |
| Aggiungendo 10% di perdite | 428 |

Formula per campionamento casuale semplice. Nel campionamento a grappoli, moltiplicare per l’effetto del disegno (in genere 1,5 a 2).


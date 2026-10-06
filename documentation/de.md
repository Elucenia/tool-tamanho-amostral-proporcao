<!-- ELUCENIA technical documentation · tamanho-amostral-proporcao · de · no clinical/professional/rights approval -->

# Stichprobengröße zur Schätzung eines Anteils

[Bedingungen, Quellen und Berechtigungen](https://elucenia.org/de/werkzeuge/tamanho-amostral-proporcao)

## Verwendung

Verwenden Sie das Werkzeug im Portal oder öffnen Sie index.html über einen lokalen HTTP-Server. Wählen Sie die Sprache, füllen Sie die Felder aus und berechnen Sie das Ergebnis.

## Eingaben und Einheiten

### Erwarteter Anteil (falls unbekannt, 50 % verwenden)

`p`

% · Bereich: 1–99

### Absolute Fehlerspanne (Präzision)

`d`

Punkte % · Bereich: 0,5–30

### Konfidenzniveau

`conf`

- `90` — 90%
- `95` — 95%
- `99` — 99%

### Populationsgröße (optional, bei endlicher Population)

`pop`

Personen · optional · Bereich: 10–100000000

### Erwartete Ausfälle und Ablehnungen (optional)

`perdas`

% · optional · Bereich: 0–50

## Fassung der Methode

WHO/Lwanga–Lemeshow 1991:einzelner Anteil, endliche Population, Ausfälle, Aufrunden;95% z1,959964

## Dokumentierte Formel

n0 = z² × p × (1 − p) / d²; z = 1,645 (90%), 1,96 (95%) oder 2,576 (99%); d = absolute Fehlermarge.

Endliche Population (N): n = n0 / \[1 + (n0 − 1) / N\]. Ausfälle: nfinal = n / (1 − Ausfallanteil). Alle Werte aufrunden.

Numerische Präzision: Für 95% gilt z=1,959964;1,96 oben ist gerundet. Referenzfallkorrektur ist in Katalogherkunft dokumentiert.

## Grenzen und Population

Verwenden Sie einen erwarteten Anteil und eine absolute Fehlermarge in den angegebenen Einheiten, um einen Anteil bei einfacher Stichprobenziehung zu schätzen. Das Konfidenzniveau ist nicht die statistische Teststärke eines Vergleichs. Die Korrektur für eine endliche Population setzt eine definierte Population voraus; sie berücksichtigt nicht automatisch Cluster, Stratifizierung oder einen Designeffekt. Die Erhöhung für Ausfälle steigert die Rekrutierung, beseitigt aber keine Nonresponse-Verzerrung. Diese Oberfläche hat weder die Normalapproximation noch das vollständige WHO-Handbuch von 1991 für jedes Design validiert.

## Referenzen

- [Lwanga SK, Lemeshow S. Sample size determination in health studies: a practical manual. Organização Mundial da Saúde, 1991.](https://iris.who.int/handle/10665/40062)

- [Charan J, Biswas T. How to calculate sample size for different study designs in medical research? Indian J Psychol Med, 2013.](https://doi.org/10.4103/0253-7176.116232)

- [Charan/Biswas2013 original article content](https://www.yoursearchevidence.com/sites/g/files/vrxlpx50391/files/2024-10/M2_ParticularidadesInvestigacion.pdf)

## Technische Tests reproduzieren

Führen Sie node test.cjs im Stammverzeichnis dieses Repositorys aus, um die dokumentierten synthetischen Fälle zu wiederholen. Ursprüngliche Eingaben, erwartete Ergebnisse und Toleranzen bleiben erhalten. Technische Tests stellen keine klinische Validierung dar.

```sh
node test.cjs
```

tool.json enthält Quellen, Ausgabe und Umfang der Überprüfung. examples.json bewahrt die synthetischen Eingaben und erwarteten Ergebnisse; results.json dokumentiert die tatsächlich erhaltenen Ergebnisse.

[Eintrag und Referenzen](../tool.json) · [JavaScript-Code](../calculator.js) · [Referenzfälle](../examples.json) · [results.json](../results.json)

## Überprüfung und Nutzungsbedingungen

Eine unabhängige klinische Prüfung wurde nicht durchgeführt.

Diese Benutzeroberfläche ist eine selbst erstellte Übersetzung und keine offizielle oder zertifizierte Ausgabe. Eine unabhängige klinische Überprüfung, eine professionelle sprachliche Prüfung und eine Klärung der Rechte an den Instrumenten wurden nicht durchgeführt.

Ergebnis der Formel oder Klassifikation. Interpretation, Vorgehen und Anwendbarkeit hängen von der fachlichen Beurteilung und der ausgewählten Quelle ab.

## Lizenz und Urheberangaben

Apache-2.0 gilt nur für den ELUCENIA-Code. Die Rechte an Instrumenten, Veröffentlichungen, Übersetzungen und Daten verbleiben bei den jeweiligen Rechteinhabern. Bewahren Sie LICENSE und NOTICE auf.

ELUCENIA · Felipe Guedes · Copyright © 2026

## Dokumentierte Ergebnisse

Die folgenden Angaben bewahren die Ausgaben der Methode für synthetische Beispiele. Sie stellen keine unabhängige klinische Validierung dar.

### 1

Benötigte Stichprobe, um 20,0 % ± 5,0 Prozentpunkte mit 95 % Konfidenz zu schätzen

| Ergebnisdetails | |
| --- | --- |
| Stichprobe ohne Korrektur (unendliche Population) | 246 |

Formel für einfache Zufallsstichprobe. Bei Clusterstichproben mit dem Designeffekt multiplizieren (in der Regel 1,5 bis 2).


### 2

Benötigte Stichprobe, um 50,0 % ± 5,0 Prozentpunkte mit 95 % Konfidenz zu schätzen

| Ergebnisdetails | |
| --- | --- |
| Stichprobe ohne Korrektur (unendliche Population) | 385 |
| Mit endlicher Population-Korrektur (N = 1000) | 278 |

Formel für einfache Zufallsstichprobe. Bei Clusterstichproben mit dem Designeffekt multiplizieren (in der Regel 1,5 bis 2).


### 3

Benötigte Stichprobe, um 50,0 % ± 5,0 Prozentpunkte mit 95 % Konfidenz zu schätzen

| Ergebnisdetails | |
| --- | --- |
| Stichprobe ohne Korrektur (unendliche Population) | 385 |
| Mit 10 % Verlusten zuschlagen | 428 |

Formel für einfache Zufallsstichprobe. Bei Clusterstichproben mit dem Designeffekt multiplizieren (in der Regel 1,5 bis 2).


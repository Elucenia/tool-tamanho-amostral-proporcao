<!-- ELUCENIA technical documentation · tamanho-amostral-proporcao · en · no clinical/professional/rights approval -->

# Sample size for estimating a proportion

[conditions, sources and permissions](https://elucenia.org/en/tools/tamanho-amostral-proporcao)

## How to use

Use the tool in the portal or open index.html through a local HTTP server. Select the language, complete the fields and calculate.

## Inputs and units

### Expected proportion (if unknown, use 50%)

`p`

% · range: 1–99

### Absolute margin of error (precision)

`d`

points % · range: 0.5–30

### Confidence level

`conf`

- `90` — 90%
- `95` — 95%
- `99` — 99%

### Population size (optional, for a finite population)

`pop`

people · optional · range: 10–100000000

### Anticipated losses and refusals (optional)

`perdas`

% · optional · range: 0–50

## Method edition

WHO/Lwanga–Lemeshow 1991: single proportion, finite-population correction, attrition, ceiling;95% z1.959964

## Documented formula

n0 = z² × p × (1 − p) / d²; z = 1.645 (90%), 1.96 (95%) or 2.576 (99%); d = absolute error margin.

Finite population (N): n = n0 / \[1 + (n0 − 1) / N\]. Attrition: nfinal = n / (1 − attrition proportion). All values round upward.

Numerical precision: For 95% calculation, z=1.959964;1.96 above is rounded display. The reference-case correction is recorded in catalogue provenance.

## Limits and population

Use an expected proportion and an absolute margin of error, in the indicated units, to estimate a proportion under simple sampling. Confidence level is not the statistical power of a comparison. Finite-population correction assumes a defined population; it does not automatically incorporate clusters, stratification or a design effect. Inflation for losses increases recruitment but does not remove nonresponse bias. The normal approximation and the full WHO 1991 manual have not been validated for every design by this interface.

## References

- [Lwanga SK, Lemeshow S. Sample size determination in health studies: a practical manual. Organização Mundial da Saúde, 1991.](https://iris.who.int/handle/10665/40062)

- [Charan J, Biswas T. How to calculate sample size for different study designs in medical research? Indian J Psychol Med, 2013.](https://doi.org/10.4103/0253-7176.116232)

- [Charan/Biswas2013 original article content](https://www.yoursearchevidence.com/sites/g/files/vrxlpx50391/files/2024-10/M2_ParticularidadesInvestigacion.pdf)

## Reproduce the technical tests

Run node test.cjs in the root directory of this repository to repeat the recorded synthetic cases. Original inputs, expectations and tolerances are preserved. Technical tests do not constitute clinical validation.

```sh
node test.cjs
```

tool.json contains sources, edition and review scope. examples.json retains synthetic inputs and expectations; results.json records the obtained results.

[Record and references](../tool.json) · [JavaScript code](../calculator.js) · [Reference cases](../examples.json) · [results.json](../results.json)

## Review and conditions of use

Independent clinical review has not been performed.

This interface is an authorial translation, not an official or certified edition. Independent clinical review, professional language review and instrument rights clearance have not been performed.

Formula or classification result. Interpretation, care and applicability depend on professional assessment and the selected source.

## License and attribution

Apache-2.0 applies only to ELUCENIA code. Rights to instruments, publications, translations and data remain with their respective holders. Preserve LICENSE and NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

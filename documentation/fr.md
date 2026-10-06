<!-- ELUCENIA technical documentation · tamanho-amostral-proporcao · fr · no clinical/professional/rights approval -->

# Taille d’échantillon pour estimer une proportion

[conditions, sources et autorisations](https://elucenia.org/fr/outils/tamanho-amostral-proporcao)

## Mode d’emploi

Utilisez l’outil sur le portail ou ouvrez index.html via un serveur HTTP local. Sélectionnez la langue, remplissez les champs et lancez le calcul.

## Données d’entrée et unités

### Proportion attendue (si inconnue, utiliser 50 %)

`p`

% · intervalle: 1–99

### Marge d’erreur absolue (précision)

`d`

points % · intervalle: 0,5–30

### Niveau de confiance

`conf`

- `90` — 90%
- `95` — 95%
- `99` — 99%

### Taille de la population (facultative, pour une population finie)

`pop`

personnes · facultatif · intervalle: 10–100000000

### Pertes et refus anticipés (facultatifs)

`perdas`

% · facultatif · intervalle: 0–50

## Édition de la méthode

OMS/Lwanga–Lemeshow 1991:proportion unique, population finie, pertes, plafond;95% z1,959964

## Formule documentée

n0 = z² × p × (1 − p) / d²; z = 1,645 (90%), 1,96 (95%) ou 2,576 (99%); d = marge d’erreur absolue.

Population finie (N): n = n0 / \[1 + (n0 − 1) / N\]. Pertes: nfinal = n / (1 − proportion perdue). Tout arrondi vers le haut.

Précision numérique : Pour 95%, z=1,959964;1,96 ci-dessus est arrondi. Correction du cas de référence consignée dans la provenance du catalogue.

## Limites et population

Utilisez une proportion attendue et une marge d’erreur absolue, dans les unités indiquées, pour estimer une proportion avec un échantillonnage simple. Le niveau de confiance n’est pas la puissance statistique d’une comparaison. La correction pour population finie suppose une population définie ; elle n’intègre pas automatiquement les grappes, la stratification ou un effet de plan. L’inflation pour pertes augmente le recrutement, mais n’élimine pas le biais de non-réponse. Cette interface n’a pas validé l’approximation normale ni l’intégralité du manuel WHO 1991 pour chaque plan.

## Références

- [Lwanga SK, Lemeshow S. Sample size determination in health studies: a practical manual. Organização Mundial da Saúde, 1991.](https://iris.who.int/handle/10665/40062)

- [Charan J, Biswas T. How to calculate sample size for different study designs in medical research? Indian J Psychol Med, 2013.](https://doi.org/10.4103/0253-7176.116232)

- [Charan/Biswas2013 original article content](https://www.yoursearchevidence.com/sites/g/files/vrxlpx50391/files/2024-10/M2_ParticularidadesInvestigacion.pdf)

## Reproduire les tests techniques

Exécutez node test.cjs dans le répertoire racine de ce dépôt pour reproduire les cas synthétiques enregistrés. Les données d’entrée, les résultats attendus et les tolérances d’origine sont conservés. Les tests techniques ne constituent pas une validation clinique.

```sh
node test.cjs
```

tool.json contient les sources, l’édition et le périmètre de la revue. examples.json conserve les données d’entrée et les résultats attendus des cas synthétiques ; results.json consigne les résultats obtenus.

[Fiche et références](../tool.json) · [Code JavaScript](../calculator.js) · [Cas de référence](../examples.json) · [results.json](../results.json)

## Revue et conditions d’utilisation

Aucune révision clinique indépendante n’a été effectuée.

Cette interface est une traduction réalisée par nos soins, et non une édition officielle ou certifiée. La revue clinique indépendante, la révision linguistique professionnelle et l’autorisation des droits sur les instruments n’ont pas été réalisées.

Résultat de la formule ou de la classification. L’interprétation, la conduite et l’applicabilité dépendent de l’évaluation professionnelle et de la source sélectionnée.

## Licence et attribution

Apache-2.0 s’applique uniquement au code d’ELUCENIA. Les droits sur les instruments, publications, traductions et données restent ceux de leurs titulaires respectifs. Conservez LICENSE et NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

## Résultats documentés

Les informations ci-dessous conservent les sorties de la méthode pour des exemples synthétiques. Elles ne constituent pas une validation clinique indépendante.

### 1

Échantillon nécessaire pour estimer 20,0 % ± 5,0 points de pourcentage avec une confiance de 95 %

| Détails du résultat | |
| --- | --- |
| Échantillon sans correction (population infinie) | 246 |

Formule pour un échantillonnage aléatoire simple. En échantillonnage en grappes, multiplier par l’effet de plan (généralement 1,5 à 2).


### 2

Échantillon nécessaire pour estimer 50,0 % ± 5,0 points de pourcentage avec une confiance de 95 %

| Détails du résultat | |
| --- | --- |
| Échantillon sans correction (population infinie) | 385 |
| Avec correction pour population finie (N = 1000) | 278 |

Formule pour un échantillonnage aléatoire simple. En échantillonnage en grappes, multiplier par l’effet de plan (généralement 1,5 à 2).


### 3

Échantillon nécessaire pour estimer 50,0 % ± 5,0 points de pourcentage avec une confiance de 95 %

| Détails du résultat | |
| --- | --- |
| Échantillon sans correction (population infinie) | 385 |
| En ajoutant 10 % de pertes | 428 |

Formule pour un échantillonnage aléatoire simple. En échantillonnage en grappes, multiplier par l’effet de plan (généralement 1,5 à 2).


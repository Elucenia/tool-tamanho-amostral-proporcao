<!-- ELUCENIA technical documentation · tamanho-amostral-proporcao · es · no clinical/professional/rights approval -->

# Tamaño de muestra para estimar una proporción

[condiciones, fuentes y permisos](https://elucenia.org/es/herramientas/tamanho-amostral-proporcao)

## Cómo usar

Utilice la herramienta en el portal o abra index.html mediante un servidor HTTP local. Seleccione el idioma, complete los campos y calcule.

## Entradas y unidades

### Proporción esperada (si se desconoce, use 50%)

`p`

% · intervalo: 1–99

### Margen de error absoluto (precisión)

`d`

puntos % · intervalo: 0,5–30

### Nivel de confianza

`conf`

- `90` — 90%
- `95` — 95%
- `99` — 99%

### Tamaño de la población (opcional, para población finita)

`pop`

personas · opcional · intervalo: 10–100000000

### Pérdidas y rechazos previstos (opcional)

`perdas`

% · opcional · intervalo: 0–50

## Edición del método

OMS/Lwanga–Lemeshow 1991:proporción única, población finita, pérdidas, techo;95% z1,959964

## Fórmula documentada

n0 = z² × p × (1 − p) / d²; z = 1,645 (90%), 1,96 (95%) o 2,576 (99%); d = margen de error absoluto.

Población finita (N): n = n0 / \[1 + (n0 − 1) / N\]. Pérdidas: nfinal = n / (1 − proporción perdida). Todos redondeados hacia arriba.

Precisión numérica: Para 95%, z=1,959964;1,96 arriba es presentación redondeada. Corrección del caso de referencia registrada en procedencia del catálogo.

## Límites y población

Use una proporción esperada y un margen de error absoluto, en las unidades indicadas, para estimar una proporción mediante muestreo simple. El nivel de confianza no es la potencia estadística de una comparación. La corrección por población finita presupone una población definida; no incorpora automáticamente conglomerados, estratificación ni efecto de diseño. La inflación por pérdidas aumenta el reclutamiento, pero no elimina el sesgo de no respuesta. Esta interfaz no ha validado la aproximación normal ni el manual WHO 1991 íntegro para cada diseño.

## Referencias

- [Lwanga SK, Lemeshow S. Sample size determination in health studies: a practical manual. Organização Mundial da Saúde, 1991.](https://iris.who.int/handle/10665/40062)

- [Charan J, Biswas T. How to calculate sample size for different study designs in medical research? Indian J Psychol Med, 2013.](https://doi.org/10.4103/0253-7176.116232)

- [Charan/Biswas2013 original article content](https://www.yoursearchevidence.com/sites/g/files/vrxlpx50391/files/2024-10/M2_ParticularidadesInvestigacion.pdf)

## Reproducir las pruebas técnicas

Ejecute node test.cjs en el directorio raíz de este repositorio para repetir los casos sintéticos registrados. Se conservan las entradas, los resultados esperados y las tolerancias originales. Las pruebas técnicas no constituyen validación clínica.

```sh
node test.cjs
```

tool.json contiene las fuentes, la edición y el alcance de la revisión. examples.json conserva las entradas y los resultados esperados de los casos sintéticos; results.json registra los resultados obtenidos.

[Ficha y referencias](../tool.json) · [Código JavaScript](../calculator.js) · [Casos de referencia](../examples.json) · [results.json](../results.json)

## Revisión y condiciones de uso

No se ha realizado una revisión clínica independiente.

Esta interfaz es una traducción de elaboración propia, no una edición oficial o certificada. No se han realizado la revisión clínica independiente, la revisión lingüística profesional ni la autorización de derechos de los instrumentos.

Resultado de la fórmula o clasificación. La interpretación, la conducta y la aplicabilidad dependen de la evaluación profesional y de la fuente seleccionada.

## Licencia y atribución

Apache-2.0 se aplica únicamente al código de ELUCENIA. Los derechos de los instrumentos, publicaciones, traducciones y datos permanecen en manos de sus respectivos titulares. Conserve LICENSE y NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

## Resultados documentados

La información siguiente conserva las salidas del método para ejemplos sintéticos. No constituye una validación clínica independiente.

### 1

Muestra necesaria para estimar 20,0% ± 5,0 puntos porcentuales con 95% de confianza

| Detalles del resultado | |
| --- | --- |
| Muestra sin corrección (población infinita) | 246 |

Fórmula para muestreo aleatorio simple. En el muestreo por conglomerados, multiplíquese por el efecto del diseño (en general 1,5 a 2).


### 2

Muestra necesaria para estimar 50,0% ± 5,0 puntos porcentuales con 95% de confianza

| Detalles del resultado | |
| --- | --- |
| Muestra sin corrección (población infinita) | 385 |
| Con corrección para población finita (N = 1000) | 278 |

Fórmula para muestreo aleatorio simple. En el muestreo por conglomerados, multiplíquese por el efecto del diseño (en general 1,5 a 2).


### 3

Muestra necesaria para estimar 50,0% ± 5,0 puntos porcentuales con 95% de confianza

| Detalles del resultado | |
| --- | --- |
| Muestra sin corrección (población infinita) | 385 |
| Añadiendo 10% de pérdidas | 428 |

Fórmula para muestreo aleatorio simple. En el muestreo por conglomerados, multiplíquese por el efecto del diseño (en general 1,5 a 2).


<!-- ELUCENIA technical documentation · tamanho-amostral-proporcao · pt-BR · no clinical/professional/rights approval -->

# Tamanho amostral para estimar uma proporção

[condições, fontes e permissões](https://elucenia.org/pt-br/ferramentas/tamanho-amostral-proporcao)

## Como usar

Use a ferramenta no portal ou abra index.html em um servidor HTTP local. Selecione o idioma, preencha os campos e calcule.

## Entradas e unidades

### Proporção esperada (se desconhecida, use 50%)

`p`

% · intervalo: 1–99

### Margem de erro absoluta (precisão)

`d`

pontos % · intervalo: 0,5–30

### Nível de confiança

`conf`

- `90` — 90%
- `95` — 95%
- `99` — 99%

### Tamanho da população (opcional, para população finita)

`pop`

pessoas · opcional · intervalo: 10–100000000

### Perdas e recusas previstas (opcional)

`perdas`

% · opcional · intervalo: 0–50

## Edição do método

WHO/Lwanga Lemeshow 1991:proporçãoúnica, correçãopopulaçãofinita, perdas, teto; z 95%1,959964

## Fórmula documentada

n0 = z² × p × (1 − p) / d², com z = 1,645 (90%), 1,96 (95%) ou 2,576 (99%) e d = margem de erro absoluta.

População finita (N): n = n0 / \[1 + (n0 − 1) / N\]. Perdas: nfinal = n / (1 − proporção de perdas). Todos os valores são arredondados para cima.

Precisão numérica: no cálculo de 95%, o quantil é z = 1,959964; 1,96 acima é sua apresentação arredondada. A correção do caso de referência está registrada na procedência do acervo.

## Limites e população

Use uma proporção esperada e uma margem de erro absoluta, nas unidades indicadas, para estimar uma proporção em amostragem simples. O nível de confiança não é poder estatístico de uma comparação. A correção de população finita pressupõe a população definida; não incorpora automaticamente conglomerados, estratificação ou efeito de desenho. A inflação para perdas aumenta o recrutamento, mas não elimina viés de não resposta. A aproximação normal e a íntegra do manual WHO 1991 não foram validadas para cada desenho por esta interface.

## Referências

- [Lwanga SK, Lemeshow S. Sample size determination in health studies: a practical manual. Organização Mundial da Saúde, 1991.](https://iris.who.int/handle/10665/40062)

- [Charan J, Biswas T. How to calculate sample size for different study designs in medical research? Indian J Psychol Med, 2013.](https://doi.org/10.4103/0253-7176.116232)

- [Charan/Biswas2013 original article content](https://www.yoursearchevidence.com/sites/g/files/vrxlpx50391/files/2024-10/M2_ParticularidadesInvestigacion.pdf)

## Reproduzir os testes técnicos

Execute node test.cjs na pasta raiz deste repositório para repetir os casos sintéticos registrados. As entradas, expectativas e tolerâncias originais são preservadas. Testes técnicos não constituem validação clínica.

```sh
node test.cjs
```

tool.json contém fontes, edição e escopo de revisão. examples.json conserva as entradas e expectativas sintéticas; results.json registra os resultados obtidos.

[Ficha e referências](../tool.json) · [Código JavaScript](../calculator.js) · [Casos de referência](../examples.json) · [results.json](../results.json)

## Revisão e condições de uso

Revisão clínica independente não realizada.

Esta interface é uma tradução autoral, não uma edição oficial ou certificada. Revisão clínica independente, revisão linguística profissional e autorização de direitos de instrumentos não foram realizadas.

Resultado da fórmula ou classificação. Interpretação, conduta e aplicabilidade dependem da avaliação profissional e da fonte selecionada.

## Licença e atribuição

Apache-2.0 aplica-se somente ao código da ELUCENIA. Os instrumentos, publicações, traduções e dados mantêm os direitos dos respectivos titulares. Preserve LICENSE e NOTICE.

ELUCENIA · Felipe Guedes · Copyright © 2026

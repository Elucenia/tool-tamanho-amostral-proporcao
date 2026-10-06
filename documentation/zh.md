<!-- ELUCENIA technical documentation · tamanho-amostral-proporcao · zh · no clinical/professional/rights approval -->

# 估计比例的样本量

[条件、来源与许可](https://elucenia.org/zh/tools/tamanho-amostral-proporcao)

## 使用方法

在门户中使用工具，或通过本地 HTTP 服务器打开 index.html。选择语言，填写各字段，然后计算。

## 输入与单位

### 预期比例（未知时用 50%）

`p`

% · 范围: 1–99

### 绝对误差限（精度）

`d`

百分点 · 范围: 0.5–30

### 置信水平

`conf`

- `90` — 90%
- `95` — 95%
- `99` — 99%

### 总体大小（可选，用于有限总体）

`pop`

人 · 选填 · 范围: 10–100000000

### 预期失访及拒绝率（可选）

`perdas`

% · 选填 · 范围: 0–50

## 方法版本

WHO/Lwanga–Lemeshow 1991：单比例、有限总体校正、失访、上取整；95% z1.959964

## 已记录的公式

n0 = z² × p × (1 − p) / d²; z = 1.645 (90%), 1.96 (95%) 或 2.576 (99%); d = 绝对误差.

有限总体（N）: n = n0 / \[1 + (n0 − 1) / N\]. 失访: nfinal = n / (1 − 失访比例). 全部向上取整。

数值精度： 95%计算使用z=1.959964；上文1.96为四舍五入后的显示值。参考案例校正记录于目录溯源。

## 限制与适用人群

请使用预期比例和指定单位下的绝对误差范围，在简单抽样条件下估计比例。置信水平不是比较检验的统计效能。有限总体校正以明确定义的总体为前提，不会自动包含整群、分层或设计效应。针对失访增加人数会提高招募量，但不能消除无应答偏倚。此界面并未针对每一种设计验证正态近似或完整的 WHO 1991 手册。

## 参考文献

- [Lwanga SK, Lemeshow S. Sample size determination in health studies: a practical manual. Organização Mundial da Saúde, 1991.](https://iris.who.int/handle/10665/40062)

- [Charan J, Biswas T. How to calculate sample size for different study designs in medical research? Indian J Psychol Med, 2013.](https://doi.org/10.4103/0253-7176.116232)

- [Charan/Biswas2013 original article content](https://www.yoursearchevidence.com/sites/g/files/vrxlpx50391/files/2024-10/M2_ParticularidadesInvestigacion.pdf)

## 复现技术测试

在此仓库的根目录中运行 node test.cjs，以重复已记录的合成案例。原始输入、预期结果和容差保持不变。技术测试不构成临床验证。

```sh
node test.cjs
```

tool.json 包含来源、版本和审查范围。examples.json 保留合成输入与预期结果；results.json 记录实际得到的结果。

[记录与参考文献](../tool.json) · [JavaScript代码](../calculator.js) · [参考案例](../examples.json) · [results.json](../results.json)

## 审查与使用条件

尚未开展独立临床审查。

此界面为自主编写的翻译，并非官方或认证版本。尚未完成独立临床审查、专业语言审查或工具权利授权。

公式或分类结果。解释、处理及适用性须结合专业评估和所选来源。

## 许可与署名

Apache-2.0 仅适用于 ELUCENIA 代码。工具、出版物、翻译和数据的权利仍归各自权利人所有。请保留 LICENSE 和 NOTICE。

ELUCENIA · Felipe Guedes · Copyright © 2026

## 已记录的结果

以下信息保留该方法对合成示例的输出，不构成独立的临床验证。

### 1

以95%置信度估计20.0% ± 5.0个百分点所需的样本量

| 结果详情 | |
| --- | --- |
| 未校正样本（无限总体） | 246 |

简单随机抽样公式。在整群抽样中，乘以设计效应（通常为1.5至2）。


### 2

以95%置信度估计50.0% ± 5.0个百分点所需的样本量

| 结果详情 | |
| --- | --- |
| 未校正样本（无限总体） | 385 |
| 采用有限总体校正（N = 1000） | 278 |

简单随机抽样公式。在整群抽样中，乘以设计效应（通常为1.5至2）。


### 3

以95%置信度估计50.0% ± 5.0个百分点所需的样本量

| 结果详情 | |
| --- | --- |
| 未校正样本（无限总体） | 385 |
| 加上10%的损耗 | 428 |

简单随机抽样公式。在整群抽样中，乘以设计效应（通常为1.5至2）。


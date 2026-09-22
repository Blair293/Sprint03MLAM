# Sprint03MLAM

O projeto utiliza uma base de dados contendo informações numéricas e aplica conceitos de **Distribuição Normal, Probabilidade e Regressão Linear**.

---

## Integrantes

| Nome                 | RM      |
| -------------------- | ------- |
| Arthur Araujo Massarioli | RM 573308 |
| Daniel Alejandro Pupo Martínez | RM 573075 |
| Victor Hugo Lavaqui | RM 573838 |
| Wendel Pedro Rezende | RM 573126 |

---

## Objetivo

Realizar análises estatísticas utilizando Python a partir de uma base de dados numérica, considerando:

1. Probabilidade de ocorrência de valores acima da mediana;
2. Probabilidade de ocorrência de valores dentro do intervalo definido pela média ± 2 desvios-padrão;
3. Modelagem utilizando Regressão Linear;
4. Interpretação dos resultados estatísticos e do modelo de aprendizado de máquina.

---

## Base de Dados

A base utilizada no projeto é:

`amostra_chargegrid.xlsx`

A base contém **120 registros e 8 variáveis**.

Entre as variáveis numéricas disponíveis, foram selecionadas:

* `renewables_share_energy`
* `population`
* `gdp`

A variável `renewables_share_energy` foi utilizada nas análises de probabilidade.

Para a Regressão Linear foram utilizadas:

* **Variável independente (X):** `population`
* **Variável dependente (Y):** `gdp`

---

# Análise 01 — Probabilidade acima da Mediana

Para esta análise foi selecionada a variável:

`renewables_share_energy`

Foi calculada a mediana da variável e, considerando a hipótese de que os dados seguem uma **Distribuição Normal**, foi estimada a probabilidade de ocorrência de valores superiores à mediana.

### Resultados

* Média: **9,7419**
* Desvio-padrão: **12,0478**
* Mediana: **4,3085**
* Probabilidade de X > Mediana: **67,40%**
* Classificação: **Provável**

A probabilidade foi calculada utilizando a função de distribuição acumulada da Normal (`norm.cdf`) da biblioteca `scipy.stats`.

---

# Análise 02 — Probabilidade no intervalo Média ± 2s

Na segunda análise foi calculado o intervalo formado pela média mais ou menos dois desvios-padrão:

$$
[\mu - 2\sigma,\ \mu + 2\sigma]
$$

Para `renewables_share_energy`, foram obtidos os seguintes valores:

* Média: **9,7419**
* Desvio-padrão: **12,0478**
* Limite inferior: **-14,3537**
* Limite superior: **33,8375**

Considerando a Distribuição Normal, a probabilidade de uma observação estar dentro desse intervalo é:

**95,45%**

Classificação:

**Quase certo**

> Observação: o limite inferior negativo ocorre devido à hipótese de Distribuição Normal. Na variável original, valores negativos de participação de energia renovável não possuem interpretação prática. Portanto, esse resultado representa uma característica da aproximação pela distribuição Normal e deve ser considerado na interpretação.

---

# Análise 03 — Regressão Linear

Para a modelagem de Regressão Linear foram selecionadas duas variáveis numéricas:

* `population` — variável independente;
* `gdp` — variável dependente.

Para facilitar a interpretação, os valores foram convertidos para:

* População → milhões de habitantes;
* PIB → bilhões.

O modelo utilizado foi:

$$
Y = \beta_0 + \beta_1X
$$

O modelo obtido foi aproximadamente:

$$
PIB = 380,4850 + 4,2579 \times População
$$

### Interpretação dos coeficientes

O **intercepto**, aproximadamente **380,4850**, representa o valor estimado do PIB quando a população assume valor zero dentro da formulação matemática do modelo.

O **coeficiente angular**, aproximadamente **4,2579**, indica que, no modelo ajustado, um aumento de **1 milhão de habitantes** está associado a um aumento estimado de aproximadamente **4,26 bilhões** no PIB.

Essa interpretação representa uma **associação estatística** entre as variáveis e não permite concluir, isoladamente, que o aumento da população cause o aumento do PIB.

### Coeficiente de determinação

O modelo apresentou:

**R² = 0,4352**

Isso significa que aproximadamente **43,52% da variabilidade observada no PIB** é explicada pela variável população no modelo linear utilizado.

Os demais **56,48%** estão associados a outros fatores e à variabilidade não explicada pelo modelo.

---

# Gráfico da Regressão

O projeto contém um gráfico de dispersão apresentando os dados observados e a reta de regressão linear ajustada.

O gráfico possui:

* Título;
* Identificação do eixo X;
* Identificação do eixo Y;
* Legenda;
* Dados observados;
* Reta de regressão.

---

# Tecnologias e Bibliotecas

O projeto foi desenvolvido utilizando **Python**.

Principais bibliotecas utilizadas:

* [Pandas](https://pandas.pydata.org/) — manipulação e análise dos dados;
* [NumPy](https://numpy.org/) — operações numéricas;
* [Matplotlib](https://matplotlib.org/) — criação dos gráficos;
* [SciPy](https://scipy.org/) — cálculos relacionados à Distribuição Normal;
* [Scikit-learn](https://scikit-learn.org/) — implementação e avaliação da Regressão Linear.

---

# Conclusão

A análise permitiu aplicar conceitos de estatística descritiva, Distribuição Normal, probabilidade e aprendizado de máquina.

A análise de probabilidade mostrou como a média e o desvio-padrão podem ser utilizados para estimar a ocorrência de determinados eventos quando se assume uma Distribuição Normal.

Na Regressão Linear, foi possível analisar a relação entre população e PIB por meio de um modelo matemático, além de visualizar graficamente os dados e interpretar os coeficientes obtidos.

O projeto demonstra, dessa forma, a utilização de **Python para análise estatística e modelagem preditiva**, relacionando conceitos estatísticos com técnicas introdutórias de aprendizado de máquina.

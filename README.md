
# 📊 Análise Exploratória dos Acidentes Rodoviários no Brasil (2023-2024)

Este notebook realiza uma **análise exploratória dos dados de acidentes rodoviários** no Brasil, nos anos de **2023 e 2024**, utilizando dados públicos extraídos do [Kaggle](https://www.kaggle.com/).

---

## 🔍 Objetivos da análise

A proposta é entender melhor o comportamento dos acidentes rodoviários, suas causas, locais de maior incidência e gravidade. Para isso, foram utilizados os seguintes métodos de análise:

- 📋 **Visão geral dos dados**: `shape`, `head`, `tail`, `sample`, `dtypes`
- 📈 **Resumo estatístico**: `describe()`
- 📊 **Visualizações gráficas**:
  - Variáveis quantitativas: histogramas, boxplots
  - Variáveis qualitativas: gráficos de barras, colunas, linhas e pizza
- 📚 **Agrupamento de dados** com `groupby()`

---

## 🧾 Fonte de dados

- Arquivo: `datatran.csv`
- Caminho: `/content/drive/MyDrive/Colab Notebooks/2025/analise_exploratoria_acidentes_rodovia/input/datatran.csv`
- Total de registros: `140.922`
- Total de colunas: `30`

---

## 📁 Bibliotecas utilizadas

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import datetime as dt
```

---

## 📄 Estrutura do DataFrame

```python
df.columns
```

- `id`, `data_inversa`, `dia_semana`, `horario`, `uf`, `br`, `km`, `municipio`,  
  `causa_acidente`, `tipo_acidente`, `classificacao_acidente`, `fase_dia`, `sentido_via`,  
  `condicao_metereologica`, `tipo_pista`, `tracado_via`, `uso_solo`,  
  `pessoas`, `mortos`, `feridos_leves`, `feridos_graves`, `ilesos`, `ignorados`,  
  `feridos`, `veiculos`, `latitude`, `longitude`, `regional`, `delegacia`, `uop`

---

## 📐 Dimensões do DataFrame

```python
df.shape
# Resultado: (140922, 30)
```

---

## 👁️‍🗨️ Amostra dos dados

```python
df.head()      # Primeiras 5 linhas  
df.tail()      # Últimas 5 linhas  
df.sample()    # Uma linha aleatória
```

---

## 🧾 Tipos de dados

```python
df.dtypes
```

- `float64`: id  
- `object`: data, hora, cidade, etc.  
- `int64`: contagens de feridos, mortos, veículos etc.

---

## 📊 Estatísticas descritivas

```python
df.describe()
```

Métricas como `média`, `mínimo`, `máximo`, `quartis` e `desvio padrão` para as colunas numéricas, como:

- `pessoas`, `mortos`, `feridos`, `veiculos`, etc.

---

## ⚠️ Verificação de dados faltantes

```python
df.isnull().sum()
```

- `classificacao_acidente`: 2 nulos  
- `regional`: 20 nulos  
- Demais colunas: sem valores ausentes

---

## 📌 Observações

- Algumas colunas foram carregadas com tipos mistos (`km`, `latitude`, `longitude`) e podem precisar de limpeza adicional.
- A base contém dados geográficos que possibilitam **análises espaciais** (ex: mapas de calor).
- A análise poderá ser expandida com modelos de predição, agrupamentos ou dashboards interativos.

---

## 🧠 Próximos passos

- Tratar e padronizar colunas com tipos inconsistentes.
- Mapear a distribuição por estado e município.
- Gerar dashboards interativos com `Plotly` ou `Streamlit`.
- Analisar sazonalidade (por data e horário).

---

## 📌 Autor

**André Rodrigues**  
[LinkedIn](https://www.linkedin.com/in/andrerodriguesdados) | [GitHub](https://github.com/seuusuario)

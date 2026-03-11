# Análise de Campanhas de Marketing

Análise exploratória multivariada de dados de clientes para identificar os fatores que influenciam a aceitação de campanhas de marketing e o comportamento de consumo por categoria de produto.

---

## Objetivo

Entender **por que um cliente aceita ou não uma campanha de marketing** e quais variáveis — demográficas, comportamentais e financeiras — melhor explicam essa decisão.

---

## Dataset

Arquivo: `dataset.csv`

O dataset contém **dados de clientes** com as seguintes informações:

| Grupo | Variáveis |
|---|---|
| **Demográfico** | Ano de nascimento, nível educacional, estado civil |
| **Financeiro** | Renda anual |
| **Familiar** | Número de crianças e adolescentes em casa |
| **Comportamento de compra** | Gastos por categoria (vinhos, frutas, carnes, peixes, doces, outros) |
| **Canal de compra** | Web, catálogo, loja física |
| **Engajamento** | Aceitação de 6 campanhas distintas, visitas ao site |

---

## Estrutura do Projeto

```
marketing-analise/
├── dataset.csv                  # Base de dados dos clientes
├── analise_marketing.ipynb      # Notebook principal da análise
├── requirements.txt             # Dependências do projeto
└── README.md                    # Documentação do projeto
```

---

## Metodologia

O notebook `analise_marketing.ipynb` está organizado nas seguintes etapas:

1. **Configuração do Ambiente** — importações e configurações globais
2. **Carregamento dos Dados** — leitura do CSV e inspeção inicial
3. **Limpeza dos Dados** — padronização de tipos, detecção de outliers via IQR, imputação de valores ausentes com KNN Imputer
4. **Engenharia de Features** — criação de variáveis derivadas (Idade, Dias_Como_Cliente, TotalCompras, Gasto_Total, RespostaCampanha)
5. **Visão Geral Exploratória** — histogramas e boxplots de todas as variáveis
6. **Perguntas de Negócio** — análises direcionadas a 8 perguntas estratégicas
7. **Importância das Features** — modelo Random Forest para identificar as variáveis mais relevantes
8. **Teste de Hipóteses** — Shapiro-Wilk + Mann-Whitney U para comparar renda por nível educacional
9. **Conclusões e Recomendações**

---

## Principais Resultados

- Os fatores com maior influência na aceitação de campanhas são **Gasto Total**, **Renda** e **Dias como Cliente**.
- Clientes com maior engajamento histórico e renda mais elevada têm maior probabilidade de converter.
- O **Teste de Mann-Whitney U** confirmou diferença estatisticamente significativa na renda entre clientes com e sem nível superior (p < 0,05).
- As campanhas com maior taxa de sucesso foram as **Campanhas 5 e 1**.
- A categoria de produto com maior gasto acumulado foi **Vinhos**, seguida de **Carnes**.

---

## Como Executar

### Pré-requisitos

- Python 3.9 ou superior
- pip

### Instalação

```bash
# Clone o repositório
git clone https://github.com/julianaloureng/marketing-analise.git
cd marketing-analise

# Crie e ative o ambiente virtual
python -m venv .venv
.venv\Scripts\activate  # Windows
# source .venv/bin/activate  # Linux/macOS

# Instale as dependências
pip install -r requirements.txt
```

### Execução

Abra o notebook no VS Code ou Jupyter:

```bash
jupyter notebook analise_marketing.ipynb
```

---

## Tecnologias Utilizadas

| Biblioteca | Finalidade |
|---|---|
| `pandas` | Manipulação e transformação de dados |
| `numpy` | Operações numéricas |
| `matplotlib` | Visualização de dados |
| `seaborn` | Visualizações estatísticas |
| `missingno` | Análise visual de valores ausentes |
| `scipy` | Testes estatísticos (Shapiro-Wilk, Mann-Whitney U) |
| `scikit-learn` | Imputação KNN e modelo Random Forest |

---


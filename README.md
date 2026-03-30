# Serasa Crédito Analytics Case

[![Python Version](https://img.shields.io/badge/python-3.10+-blue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)]()
[![Status](https://img.shields.io/badge/status-Concluído-success)]()
[![Time](https://img.shields.io/badge/desenvolvido_em-2_dias-orange)]()

**Case completo de Analytics & Otimização para Serasa Experian**
Previsão de conversão via GLM + Otimização de alocação de ofertas via MILP, tudo com arquitetura Medallion, versionamento e apresentação executiva.

## Sobre o Projeto

Este repositório contém a solução **end-to-end** desenvolvida para o case de **Analista de Estratégia de Dados Sênior** (ou Especialista) da Serasa Experian.

**Objetivo principal:**

Realocar as 18,13 milhões de ofertas de crédito de forma inteligente, **mantendo o mesmo volume total**, para **maximizar a receita gerada** através de maior taxa de conversão.

**Principais entregas:**

* Arquitetura **Medallion** completa (Raw → Bronze → Silver → Gold)
* Modelo de previsão de conversão via **GLM (Binomial + Logit)**
* Otimização de alocação via **MILP (Mixed-Integer Linear Programming)**
* Dashboard interativo no **Power BI**
* Apresentação executiva completa
* Documentação técnica e formulação matemática
* Versionamento limpo no GitHub

**Tempo total de desenvolvimento:** 2 dias

## Estrutura de Pastas

```
SERASA-CREDITO-ANALYTICS-CASE/
├── application/
│   └── power_bi/
│       └── Serasa_Credito_Analise.pbix
├── data/
│   ├── raw/
│   │   └── SerasaCredito - Case.xlsx
│   ├── bronze/
│   ├── silver/
│   └── gold/
├── docs/
│   ├── case_brief.md
│   └── formulacao_matematica.md
├── notebooks/
│   ├── 01_eda_exploratorio.ipynb
│   ├── 02_bronze_layer.ipynb
│   ├── 03_silver_layer.ipynb
│   ├── 04_gold_layer.ipynb
│   ├── 05_glm.ipynb
│   ├── 06_opt_oferta_credito.ipynb
│   └── 07_eda_pos_opt.ipynb
├── presentation/
│   └── Case Serasa - Eduardo Zanutti.pdf
├── images/
├── .gitignore
├── LICENSE
└── README.md
```

## Como Utilizar o Repositório

1. **Clone o repositório**

```bash
git clone https://github.com/eduardozanutti/serasa-credito-analytics-case.git
cd serasa-credito-analytics-case
```

2. **Instale as dependências**

```bash
pip install -r requirements.txt
```

*(caso não tenha o arquivo, as principais bibliotecas são: pandas, numpy, pyomo, scikit-learn, seaborn, matplotlib, openpyxl)*

3. **Execute os notebooks na ordem**

* 01_eda_exploratorio.ipynb
* 02_bronze_layer.ipynb → 03_silver_layer.ipynb → 04_gold_layer.ipynb
* 05_glm.ipynb (modelagem de conversão)
* 06_opt_oferta_credito.ipynb (otimização MILP)
* 07_eda_pos_opt.ipynb

4. **Abra o dashboard**
   Abra o arquivo `Serasa_Credito_Analise.pbix` no Power BI Desktop

5. **Leia a documentação**

* `docs/case_brief.md` → briefing do case
* `docs/formulacao_matematica.md` → formulação completa do MILP

## Tecnologias Utilizadas

* Python 3.10+
* Pandas / NumPy – manipulação de dados
* Pyomo + CPLEX – otimização MILP
* Statsmodels – GLM (previsão de conversão)
* Power BI – dashboard interativo
* Medallion Architecture – Bronze, Silver e Gold layers
* Git + GitHub – versionamento e boas práticas

## Resultados Alcançados

* Taxa de conversão: 3,87% → 36,44%
* Receita mensal: R$ 2,73 milhões → R$ 494,2 milhões
* Ganho total: + R$ 491,47 milhões (+17.902%)

## Autor

**Eduardo Soares Zanutti**

Data Analyst | Analytics Engineer | Mestrando em Estatística Aplicada

LinkedIn: linkedin.com/in/eduardo-zanutti


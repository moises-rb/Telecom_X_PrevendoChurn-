# 🚀 Projeto de Previsão de Churn em uma Empresa de Telecomunicações

## 📖 Visão Geral

Este projeto tem como objetivo principal desenvolver um modelo de Machine Learning para prever o **Churn de Clientes (evasão)** em uma empresa de telecomunicações. A partir de um conjunto de dados históricos, o projeto percorre todas as etapas de um pipeline de Ciência de Dados — da Análise Exploratória (EDA) e pré-processamento até a construção, otimização e interpretação de um modelo preditivo.

O projeto foi construído em duas versões:

- **V1 (Baseline)**: Implementação inicial do modelo, servindo como ponto de partida.
- **V2 (Otimizada e Refatorada)**: Versão aprimorada com técnicas avançadas como balanceamento de dados (SMOTE), otimização de hiperparâmetros e interpretação do modelo com SHAP.

---

## 🎯 Objetivo

Construir um modelo de **classificação** capaz de identificar clientes com alta probabilidade de churn, fornecendo à empresa uma ferramenta para tomar **decisões proativas de retenção**, com base em **insights claros** sobre os fatores que influenciam a evasão.

---

## 🛠️ Metodologia

A metodologia segue um pipeline de Machine Learning estruturado, documentado em notebooks:

### 🔍 1. Análise Exploratória e Pré-processamento
- Limpeza e tratamento de dados faltantes e inconsistentes.
- Análise de correlação e distribuição das variáveis.
- Codificação de variáveis categóricas e padronização das numéricas.

### 🤖 2. Modelagem V1 (Baseline)
- Separação dos dados em treino e teste.
- Treinamento de um modelo `RandomForestClassifier` sem otimizações.
- Avaliação com **Acurácia**, **F1-Score** e **AUC**.

### 🚀 3. Modelagem V2 (Otimização e Interpretação)
- **Balanceamento de Dados**: Técnica SMOTE aplicada para corrigir desbalanceamento.
- **Otimização de Hiperparâmetros**: Utilização de `RandomizedSearchCV`.
- **Ajuste de Threshold**: Maximização do F1-Score com corte ideal.
- **Interpretabilidade (SHAP)**: Análise da importância das features com `summary_plot` e `force_plot`.

### 📊 4. Conclusão e Comparação
- Comparação das métricas entre as versões V1 e V2.
- Geração de previsões para clientes simulados.
- Recomendações estratégicas para o negócio com base nos insights.

---

## 📂 Estrutura do Repositório

```
.
├── data/
│   ├── raw/
│   │   └── df_final.csv             # Dataset original
│   ├── processed/
│   │   └── split/                   # Conjuntos de treino e teste
├── models/
│   ├── preprocessing/               # Artefatos do pré-processamento
│   ├── final_model/                 # Modelo V1 (baseline)
│   └── final_model_v2/              # Modelo V2 (otimizado e refatorado)
├── notebooks/
│   ├── 01_EDA_e_PreProcessamento.ipynb
│   ├── 02_Modelagem_V1.ipynb
│   ├── 03_Otimizacao_e_Interpretacao_v2.ipynb
│   └── 04_Simulacao_e_Conclusao_v2.ipynb
├── reports/
│   ├── v2/                          # Métricas e gráficos do modelo V2
│   └── ...
└── README.md
```

---

## 📈 Resultados e Conclusões

O modelo **V2 (Otimizado e Refatorado)** obteve desempenho superior ao baseline, especialmente nas métricas mais relevantes:

| Métrica              | Modelo V1 | Modelo V2 |
|----------------------|-----------|-----------|
| **Accuracy**         | 0.73      | 0.73      |
| **Precision**        | 0.64      | 0.70      |
| **Recall**           | 0.53      | 0.76      |
| **F1-Score**         | 0.58      | 0.70      |
| **AUC**              | 0.84      | 0.82      |
| **Threshold Ótimo**  | —         | 0.35      |
| **n_estimators**     | 100       | 300       |
| **max_depth**        | —         | None      |
| **min_samples_split**| —         | 2         |
| **min_samples_leaf** | —         | 1         |

> 🔎 *Fonte: `comparacao_modelos_base.csv` e `final_model_metrics_v2.json`*

### 🔎 Principais Insights com SHAP:
- **Contract_Month-to-month**: Clientes com contrato mensal têm maior propensão ao churn.
- **tenure**: Clientes com menor tempo de serviço são mais propensos a evadir.
- **OnlineSecurity_No**: A ausência de segurança online está fortemente associada ao churn.

### 🎯 Ações Estratégicas Sugeridas:
- Oferecer descontos para contratos mensais.
- Criar planos personalizados de fidelização para novos clientes.
- Oferecer segurança online como benefício adicional.

---

## ⚙️ Como Executar o Projeto

### 1. Clone o repositório:

```bash
git clone https://github.com/seu_usuario/seu_repositorio.git
cd seu_repositorio
```

### 2. Crie e ative o ambiente virtual:

```bash
# Exemplo com conda
conda create --name churn_env python=3.9
conda activate churn_env
```

### 3. Instale as dependências:

```bash
pip install -r requirements.txt
```

> Obs.: Certifique-se de que o arquivo `requirements.txt` inclui as seguintes bibliotecas:
> `pandas`, `scikit-learn`, `imblearn`, `shap`, `matplotlib`, `seaborn`, `joblib`

### 4. Execute os notebooks:

Abra o Jupyter Notebook e execute os notebooks na seguinte ordem:

1. `01_EDA_e_PreProcessamento.ipynb`  
2. `02_Modelagem_V1.ipynb`  
3. `03_Otimizacao_e_Interpretacao_v2.ipynb`  
4. `04_Simulacao_e_Conclusao_v2.ipynb`

---

## 👨‍💻 Autor

**Moisés Ribeiro**  
📌 Ciência de Dados | Projetos | Processos

- [GitHub](https://github.com/moises-rb)  
- [LinkedIn](https://www.linkedin.com/in/moisesrsjr/)  
- [Medium](https://medium.com/@moises.rsjr)

---

## 📄 Licença

Este projeto está licenciado sob os termos da **MIT License** – veja o arquivo [LICENSE](LICENSE) para detalhes.

# Previsão de Rotatividade de Clientes (Churn Prediction)

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3+-green.svg)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-2.0+-red.svg)](https://xgboost.ai/)
[![License: Public](https://img.shields.io/badge/License-Public-yellow.svg)]

**Previsão de churn de clientes de telecomunicações usando Machine Learning - Projeto Didático Completo**

---

## Sobre o Projeto

Este projeto é um pipeline completo de Data Science para prever quais clientes de uma empresa de telecomunicações têm maior probabilidade de cancelar o serviço (*churn*), permitindo ações de retenção proativas.

O projeto aborda todas as etapas essenciais de um projeto de dados:
1. **Contextualização do problema de negócio**
2. **Análise Exploratória de Dados (EDA)**
3. **Limpeza e pré-processamento**
4. **Engenharia de features**
5. **Tratamento de desbalanceamento de classes**
6. **Modelagem** (Regressão Logística → Random Forest → XGBoost)
7. **Avaliação com métricas apropriadas** (não só acurácia!)
8. **Interpretação de resultados e importância das variáveis**
9. **Conclusões e próximos passos**

---

## Objetivo

**Pergunta de negócio:** *Dado o perfil e o histórico de um cliente, qual a probabilidade de ele cancelar o serviço no próximo período?*

**Por que isso importa:**
- Permite à empresa priorizar ações de retenção para clientes de alto risco
- Evita desperdiçar recursos de retenção em clientes que não iriam cancelar de qualquer forma
- Reduz o custo de aquisição de novos clientes (5 a 25x mais caro que reter um existente)

---

## Dataset

**Fonte:** [Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) (IBM Sample Dataset)

**Características:**
- **7.043** clientes
- **21** atributos
- **Desbalanceamento de classes:** ~73% não-churn vs ~27% churn

**Variáveis principais:**
- Demográficas: `gender`, `SeniorCitizen`, `Partner`, `Dependents`
- Serviços contratados: `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`
- Contrato: `Contract`, `PaperlessBilling`, `PaymentMethod`
- Financeiras: `MonthlyCharges`, `TotalCharges`
- Tempo de casa: `tenure`
- **Target:** `Churn` (Yes/No)

---

## Tecnologias Utilizadas

### Core
- **Python 3.11** - Linguagem principal
- **Jupyter Notebook** - Ambiente de desenvolvimento
- **Pandas / NumPy** - Manipulação e análise de dados
- **Matplotlib / Seaborn** - Visualização de dados

### Machine Learning
- **Scikit-learn** - Modelos base, pré-processamento e métricas
- **XGBoost** - Modelo de Gradient Boosting de alto desempenho
- **Imbalanced-learn** - Técnicas de balanceamento (SMOTE)

### Interpretabilidade
- **SHAP** (mencionado, para extensão futura) - Explicabilidade de modelos

---

## Estrutura do Projeto
```
previsao_de_rotatividade/
├── previsao_de_rotatividade.ipynb # Notebook principal com todo o pipeline
├── Telco-Customer-Churn.csv # Dataset utilizado
├── README.md # Este arquivo
└── requirements.txt # Dependências do projeto
```
---

## Como Executar

### 1. Clone o repositório

```
git clone https://github.com/saorim10/prev_rotatividade
cd prev_rotatividade
```
### 2. Instale as dependências
```
pip install -r requirements.txt
```
### 3. Execute o notebook
```
jupyter notebook previsao_de_rotatividade.ipynb
```

### Principais Insights

1. Tipo de contrato é o fator mais importante - clientes Month-to-month têm muito mais chance de churn
2. Tempo de casa (tenure) é crítico - clientes nos primeiros meses são os que mais cancelam
3. Método de pagamento Electronic check está associado a maior taxa de churn
4. Quanto mais serviços adicionais o cliente contrata, menor a probabilidade de churn

### Importância das Features (Top 5 - XGBoost)
1. Contract_Month-to-month - Contrato mensal
2. tenure - Tempo de casa
3. TotalCharges - Valor total pago
4. MonthlyCharges - Valor da mensalidade
5. PaymentMethod_Electronic check - Pagamento via boleto/cheque

### Aprendizados e Desafios
Desafios Superados
* Desbalanceamento de classes - Uso de class_weight e SMOTE
* Limpeza de dados - Correção de valores inconsistentes em TotalCharges
* Feature Engineering - Criação de variáveis derivadas com alto poder preditivo
* Escolha de métricas - Não usar acurácia como única métrica

### Próximos Passos (Extensões Futuras)
1. Tuning de hiperparâmetros com GridSearchCV ou Optuna
2. SHAP values para interpretabilidade individual das previsões
3. Ajuste do limiar de decisão com base no custo de negócio real
4. Deploy simples via Streamlit
5. Testar LightGBM ou CatBoost

### Contribuições
Contribuições são sempre bem-vindas! Sinta-se à vontade para:

* Reportar bugs
* Sugerir melhorias
* Enviar pull requests

### Licença
Este projeto está sob a licença MIT - veja o arquivo LICENSE para detalhes.

### Contato: 
Marcelo Saorim - marcelo.saoriml@gmail.com

### LinkedIn: 
[marcelo-rocha-saorim](https://www.linkedin.com/in/marcelo-rocha-saorim/)

### GitHub: 
[@saorim10](https://github.com/saorim10)

### Agradecimentos
* IBM pelo dataset público
* Kaggle pela plataforma de dados
* Comunidade de Data Science pelos recursos e inspiração
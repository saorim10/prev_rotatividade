# Previsão de Rotatividade de Clientes (Churn Prediction)

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3+-green.svg)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-2.0+-red.svg)](https://xgboost.ai/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

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

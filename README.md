# Credit Risk Prediction Project

Este projeto implementa um **pipeline completo de Ciência de Dados** para prever o risco de crédito de um solicitante, incluindo análise de dados, pré-processamento, comparação de modelos de Machine Learning e uma aplicação interativa desenvolvida em **Streamlit**.

---

## 📂 **1. Sobre o Dataset**

O dataset utilizado é composto por informações de clientes relacionadas a solicitações de crédito. Ele contém variáveis numéricas e categóricas que representam características pessoais, financeiras e comportamentais.

### 🔑 **Principais colunas do dataset**

* **Age** — Idade do solicitante
* **Sex** — Sexo (male/female)
* **Job** — Categoria profissional (0 a 3)
* **Housing** — Condição de moradia (own/rent/free)
* **Saving accounts** — Nível de poupança (little/moderate/rich/quite rich)
* **Checking account** — Conta corrente (little/moderate/rich)
* **Credit amount** — Valor solicitado de crédito
* **Duration** — Duração do empréstimo (em meses)
* **Risk** — Variável-alvo (good/bad)

O dataset passou por tratamento para lidar com **valores nulos**, formatação inconsistente e codificação das variáveis categóricas.

---

## 🔧 **2. Pipeline de Pré-processamento**

O pipeline foi construído seguindo boas práticas para garantir reprodutibilidade e escalabilidade.

Inclui as seguintes etapas:

* Remoção e tratamento de valores faltantes
* Conversão de tipos
* Codificação de variáveis categóricas usando **Label Encoding**
* Normalização quando necessário
* Separação entre treinamento e teste
* Salvamento dos encoders com **joblib**

---

## 🤖 **3. Modelagem de Machine Learning**

Foram testados diferentes algoritmos clássicos de classificação:

* **Decision Tree**
* **Random Forest**
* **Extra Trees Classifier**
* **XGBoost**

Após a comparação das métricas, o modelo escolhido para a aplicação final foi o **XGBoost**, por apresentar o melhor desempenho geral.

Todos os modelos e encoders utilizados no deploy foram salvos usando:

```python
joblib.dump(model, "xgb_credit_model.pkl")
```

---

## 🌐 **4. Aplicação Web com Streamlit**

O projeto inclui um aplicativo em **Streamlit** que permite ao usuário inserir os dados do solicitante e obter a classificação de risco em tempo real.

### Pontos principais da aplicação:

* Interface simples e funcional com campos numéricos e dropdowns
* Codificação automática das variáveis usando os encoders salvos
* Predição realizada pelo modelo XGBoost treinado
* Feedback visual indicando **GOOD** ou **BAD**

O arquivo principal da aplicação é o `app.py`.

---

## 🚀 **5. Como Executar o Projeto Localmente**

### **Pré-requisitos:**

* Python 3.9+
* pip instalado

### **Instalar dependências:**

```bash
pip install -r requirements.txt
```

### **Executar o app Streamlit:**

```bash
streamlit run app.py
```

Certifique-se de que os arquivos `.pkl` do modelo e encoders estão na mesma pasta.

---

## 📁 **6. Estrutura do Projeto**

```
📦 credit-risk-project
 ┣ 📜 app.py
 ┣ 📜 model_training.ipynb
 ┣ 📜 xgb_credit_model.pkl
 ┣ 📜 Sex_encoder.pkl
 ┣ 📜 Housing_encoder.pkl
 ┣ 📜 Saving accounts_encoder.pkl
 ┣ 📜 Checking account_encoder.pkl
 ┣ 📜 requirements.txt
 ┗ 📜 README.md
```

---


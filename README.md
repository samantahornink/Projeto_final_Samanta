# 🚗 API de Previsão de Preços de Carros Usados

Esta é uma API desenvolvida em Python utilizando o microframework **Flask** e a biblioteca **scikit-learn**. Ela treina um modelo de Regressão Linear baseado em dados históricos de veículos e expõe um endpoint para prever o preço de um carro com base em suas características.

> 🌐 **Acesse a aplicação online:** [Drive Value Predict](https://drive-value-predict.lovable.app/)

---

## 🛠️ Tecnologias Utilizadas

* **Python 3**
* **Flask** (Criação da API)
* **Flask-CORS** (Permissões de acesso de diferentes origens)
* **Pandas** (Manipulação de dados)
* **Scikit-Learn** (Modelo de Machine Learning - Regressão Linear)

---

## 📁 Estrutura de Arquivos Necessária

Para que a API funcione corretamente de forma local, certifique-se de que o arquivo do dataset esteja na mesma pasta do seu script principal:

```text
├── seu_script.py
└── dataset_carros_usados.csv
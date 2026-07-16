# 🚗 Drive Value Predict — API de Previsão de Preço de Carros Usados

API REST simples que utiliza Machine Learning (Regressão Linear) para estimar o preço de carros usados com base em quatro atributos: **ano**, **quilometragem**, **motor** e **número de revisões**. Desenvolvida com **Flask** e **scikit-learn**.

🌐 **Deploy em produção:** [https://drive-value-predict.lovable.app/](https://drive-value-predict.lovable.app/)

---

## 🛠️ Tecnologias Utilizadas

| Componente | Tecnologia |
|---|---|
| Backend | Flask |
| CORS | flask-cors |
| Machine Learning | scikit-learn (LinearRegression) |
| Manipulação de dados | pandas |
| Ambiente | Python 3.8+ |

---

## 📦 Pré-requisitos

- Python 3.8 ou superior
- pip (gerenciador de pacotes Python)
- Arquivo do dataset: `dataset_carros_usados.csv` no diretório raiz do projeto

---

## ⚙️ Instalação

1. **Clonar o repositório**
   ```bash
   git clone https://github.com/seu-usuario/drive-value-predict.git
   cd drive-value-predict
   ```

2. **Criar ambiente virtual (recomendado)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate    # Windows
   ```

3. **Instalar as dependências**
   ```bash
   pip install -r requirements.txt
   ```

4. **Garantir o dataset**
   - Coloque o arquivo `dataset_carros_usados.csv` na raiz do projeto (mesmo diretório de `app.py`).
   - O modelo é treinado automaticamente na inicialização do servidor.

---

## ▶️ Execução Local

```bash
python app.py
```

O servidor será iniciado em:
```
http://0.0.0.0:8000/  (acessível em http://localhost:8000/)
```

Com o parâmetro `debug=True`, qualquer alteração no código reinicia o servidor.

---

## 📡 Endpoints da API

### `GET /` — Status da API
Verifica se a API está online.

**Exemplo:**
```bash
curl -X GET http://localhost:8000/
```

**Resposta esperada:**
```json
{
  "Status": "API online e funcionando corretamente",
  "Autor": "Samanta"
}
```

---

### `POST /prever` — Prever preço de um carro
Recebe os dados do carro e retorna a estimativa de preço calculada pelo modelo de Machine Learning.

**Corpo da requisição (JSON):**
```json
{
  "ano": 2018,
  "quilometragem": 45000,
  "motor": 1.6,
  "num_revisoes": 3
}
```

**Exemplo com cURL:**
```bash
curl -X POST http://localhost:8000/prever \
  -H "Content-Type: application/json" \
  -d '{"ano":2018,"quilometragem":45000,"motor":1.6,"num_revisoes":3}'
```

**Resposta esperada:**
```json
{
  "Preço": 58975.42
}
```

**Em caso de erro (ex.: campo faltando ou tipo inválido):**
```json
{
  "erro": "mensagem descrevendo o problema"
}
```

---

## 📊 Dataset Esperado

O arquivo `dataset_carros_usados.csv` deve conter, **no mínimo**, as seguintes colunas:

| Coluna | Tipo | Descrição |
|---|---|---|
| `ano` | int/float | Ano de fabricação do veículo |
| `quilometragem` | int/float | Quilometragem rodada (km) |
| `motor` | float | Cilindrada do motor (ex.: 1.0, 1.6, 2.0) |
| `num_revisoes` | int | Número de revisões realizadas |
| `preco` | float | Preço de venda (variável alvo) |

> **Nota:** O modelo é treinado com todos os dados do CSV a cada inicialização. Para melhores resultados, mantenha o dataset atualizado e com amostras representativas do mercado.

---

## 🧠 Sobre o Modelo

- **Algoritmo:** Regressão Linear (`LinearRegression` do scikit-learn)
- **Features utilizadas:** `ano`, `quilometragem`, `motor`, `num_revisoes`
- **Treinamento:** Ocorre automaticamente ao iniciar o app (`modelo.fit(X, y)`)
- **Limitações:** Regressão Linear é um modelo simples; pode não capturar relações não-lineares complexas entre as features e o preço. Para cenários reais, considere modelos mais robustos (Random Forest, Gradient Boosting, etc.) e validação estatística.

---

## 🚀 Deploy

A aplicação está publicamente disponível em:

👉 **[https://drive-value-predict.lovable.app/](https://drive-value-predict.lovable.app/)**

Os mesmos endpoints funcionam remotamente (com CORS habilitado):
- `GET https://drive-value-predict.lovable.app/`
- `POST https://drive-value-predict.lovable.app/prever`

---

## 📄 Licença

MIT
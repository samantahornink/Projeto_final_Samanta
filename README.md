Markdown
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
Nota: O arquivo dataset_carros_usados.csv deve conter as colunas: ano, quilometragem, motor, num_revisoes e preco.

🚀 Como Executar o Projeto Localmente
Siga os passos abaixo para rodar a aplicação na sua máquina.

1. Clonar o repositório ou salvar os arquivos
Certifique-se de ter o arquivo Python (ex: app.py) e o dataset na mesma pasta.

2. Instalar as dependências
Abra o seu terminal na pasta do projeto e instale as bibliotecas necessárias rodando:

Bash
pip install flask flask-cors pandas scikit-learn
3. Iniciar o servidor
Execute o arquivo principal da API:

Bash
python app.py
A API local estará rodando no endereço: http://localhost:8000 (ou http://0.0.0.0:8000).

🔌 Rotas e Endpoints
1. Verificar Status da API
Retorna o estado da aplicação e informações do desenvolvedor.

Método: GET

Rota: /

Exemplo de Resposta:

JSON
{
  "Autor": "Samanta",
  "Status": "API online e funcionando corretamente"
}
2. Prever Preço do Veículo
Recebe as características de um carro e retorna o preço estimado pelo modelo de Machine Learning.

Método: POST

Rota: /prever

Cabeçalho obrigatório: Content-Type: application/json

Corpo da requisição (JSON):

JSON
{
  "ano": 2018,
  "quilometragem": 55000,
  "motor": 1.6,
  "num_revisoes": 4
}
Exemplo de Resposta de Sucesso:

JSON
{
  "Preço": 45250.85
}
Exemplo de Resposta de Erro (400 Bad Request):

JSON
{
  "erro": "KeyError: 'ano'"
}
🧪 Como Testar a API
Você pode testar as requisições utilizando ferramentas como Postman, Insomnia ou diretamente pelo terminal usando o comando cURL (seja apontando para o seu ambiente local ou utilizando a interface online):

Testando no Ambiente Local
Bash
curl -X POST http://localhost:8000/prever \
     -H "Content-Type: application/json" \
     -d '{"ano": 2020, "quilometragem": 30000, "motor": 2.0, "num_revisoes": 3}'
Testando na Versão Online
Você também pode interagir de forma visual e amigável diretamente pela interface web do projeto:
👉 https://drive-value-predict.lovable.app/

👤 Autora
Samanta — Desenvolvimento da API e Modelo de Machine Learning.
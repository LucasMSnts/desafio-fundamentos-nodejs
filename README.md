# Desafio Fundamentos Nodejs
Desafio 05 Gostack: Fundamentos de NodeJS

## Rotas de aplicação

- **`POST /transactions`**: A rota recebe `title`, `value`, `type`, e `category` dentro do corpo da requisição, sendo o `type` o tipo da transação, que `income` para entradas (depósitos) e `outcome` para saidas (retiradas). Ao cadastrar uma nova transação, é armazenada dentro do seu banco de dados, possuindo os campos `id`, `title`, `value`, `type`, `category_id`, `created_at`, `updated_at`.

```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income",
  "category": "Alimentação"
}
```

- **`GET /transactions`**: Essa rota retorna uma listagem com todas as transações que foram cadastradas até agora, junto com o valor de soma de entradas, retiradas e total de crédito. Essa rota retorna um objeto com o formato a seguir:
```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Salário",
      "value": 4000,
      "type": "income",
      "category": "Salary"
    },
    {
      "id": "uuid",
      "title": "Freela",
      "value": 2000,
      "type": "income",
      "category": "Others"
    },
    {
      "id": "uuid",
      "title": "Pagamento da fatura",
      "value": 4000,
      "type": "outcome",
      "category": "Others"
    },
    {
      "id": "uuid",
      "title": "Cadeira Gamer",
      "value": 1200,
      "type": "outcome",
      "category": "Recreation"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

- **`DELETE /transactions/:id`**: A rota deleta uma transação com o id presente nos parâmetros da rota;

- **`POST /transactions/import`**: A rota permite a importação de um arquivo com formato `.csv` contendo as mesmas informações necessárias para criação de uma transação `id`, `title`, `value`, `type`, `category_id`, `created_at`, `updated_at`, onde cada linha do arquivo CSV deve ser um novo registro para o banco de dados, e por fim retorne todas as `transactions` que foram importadas para seu banco de dados.

## Iniciar projeto ▶️

Primeiro, fazer um clone do projeto:
```bash
  git clone https://github.com/LucasMSnts/desafio-fundamentos-nodejs.git
```

Depois, instalar as dependências dos projetos, executar ```yarn``` dentro da pasta do projeto

#### Back-end 💭

Para rodar o projeto, executar:
```  yarn dev ``` 

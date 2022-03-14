# Contas a pagar - Telefonia - API

Esse é o repositório com a base de sistema de contas a pagar a fornecedores de telefonia.

## Endpoints

Existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.
1 endpoint pode ser usado para consultar os fornecedores cadastrados atualmente.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### Fornecedores

GET /suppliers

Qualquer usuário que esteja logado pode consultar os fornecedores cadastrados, mas não é permitido alterá-los.

Lista de fornecedores:

```json
"suppliers": [
    {
      "supplier": "Vivo",
      "id": 1
    },
    {
      "supplier": "Claro",
      "id": 2
    },
    {
      "supplier": "Oi",
      "id": 3
    },
    {
      "supplier": "Tim",
      "id": 4
    }
  ]
```

### Contas a pagar

POST /bills <br/>
GET /bills/:id

Um usuário deslogado não pode consultar nem alterar qualquer conta.
Um usuário logado pode consultar todas as contas a pagar e registrar novas contas. Apenas o responsável pelo registro de cada conta a pagar pode fazer alterações nela. O id do usuário deve ser informado no momento do POST /bills, no seguinte formato:

```json
"userId": 2
```

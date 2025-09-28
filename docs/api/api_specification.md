# Autenticação e Autorização 

Todas as rotas que exigem que o usuário esteja logado serão protegidas. A autenticação será feita via token JWT (JSON Web Token). O token será gerado no endpoint de login e deverá ser enviado no cabeçalho Authorization de cada requisição subsequente como Bearer <token>.

+----------------------------------------------+

**Endpoints Previstos** 


Autenticação

* POST /auth/register: Registra um novo usuário.

* POST /auth/login: Autentica um usuário e retorna um token JWT.


**Itens**

* GET /items: Retorna uma lista de itens disponíveis, com suporte a filtros.

* GET /items/:id: Retorna os detalhes de um item específico.

* POST /items: Cria um novo anúncio de item (requer autenticação).

* PUT /items/:id: Atualiza os dados de um item (requer autenticação, apenas o dono).

* DELETE /items/:id: Remove um item (requer autenticação, apenas o dono).

**Doações**

* POST /donations/:itemId/request: Um donatário manifesta interesse em um item.

* PATCH /donations/:donationId/accept: O doador aceita um pedido de doação.

+-------------------------------------------------+

**Exemplos de Chamadas e Respostas** 

Criar um novo item

* Requisição: POST /items

* Headers: Authorization: Bearer <jwt_token>

* Body (parâmetros de requisição): 

JSON

{
  "title": "Cadeira de Escritório Usada",
  "description": "Em bom estado, com rodinhas funcionando.",
  "categoryId": "a1b2c3d4-e5f6-..."
}

* Resposta (formatos de resposta): 

* Sucesso (201 Created):

JSON

{
  "id": "f4g5h6j7-k8l9-...",
  "title": "Cadeira de Escritório Usada",
  "status": "disponível",
  "createdAt": "2025-09-27T22:00:00.000Z"
}
* Erro (401 Unauthorized):

JSON

{
  "error": "Token de autenticação inválido ou não fornecido."
}


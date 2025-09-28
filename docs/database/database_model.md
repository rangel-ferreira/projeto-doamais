Modelo de Dados 

O modelo de dados foi projetado para armazenar informações sobre usuários, itens, categorias e as transações de doação.

Users: Armazena os dados de todos os usuários.

Categories: Armazena as categorias dos itens (ex: Móveis, Eletrônicos, Vestuário).

Items: Contém os detalhes de cada item disponível para doação e sua relação com o doador e a categoria.

Donations: Registra o processo de doação, conectando o doador, o donatário e o item.

Reviews: Armazena as avaliações que os usuários fazem uns dos outros após uma doação.


Diagrama Entidade-Relacionamento (ER) 

```
+-------------+      +-------------+
|   Users     |      |  Categories |
+-------------+      +-------------+
| PK user_id  |      | PK category_id|
| name        |      | name        |
| email       |      +-------------+
| password_hash|           |
| location    |           |
+-------------+           |
    |  |                  |
 (donates)                | (has)
    |  |                  |
    |  v                  v
    | +-------------+
    | |   Items     |
    | +-------------+
    | | PK item_id  |
    | | FK user_id  |
    | | FK category_id|
    | | title       |
    | | description |
    | | status      |
    | +-------------+
    |  |
    |  | (is object of)
    |  v
    +-------------+      +-------------+
    | Donations   |      |   Reviews   |
    +-------------+      +-------------+
| PK donation_id|      | PK review_id|
| FK item_id  |      | FK donation_id|
| FK donor_id (Users)| | FK reviewer_id(Users)|
| FK donee_id (Users)| | FK reviewed_id(Users)|
| status      |      | rating      |
    +-------------+      | comment     |
                         +-------------+ ```


Dicionário de Dados 

| Tabela | Coluna | Tipo | Descrição |
|---|---|---|---|
| Users | user_id | UUID | Identificador único do usuário. |
| | name | VARCHAR(100) | Nome completo do usuário. |
| | email | VARCHAR(100) | E-mail do usuário (único). |
| | password_hash | VARCHAR(255) | Hash da senha do usuário. |
| | location | VARCHAR(255) | Localização (bairro/cidade) para busca. |
| Items | item_id | UUID | Identificador único do item. |
| | user_id | UUID | Chave estrangeira para o doador (Users). |
| | category_id | UUID | Chave estrangeira para a categoria (Categories). |
| | title | VARCHAR(150) | Título do anúncio do item. |
| | status | VARCHAR(20) | Status do item (disponível, reservado, doado). |
| Donations | donation_id | UUID | Identificador único da transação de doação. |
| | item_id | UUID | Chave estrangeira para o item doado. |
| | donor_id | UUID | Chave estrangeira para o usuário doador. |
| | donee_id | UUID | Chave estrangeira para o usuário donatário. |
| | status | VARCHAR(20) | Status da doação (solicitada, aceita, concluída). |

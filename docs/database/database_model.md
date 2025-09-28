Modelo de Dados 

O modelo de dados foi projetado para armazenar informações sobre usuários, itens, categorias e as transações de doação.

Users: Armazena os dados de todos os usuários.

Categories: Armazena as categorias dos itens (ex: Móveis, Eletrônicos, Vestuário).

Items: Contém os detalhes de cada item disponível para doação e sua relação com o doador e a categoria.

Donations: Registra o processo de doação, conectando o doador, o donatário e o item.

Reviews: Armazena as avaliações que os usuários fazem uns dos outros após uma doação.


Diagrama Entidade-Relacionamento (ER) 

```
+-------------+      +-----------------+
|   Usuarios  |      |    Categorias   |
+-------------+      +-----------------+
| PK id_usuario |    | PK id_categoria |
| nome          |    | nome            |
| email         |    +-----------------+
| senha_hash    |           |
| localizacao   |           |
+-------------+             |
    |  |                    |
 (doacoes)                  | (has)
    |  |                    |
    |  v                    v
    | +-------------+
    | |   Items     |
    | +-------------+
    | | PK item_id  |
    | | FK id_usuario  |
    | | FK id_categoria|
    | | titulo       |
    | | descricao |
    | | status      |
    | +-------------+
    |  |
    |  | (e objeto de)
    |  v
    +-----------------------+   +---------------------+
    | doacoes                |  |       Reviews        |
    +-----------------------+   +---------------------+
    | PK id_doacao           |  | PK review_id         |
    | FK item_id             |  | FK id_doacao         |
    | FK id_doador (Users)   |  | FK reviewer_id(Users)|
    | FK id_donatario (Users)|  | FK reviewed_id(Users)|
    | status                 |  | rating               |    
    +------------------------+  | comentario           |
                                 +---------------------+


Dicionário de Dados 
``
| Tabela    | Coluna        | Tipo         | Descrição                                         |
+----------------------------------------------------------------------------------------------+
| Usuarios  | id_usuario    | UUID         | Identificador único do usuário.                   |
|           | nome          | VARCHAR(100) | Nome completo do usuário.                         |
|           | email         | VARCHAR(100) | E-mail do usuário (único).                        |
|           | senha_hash    | VARCHAR(255) | Hash da senha do usuário.                         |
|           | localizacao   | VARCHAR(255) | Localização (bairro/cidade) para busca.           |
+----------------------------------------------------------------------------------------------+
| Items     | item_id       | UUID         | Identificador único do item.                      |
|           | id_usuario    | UUID         | Chave estrangeira para o doador (Users).          |
|           | id_categoria  | UUID         | Chave estrangeira para a categoria (Categories).  |
|           | titulo        | VARCHAR(150) | Título do anúncio do item.                        |
|           | status        | VARCHAR(20)  | Status do item (disponível, reservado, doado).    |
+----------------------------------------------------------------------------------------------+
| Doacoes   | id_doacao     | UUID         | Identificador único da transação de doação.       |
|           | item_id       | UUID         | Chave estrangeira para o item doado.              |
|           | id_doador     | UUID         | Chave estrangeira para o usuário doador.          |
|           | id_donatario  | UUID         | Chave estrangeira para o usuário donatário.       |
|           | status        | VARCHAR(20)  | Status da doação (solicitada, aceita, concluída). |
+----------------------------------------------------------------------------------------------+
```

# Descrição da Arquitetura 

A arquitetura do ReAproveita é uma arquitetura em camadas, composta por uma camada de apresentação (frontend), uma camada de aplicação (backend) e uma camada de dados (banco de dados). As aplicações cliente (web e mobile) são desacopladas do backend e se comunicam através de uma API RESTful. 


**Componentes do Sistema**


* Frontend Web (React): Uma Single-Page Application (SPA) responsável por fornecer a experiência do usuário em navegadores web. 

* Frontend Mobile (React Native): Um aplicativo móvel híbrido para iOS e Android, que compartilhará parte da lógica de estado com a aplicação web. 

* Backend (Node.js/Express): Uma API RESTful que centraliza todas as regras de negócio, como gerenciamento de usuários, itens, doações e autenticação.

* Banco de Dados (PostgreSQL): Um banco de dados relacional para persistir os dados da aplicação de forma estruturada e confiável. 



**Padrões Arquiteturais Utilizados** 


* Cliente-Servidor: Padrão fundamental que separa as responsabilidades da interface do usuário (cliente) da lógica de negócio e armazenamento de dados (servidor).

* REST (Representational State Transfer): Utilizado para a comunicação entre frontend e backend, garantindo uma interface de comunicação padronizada e sem estado.

* Model-View-Controller (MVC) - Lado do Backend: A estrutura do backend será organizada seguindo os princípios do MVC para separar as responsabilidades em Modelos (dados), Visões (representação - neste caso, a resposta da API) e Controladores (lógica).


**Decisões Técnicas e Justificativas** 

* React e React Native: A escolha foi baseada na possibilidade de reutilizar código e lógica de componentes entre a plataforma web e móvel, otimizando o tempo de desenvolvimento.

* Node.js: Mantém o ecossistema de desenvolvimento em JavaScript/TypeScript, facilitando a gestão da equipe e a troca de conhecimento entre desenvolvedores de frontend e backend.

* PostgreSQL: Escolhido por ser um banco de dados relacional robusto, confiável e com bom suporte da comunidade, adequado para os relacionamentos estruturados entre usuários, itens e doações.



# Perfis de Usuários 

* Doador: Usuário que deseja disponibilizar um ou mais itens para doação.
* Donatário/Coletor: Usuário que busca e manifesta interesse em receber itens doados.
* Administrador: Usuário responsável por gerenciar a plataforma, moderar conteúdo e resolver disputas.


## Requisitos Funcionais (RF)

* RF01: O sistema deve permitir que um usuário se cadastre utilizando e-mail e senha.
* RF02: O sistema deve permitir que um usuário realize login com suas credenciais.
* RF03: O sistema deve permitir que o Doador cadastre um item para doação, informando título, descrição, categoria e fotos.
* RF04: O sistema deve associar a localização do item ao cadastro do Doador.
* RF05: O sistema deve permitir que o Donatário busque itens por categoria, palavra-chave ou proximidade.
* RF06: O sistema deve exibir os itens disponíveis em formato de lista ou mapa.
* RF07: O sistema deve permitir que um Donatário manifeste interesse em um item.
* RF08: O sistema deve notificar o Doador quando houver um novo interessado.
* RF09: O sistema deve disponibilizar um chat para que Doador e Donatário combinem a entrega após o Doador aceitar o pedido.
* RF10: O sistema deve permitir que, após a conclusão da doação, ambos os usuários se avaliem mutuamente.
* RF11: O sistema deve permitir que o Doador marque um item como "doado".
* RF12: O sistema deve permitir que usuários denunciem publicações ou comportamentos inadequados.
* RF13: O Administrador deve possuir um painel para visualizar denúncias e gerenciar usuários/itens.


## Requisitos Não-Funcionais (RNF) 

* RNF01 - Usabilidade: A interface deve ser intuitiva e acessível para usuários com diferentes níveis de habilidade tecnológica. 
* RNF02 - Desempenho: As buscas e a listagem de itens devem ser exibidas em menos de 2 segundos.
* RNF03 - Segurança: As senhas dos usuários devem ser armazenadas de forma criptografada. A comunicação com a API deve ocorrer via HTTPS.
* RNF04 - Compatibilidade: A aplicação móvel deve ser compatível com as duas últimas versões dos sistemas iOS e Android. A aplicação web deve ser compatível com as versões mais recentes dos navegadores Chrome, Firefox e Safari.
* RNF05 - Escalabilidade: A arquitetura deve suportar um aumento de 100% no número de usuários ativos em um período de 6 meses sem degradação significativa do desempenho.


## Histórias de Usuário (Exemplos)

* HU01: Eu, como Doador, quero cadastrar um item que não uso mais, com fotos e descrição, para que outra pessoa possa aproveitá-lo.
* HU02: Eu, como Donatário, quero buscar por "cadeira de escritório" perto da minha casa para encontrar uma doação que atenda à minha necessidade.
* HU03: Eu, como Doador, quero receber uma notificação quando alguém se interessar pelo meu item para que eu possa combinar a entrega rapidamente.
* HU04: Eu, como Donatário, quero ver a avaliação de um Doador antes de combinar a retirada para me sentir mais seguro.



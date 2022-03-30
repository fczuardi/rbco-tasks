# Task 1: Escrever User Stories técnicas

## User Story (História de Usuário)

[User story][1] ([História de usuário][2]) é uma ferramenta de análise de
requisitos que captura o "quem", o "o quê" e o "por quê" de um determinado
requisito em um sistema de de software. É uma especificação sucinta e em
linguagem natural que descreve em poucas sentenças um determinado cenário
ou uma função que necessita estar presente e ser atendida pelo sistema.

Histórias de usuário são boas para descrever requisitos sob o ponto de vista
dos usuários finais de um produto. Normalmente incluem além das sentenças 
no formato `"Como um <papel>, eu quero <meta/desejo> de modo que <benefício>"`
juntamente com alguns critérios de aceitação. O que é importante para verificar
, no ambito de produto, se a funcionalidade nova foi de fato implementada
satisfatoriamente.

A "User Story" não entra nos detalhes de implementação, não descreve
mudanças técnicas necessárias no sistema e o tamanho do esforço para a 
implementação de uma "User Story" pode envolver múltiplas subtarefas de apoio,
que podem ser escritas num formato um pouco diferente, o de história técnica.

## Technical User Story (Tech Story, Technical Support Story, Histórias Técnicas)

A [User Story técnica][3] é um pouco diferente, ela descreve uma melhoria 
ou necessidade técnica do sistema, ao invés de uma nova funcionalidade
para o usuário.

Histórias de Usuário normalmente [contém][4] histórias técnicas como dependências,
como histórias de apoio/suporte.

> A Technical User Story is one focused on non-functional support of a system. For example, 
> implementing back-end tables to support a new function, or extending an existing service layer.
> Sometimes they are focused on classic non-functional stories, for example: security, performance,
> or scalability related.

Exemplos: a atualização de uma biblioteca, o desenvolvimento de
um novo componente de interface, a correção de um bug, a alteração de 
um formato de log, a adição de um endpoint em uma API...


## Exercício

A tarefa deste exercício é **escrever histórias de usuário e histórias técnicas**, que descrevam
a necessidade da implementação de 5 novas funcionalidades (comandos) num sistema de automação de
gerencia de TI para ambientes Linux:

1. Um comando para listar grupos de usuários existentes
1. Um comando para listar os usuários existentes
1. Um comando para criar um novo usuário
1. Um comando para adicionar um usuário a um grupo
1. Um comando para listar os grupos a que um usuário específico pertence

[1]: https://en.wikipedia.org/wiki/User_story
[2]: https://pt.wikipedia.org/wiki/Hist%C3%B3ria_de_usu%C3%A1rio
[3]: https://rgalen.com/agile-training-news/2013/11/10/technical-user-stories-what-when-and-how
[4]: https://argondigital.com/blog/product-management/user-stories-technical-stories-agile-development-productmanagement/

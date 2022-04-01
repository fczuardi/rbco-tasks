## User Story 1

Como uma gerente de TI da empresa, quero poder verificar numa tela do sistema, quais são (no Linux
dos colaboradores) os grupos de usuários existentes e quais contas de usuário fazem parte de cada
um deles. De modo que eu verifique se existem grupos que ainda precisem ser criados, se ha grupos 
que podem ser removidos e se alguma conta de usurário faz parte de grupos que não deveria.

**Critérios de aceite:**
  - listagem com todos usuários do sistema
    - se nenhum usuário existe, uma mensagem deve ser exibida
  - listagem de todos os grupos do sistema
    - se nenhum grupo existe, uma mensagem deve ser exibida
  - listagens de usuários pertencentes a um grupo
    - se o grupo não possui usuários, uma mensagem deve ser exibida

### Tech Story 1.1

Para que seja possível fornecer a listagem de todos usuários de um sistema Linux, precisamos
adicionar um novo método à nossa classe "Conector/Linux" (algo como `get_accounts` ou 
`list_accounts`) que execute um comand (algo como `getent passwd | cut -d: -f1`) e retorne
uma lista em caso de sucesso. Ou um exit code de erro, se possível com mensagem descritiva caso
o comando falhe.

### Tech Story 1.2

Para que seja possível fornecer a listagem de todos os grupos de um sistema Linux, precisamos
adicionar um novo método à nossa classe "Conector/Linux" (algo como `get_groups` ou 
`list_groups`) que execute um comand (algo como `getent group | cut -d: -f1`) e retorne
uma lista em caso de sucesso. Ou um exit code de erro, se possível com mensagem descritiva caso
o comando falhe.

### Tech Story 1.3

Para que seja possível fornecer a listagem de usuarios pertencente a um grupo de um sistema Linux, 
precisamos adicionar um novo método à nossa classe "Conector/Linux" (algo como `get_group_accounts`
 ou `list_group_accounts`) que recebe como argumento o nome de um grupo e retorna no caso de sucesso
uma lista de accounts que é o resultado da execução de um comando (algo como
`getent group NOME_DO_GRUPO`). Ou um exit code de erro, se possível com mensagem descritiva caso
o comando falhe ou caso o nome passado como argumento nao seja de um grupo existente.


## User Story 2

Como uma gerente diretamente responsável por uma colaboradora recém contratada, quero poder através
de uma interface do sistema, indicar a quais grupos (no Linux dos colaboradores) a nova conta desta
pessoa deve fazer parte. De modo que esta pessoa não sofra o com erros de acesso negado em seus 
primeiros dias de trabalho por falta de ter os grupos necessários, evitando assim abertura de 
tickets repetitivos ao suporte.

**Critérios de aceite:**
- existe um formulário para criação de nova conta em sistema Linux
  - este formulário possui campos para a inclusão de um conjunto inicial de grupos que esta conta
deve fazer parte

### Tech Story 2.1

Para que seja possível a criação de uma nova conta de usuário linux, precisamos adicionar um ou dois
novos métodos à classe "Connector/Linux", algo tipo `create_account` ou `create_account_with_groups`,
que recebe como argumento obrigatorio um nome de usuário, e como argumento opcional uma lista de
grupos existentes aos quais este novo usuário deve ser adicionado. Em caso de sucesso retorne um
 status de sucesso e em caso de erro uma mensagem descritiva junto com um status de erro. A
 criação deste usuário é a execução de um comando para a criação de usuário com home 
(ex: `useradd --create-home`) seguida de um comando para adicioná-lo
a uma lista de grupos caso este argumento opcional tenha sido passado (ex `useradd -G`).




## User Story 3

Como uma engenheira de segurança da informação, responsável pela prevenção de incidentes e pela
auditoria e revisão dos acessos de uma conta de usuário em férias ou desligado, quero uma forma
simples de consultar via sistema, a lista de grupos (no Linux dos colaboradores) de uma conta a 
partir do nome de usuário. De modo que eu não precise percorrer a lista toda de usuários.

**Critérios de aceite:**
- listagem de grupos para uma conta específica

### Tech Story 3.1

Para que a listagem de grupos para uma conta especifica seja possivel, um novo método 
(`list_account_groups` ou algo assim) deve ser adicionado à classe "Connector/Linux", esta funcao deve
receber um username e retornar, em caso de sucesso a lista de grupos a que ela pertence, os casos
de lista vazia e erros devem estar cobertas por testes de unidade.

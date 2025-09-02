## Histórias de Usuários (HU)

> **HU-01: Cadastro e Autenticação de Usuário**
> **como um** novo visitante da plataforma,
> **eu quero** me cadastrar com nome, e-mail e senha, e depois fazer login,
> **para que** eu possa acessar as funcionalidades seguras da plataforma e ser identificado pela comunidade.
>
> **Critérios de Aceitação:**
> * **Dado** que estou na página de cadastro e preencho os dados válidos, **quando** eu clico em "Cadastrar", **então** um novo 'User' é criado no banco de dados e sou redirecionado para a página de login.
> * **Dado** que tento me cadastrar com um e-mail que já existe, **quando** eu envio o formulário, **então** devo receber uma mensagem de erro informando "E-mail já cadastrado".
> * **Dado** que possuo uma conta válida e estou na página de login, **quando** eu preencho minhas credenciais corretas e clico em "Entrar", **então** devo receber um token de autenticação (JWT) e ser redirecionado para a página principal.

> **HU-02: Criar Pedido de Favor**
> **como um** usuário autenticado,
> **eu quero** poder criar um novo pedido de favor com título e descrição,
> **para que** outros membros da comunidade possam ver minha necessidade.
>
> **Critérios de Aceitação:**
> * **Dado** que estou logado, **quando** eu preencho o formulário de "Novo Pedido" e clico em "Publicar", **então** um novo 'Pedido' é criado no banco de dados, associado ao meu usuário e com status 'ABERTO'.
> * **Dado** que o pedido foi criado com sucesso, **então** devo receber uma mensagem de confirmação e ver meu novo pedido na lista da página principal.
> * **Dado** que não estou logado, **quando** tento acessar a funcionalidade para criar um pedido, **então** devo ser redirecionado para a página de login.

> **HU-03: Visualizar Detalhes de um Pedido**
> **como um** usuário autenticado,
> **eu quero** clicar em um pedido na lista da página principal,
> **para que** eu possa ver todas as suas informações em uma página dedicada.
>
> **Critérios de Aceitação:**
> * **Dado** que estou na página principal, **quando** eu clico em um card de pedido, **então** sou redirecionado para a rota `/pedidos/[id]`, onde `[id]` é o identificador único do pedido.
> * **Dado** que estou na página de detalhes de um pedido, **então** devem ser exibidos o título completo, a descrição completa e o nome do usuário que o criou.
> * **Dado** que tento acessar a URL de um pedido com um ID que não existe, **então** devo ser redirecionado para uma página de erro "Pedido não encontrado".

> **HU-04: Manifestar Interesse em Ajudar**
> **como um** usuário autenticado,
> **eu quero** poder manifestar interesse em ajudar em um pedido de outro usuário,
> **para que** o autor do pedido saiba que estou disponível para colaborar.
>
> **Critérios de Aceitação:**
> * **Dado** que estou logado e visualizando os detalhes de um pedido que não é meu, **quando** eu clico no botão "Eu quero ajudar!", **então** uma nova entrada é criada na tabela 'Interesse', relacionando meu usuário ao pedido.
> * **Dado** que o interesse foi registrado com sucesso, **então** devo receber um feedback visual de confirmação e o botão deve ser desabilitado para mim.
> * **Dado** que estou visualizando os detalhes de um pedido que eu mesmo criei, **então** o botão "Eu quero ajudar!" não deve estar visível.

> **HU-05: Visualizar Interessados em Meu Pedido**
> **como um** usuário autenticado,
> **eu quero** conseguir ver a lista de pessoas que se interessaram em um pedido que eu criei,
> **para que** eu possa saber quem está disposto a me ajudar.
>
> **Critérios de Aceitação:**
> * **Dado** que estou logado e na página de detalhes de um pedido que eu criei, **quando** existem interesses registrados, **então** uma seção "Interessados" deve ser exibida com a lista de nomes dos usuários.
> * **Dado** que estou na página de detalhes de um pedido meu e não há interesses, **então** a seção "Interessados" deve exibir uma mensagem como "Ainda não há interessados".
> * **Dado** que estou na página de detalhes de um pedido de outro usuário, **então** a seção "Interessados" não deve estar visível.
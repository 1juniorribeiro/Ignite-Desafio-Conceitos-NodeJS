# Criar um gerenciador de To do

## Requisitos

-[x] Criar um usuário com name e username
-[x] Criar um novo to do
-[x] listar todos os to dos
-[x] alterar o title e deadline de um to do existente 
-[x] marcar um to do como feito
-[x] excluir um to do 

## Rotas da aplicação 

-[x] as rotas devem ser no arquivo index.js
-[x] post /users deve receber name e username no body e deve ser armazenado em um objeto com um id gerado pelo uuid e um array de to dos
-[x] get /todos deve receber pelo header da requisição uma propriedade username e retornar os todos desse usuario
-[x] post /todos deve receber title e deadline dentro do body da requisição e o username no header e ao criar um todo ele ser amazenado no array do user, formato de um todo, id, title, done: false, deadline: new Date(deadline), created_at date
-[x] PUT /todos/:id a rota deve receber pelo header o username é possivel alterar apenas o title e deadline que possua o mesmo id do to do
-[x] PATCH /todos/:id/done a rota deve receber o username pelo header, e alterar a propriedade done para true se tiver o mesmo id
-[x] Delete /todos/:id a rota deve receber o username pela rota e excluir um todo com o mesmo id informado 

## Especificação de testes/ regras de negócio

-[x] Should be able to create a new user, criar um usuario e retornar em um json do user e retornar o codigo 201
-[x] Should not be able to create a new user when username already exists se tiver um username que exista retornar uma mensagem de erro com o status 400 
-[x] middleware deve ser completado e retornar um erro se o usuario nao existir
-[x] Should be able to list all user's todos retornar a lista de todos se o user existir
-[x] Should be able to create a new todo se o usuario existir criar um todo que recebe as informações do usuario do middleware  o title e o deadline do body
-[] Should be able to update a todo atualizar um todo se o user existir e se tiver o id do mesmo id que foi criado
-[x] Should not be able to update a non existing todo não permitir a atualização de um todo que não existe e retornar um erro 404
-[x] Should be able to delete a todo deletar um todo pelo id retornando um status 204
-[x] Should not be able to delete a non existing todo retornar um erro 404 se for excluir um todo que não existe
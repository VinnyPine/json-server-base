# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento de rede social.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.
Também existem mais 2 endpoints um sendo para posts e outro para comentarios.

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

### Posts

GET /posts

Terá um retorno com todos os posts em um array de objetos. não é necessario "auth"

POST /posts

Para a criação de posts, necessário "auth", enviar arquivo json com:

{
  "title": "hey, this is a post",
  "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin commodo accumsan justo nec elementum.",
  "userId": 1
}

é retornado o post com um id

DELETE /posts/{id}

para deletar posts insira o id após o endpoint sendo necessario "auth", somente o usuário criador do post pode deletar.

### Comments

GET /comments

Terá um retorno com todos os comentários em um array de objetos. não é necessario "auth"

POST /comments

Para a criação de comentários, necessário "auth", enviar arquivo json com:

{
  "content": "hey, this is a comment",
  "postId": 1
  "userId": 1
}

é retornado o comentario com um id

DELETE /comments/{id}

para deletar comentários insira o id após o endpoint sendo necessario "auth", somente o usuário criador do comentário pode deletar.



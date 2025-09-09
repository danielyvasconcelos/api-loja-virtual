# Contrato da API com base nos requisitos fornecidos:

## Recursos Principais
De acordo com o escopo funcional e modelo de dados, a API terá dois recursos principais com uma relação 1:N:

- Categoria (/categorias)
- Produto (/produtos) → Um produto pertence a uma categoria.

# Endpoints da API e Verbos HTTP
Seguindo as boas práticas REST e os requisitos de funcionalidade, os endpoints da API seriam:

## Recurso: categories

- Listar categorias (com paginação): 
    - Método: GET
    - Endpoint: /categorias
    - Parâmetros de Query:
        _page: Número da página.
        _limit: Quantidade de itens por página.


Exemplo de Resposta: Uma lista paginada de objetos Categoria.


### Criar categoria: 

- Método: POST
- Endpoint: /categories
- Corpo da Requisição (Payload): Um objeto JSON com os campos nome (obrigatório, sem duplicidade).

Exemplo de Resposta: O objeto da categoria criada com seu identificador.


### Editar categoria: 

- Método: PUT ou PATCH
- Endpoint: /categorias/:id
- Corpo da Requisição (Payload): Um objeto JSON com o campo nome.

Exemplo de Resposta: O objeto da categoria atualizada.


### Excluir categoria: 

- Método: DELETE
- Endpoint: /categorias/:id

Exemplo de Resposta: Resposta vazia ou de confirmação de sucesso.

## Recurso: products

### Listar produtos (com paginação e ordenação): 

- Método: GET
- Endpoint: /produtos
- Parâmetros de Query:
    _page: Número da página.
    _limit: Quantidade de itens por página.
    _sort: Campo para ordenação (ex: createdDate)._order: Direção da ordenação (asc ou desc).


Exemplo de Resposta: Uma lista paginada e ordenada de objetos Produto.


### Listar produtos por categoria: 

- Método: GET
- Endpoint: /produtos
- Parâmetros de Query:
    categoryId: ID da categoria para filtro.

Exemplo de Resposta: Uma lista de objetos Produto filtrada pela categoria.

### Detalhes de um produto específico: 
- Método: GET
- Endpoint: /products/:id

Exemplo de Resposta: Um único objeto Produto.


### Criar produto: 
- Método: POST
- Endpoint: /produtos
- Corpo da Requisição (Payload): Um objeto JSON com os campos: nome, preco, descricao, categoriaId e data.
- Regras de integridade: A categoroaId deve ser de uma categoria existente.

Exemplo de Resposta: O objeto do produto criado.


### Editar produto: 
- Método: PUT ou PATCH
- Endpoint: /produtos/:id
- Corpo da Requisição (Payload): Um objeto JSON com os campos a serem atualizados.

Exemplo de Resposta: O objeto do produto atualizado.


### Excluir produto: 
- Método: DELETE
- Endpoint: /products/:id

Exemplo de Resposta: Resposta vazia ou de confirmação de sucesso.
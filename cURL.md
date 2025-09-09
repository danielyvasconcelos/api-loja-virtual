# Utilizei o POSTMAN

# Fluxo 01 - Categorias 

## 01 - PARA OBTER TODAS AS CATEGORIAS : 
Método GET - http://localhost:3000/categorias?_page=1&_limit=8

## 02 - PARA ADICIONAR UMA NOVA CATEGORIA:
Método POST - http://localhost:3000/categorias
no body > raw > json 
  {"nome": "Acessórios"}
observação: o id é alto incrementado .

## 03 - PARA EDITAR UMA CATEGORA 
Método PUT - http://localhost:3000/categorias/39d0 (39d0 é um id )
no body > raw > json 
  {"nome": "nome editado Acessórios"}

## 04 - EXCLUIR UMA CATEGORIA :
Método DELETE - http://localhost:3000/categorias/3 

# FLUXO 02 E 03

## Listar Produtos com Paginação e Ordenação
Método GET - http://localhost:3000/produtos?_page=1&_limit=6&_sort=created_at&_order=desc

## Filtrar Produtos por Categoria
Método GET - http://localhost:3000/produtos?categoriaId=6 

## Consultar Detalhes de um Produto por ID
Método GET - http://localhost:3000/produtos/6

## Criar um Produto Válido
Método POST - http://localhost:3000/produtos 
no body > raw > json 
    {
      "id": "7",
      "nome": "Capinha Iphone 14 ",
      "preco": 50.00,
      "descricao": "descrição do produtos",
      "dataCriacao": "2025-09-09",
      "categoriaId": "39d0"
    }

## Editar Campos de um Produto
Método PATCH - http://localhost:3000/produtos/7 
no body > raw > json 
{
    "descricao": "Capinha azul claro "
}

## Excluir um Produto
Método DELETE - http://localhost:3000/produtos/4
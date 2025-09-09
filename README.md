# Projeto: Construindo uma API Contract-First com json-server


### Disciplina : Programação Web II
### Professor : Paulo Henrique
### - Data limite de entrega: 15/09
### - Atividade individual
### - Pontuação: 0 a 2,5 pontos

Este projeto visa a construção de uma API simulada para uma mini loja virtual, aplicando os princípios do desenvolvimento *Contract-First*. 
A partir de interfaces de usuário (UI) definidas, irei traduzir os requisitos visuais em contratos de API funcionais, utilizando o `json-server` para criar um mock server. 

## Objetivos de Aprendizagem

- Exercitar a tradução de requisitos de interface em contratos de API. 
- Aplicar boas práticas REST na definição de recursos e endpoints. 
- Compreender e aplicar os níveis de maturidade do Modelo de Richardson. 
- Criar e testar uma API simulada usando o `json-server`. 

---

## ✅ Lista de Tarefas do Projeto

### Fase 1: Modelagem de Dados e Configuração

-   [x] **1. Identificar os recursos da API:**
    -   Definir os recursos principais como `categories` e `products`, com uma relação de 1-N (um produto pertence a uma categoria). 

-   [x] **2. Definir o Modelo de Dados Mínimo:** 
    -   **Categoria:** Deve conter `id` e `nome` (obrigatório e sem duplicidade). 
    -   **Produto:** Deve conter `id`, `nome` (obrigatório), `price`, `short_description`, `categoriaId` (referência à categoria) e `dataCriacao` (para ordenação). 

-   [x] **3. Criar e Popular o arquivo `db.json`:** 
    -   Criar o arquivo `db.json`.
    -   Adicionar ao menos 3 categorias distintas. 
    -   Adicionar ao menos 6 produtos distribuídos entre as categorias criadas. 
    -   Garantir que cada produto tenha uma referência a uma `categoriaId` válida e existente. 

### Fase 2: Definição e Teste dos Endpoints

Crie um arquivo de texto para armazenar os comandos cURL correspondentes a cada um dos critérios de aceite abaixo. 

#### **Recurso: Categories** 

-   [x] **Listar Categorias:**
    -   Criar um cURL para `GET /categorias` que demonstre a listagem paginada  

-   [x] **Criar Categoria:**
    -   Criar um cURL para `POST /categorias` enviando o payload de uma nova categoria válida. 
-   [x] **Editar Categoria:**
    -   Criar um cURL para `PATCH /categorias/{id}` ou `PUT /categories/{id}` para editar o nome de uma categoria existente. 

-   [x] **Excluir Categoria:**
    -   Criar um cURL para `DELETE /categorias/{id}` para excluir uma categoria existente. 

#### [cite_start]**Recurso: Products** 

-   [x] **Listar Produtos:**
    -   Criar um cURL para `GET /products` que demonstre a listagem paginada e ordenada por um campo 

-   [x] **Filtrar Produtos por Categoria:**
    -   Criar um cURL para `GET /products?categoryId={id}` para listar apenas os produtos de uma categoria específica. 

-   [x] **Consultar Detalhes do Produto:**
    -  Criar um cURL para `GET /products/{id}` para consultar os detalhes de um produto específico. 

-   [ ] **Criar Produto:**
    -  Criar um cURL para `POST /products` para criar um novo produto, garantindo que ele esteja vinculado a uma `categoryId` existente. 

-   [x] **Editar Produto:**
    -  Criar um cURL para `PATCH /products/{id}` para editar campos de um produto existente (ex: `price` ou `description`). 

-   [x] **Excluir Produto:**
    -  Criar um cURL para `DELETE /products/{id}` para excluir um produto existente. 

---

### Fase 3: Entregáveis do Projeto

-   [x] **1.Arquivo `db.json`:** 
    -  O arquivo deve estar corretamente configurado e populado conforme os requisitos da Fase 1.

-   [x] **2.Arquivo de cURLs:** 
    -  Um único arquivo de texto (`.txt` ou `.md`) contendo todos os comandos cURL organizados por recurso/fluxo, cobrindo todos os critérios de aceite da Fase 2. 

## Como Executar o Projeto

1.  Certifique-se de ter o `json-server` instalado (`npm install -g json-server`).
2.  Navegue até o diretório do projeto.
3.  Inicie o servidor com o seguinte comando:
    ```bash
    json-server --watch db.json
    ```
4.  O servidor estará disponível em `http://localhost:3000`.
5.  Use os cURLs criados para testar os endpoints.

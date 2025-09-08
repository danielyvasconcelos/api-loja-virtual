# Projeto: Construindo uma API Contract-First com json-server

[cite_start]Este projeto visa a construção de uma API simulada para uma mini loja virtual, aplicando os princípios do desenvolvimento *Contract-First*. 
[cite_start]A partir de interfaces de usuário (UI) definidas, irei traduzir os requisitos visuais em contratos de API funcionais, utilizando o `json-server` para criar um mock server. 

## Objetivos de Aprendizagem

- [cite_start]Exercitar a tradução de requisitos de interface em contratos de API. 
- [cite_start]Aplicar boas práticas REST na definição de recursos e endpoints. 
- [cite_start]Compreender e aplicar os níveis de maturidade do Modelo de Richardson. 
- [cite_start]Criar e testar uma API simulada usando o `json-server`. 

---

## ✅ Lista de Tarefas do Projeto

### Fase 1: Modelagem de Dados e Configuração

-   [ ] **1. Identificar os recursos da API:**
    -   [cite_start]Definir os recursos principais como `categories` e `products`, com uma relação de 1-N (um produto pertence a uma categoria). 

-   [ ] **2. [cite_start]Definir o Modelo de Dados Mínimo:** [cite: 75]
    -   [cite_start]**Categoria:** Deve conter `id` e `name` (obrigatório e sem duplicidade). 
    -   [cite_start]**Produto:** Deve conter `id`, `name` (obrigatório), `price`, `short_description`, `categoryId` (referência à categoria) e `created_date` (para ordenação). 

-   [ ] **3. [cite_start]Criar e Popular o arquivo `db.json`:** 
    -   Criar o arquivo `db.json`.
    -   [cite_start]Adicionar ao menos 3 categorias distintas. 
    -   [cite_start]Adicionar ao menos 6 produtos distribuídos entre as categorias criadas. 
    -   [cite_start]Garantir que cada produto tenha uma referência a uma `categoryId` válida e existente. 

### Fase 2: Definição e Teste dos Endpoints

[cite_start]Crie um arquivo de texto para armazenar os comandos cURL correspondentes a cada um dos critérios de aceite abaixo. 

#### [cite_start]**Recurso: Categories** 

-   [ ] **Listar Categorias:**
    -   [cite_start]Criar um cURL para `GET /categories` que demonstre a listagem paginada (ex: `_page=1&_limit=2`). 

-   [ ] **Criar Categoria:**
    -   [cite_start]Criar um cURL para `POST /categories` enviando o payload de uma nova categoria válida. 
-   [ ] **Editar Categoria:**
    -   [cite_start]Criar um cURL para `PATCH /categories/{id}` ou `PUT /categories/{id}` para editar o nome de uma categoria existente. 

-   [ ] **Excluir Categoria:**
    -   [cite_start]Criar um cURL para `DELETE /categories/{id}` para excluir uma categoria existente. 

#### [cite_start]**Recurso: Products** 

-   [ ] **Listar Produtos:**
    -   [cite_start]Criar um cURL para `GET /products` que demonstre a listagem paginada e ordenada por um campo (ex: `_sort=created_date`). 

-   [ ] **Filtrar Produtos por Categoria:**
    -   [cite_start]Criar um cURL para `GET /products?categoryId={id}` para listar apenas os produtos de uma categoria específica. 

-   [ ] **Consultar Detalhes do Produto:**
    -   [cite_start]Criar um cURL para `GET /products/{id}` para consultar os detalhes de um produto específico. 

-   [ ] **Criar Produto:**
    -   [cite_start]Criar um cURL para `POST /products` para criar um novo produto, garantindo que ele esteja vinculado a uma `categoryId` existente. 

-   [ ] **Editar Produto:**
    -   [cite_start]Criar um cURL para `PATCH /products/{id}` para editar campos de um produto existente (ex: `price` ou `description`). 

-   [ ] **Excluir Produto:**
    -   [cite_start]Criar um cURL para `DELETE /products/{id}` para excluir um produto existente. 

---

### Fase 3: Entregáveis do Projeto

-   [ ] **1. [cite_start]Arquivo `db.json`:** 
    -   [cite_start]O arquivo deve estar corretamente configurado e populado conforme os requisitos da Fase 1.

-   [ ] **2. [cite_start]Arquivo de cURLs:** 
    -   [cite_start]Um único arquivo de texto (`.txt` ou `.md`) contendo todos os comandos cURL organizados por recurso/fluxo, cobrindo todos os critérios de aceite da Fase 2. 

## Como Executar o Projeto

1.  Certifique-se de ter o `json-server` instalado (`npm install -g json-server`).
2.  Navegue até o diretório do projeto.
3.  Inicie o servidor com o seguinte comando:
    ```bash
    json-server --watch db.json
    ```
4.  O servidor estará disponível em `http://localhost:3000`.
5.  [cite_start]Use os cURLs criados para testar os endpoints.
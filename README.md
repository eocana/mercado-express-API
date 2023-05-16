# mercado-express

Gestion de productos/regalos para social-gift u otro servicio...

## Gestion de productos

- crear productos
- editar productos
- desactivar productos
- buscar productos (por nombre y descripción)
- visualizar productos

## Gestion de categorias

- crear categorias
- editar categorias
- eliminar categorias
- visualizar categorias

# Casos de uso

TBD

# Base de datos

| PRODUCTS    |
| ----------- |
| id          |
| name        |
| description |
| image_url   |
| url <?>     |
| price       |
| stock       |
| deleted     |

| CATEGORIES  |
| ----------- |
| id          |
| name        |
| description |
| image_url   |
| parent_id   |

| PRODUCTS_CATEGORIES |
| ------------------- |
| product_id          |
| category_id         |

## Enpoints // Representaciones

### crear productos

    ```
    POST /products/
    {
        "name": "Nintendo Switch",
        "description": "Descripcion del producto 1",
        "image_url": "https://www.google.com/switch.jpg",
        "url": "https://www.google.com/switch.com",
        "price": 100,
        "stock": 10,
        "categories": [1, 2, 3, ...]
    }

    ```

### editar productos

    ```
    PUT /products/:id
    {
        "name": "Nintendo Switch",
        "description": "Descripcion del producto 1",
        "image_url": "https://www.google.com/switch.jpg",
        "url": "https://www.google.com/switch.com",
        "price": 100,
        "stock": 10,
        "categories": [1, 2, 3, ...]
    }
    ```

### desactivar productos

    ```
    DELETE /products/:id
    ```
    Update de la tabla products, campo deleted = true

### borrar prodcuto

    ```
    DELETE /products/:id?force=true
    {
        force: true
    }

    ```
    Delete de la tabla products

### visualizar productos

        ```
        GET /products
        ```

### visualizar UN producto

            ```
            GET /products/:id
            ```

### buscar productos (por nombre y descripción)

    ```
    POST /products/search
    {
        "criteria":"nintendo"
    }
    ```

    ```
    GET /products/search?criteria=nintendo // ---> opcional: &page=10&offset=20
    ```

### crear categorias

    ```
    POST /categories/
    {
        "name": Categoria 2",
        "description": "Descripcion de la categoria 2",
        "image_url": "https://www.google.com/category2.jpg",
        "parent_id": 1 (puede o no estar)
    }
    ```

### editar categorias

    ```
    PUT /categories/:id
    {
        "name": Categoria 2",
        "description": "Descripcion de la categoria 2",
        "image_url": "https://www.google.com/category2.jpg",
        "parent_id": 1 (puede o no estar)
    }
    ```

### eliminar categorias

    ```
    DELETE /categories/:id
    ```

### visualizar categorias

    ```
    GET /categories
    ```

### visualizar UNA categoria

    ```
    GET /categories/:id
    ```

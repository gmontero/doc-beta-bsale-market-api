## Estructura JSON

Al realizar una petición HTTP, el servicio retornara un JSON con la siguiente estructura:
```json
{
  "code": "200",
  "data": {
    "id": 6805,
    "createAt": 1506426485,
    "cartDetails": [
      {
        "id": 44,
        "quantity": 1,
        "unitValue": 29990,
        "netUnitValue": 25201.6806722689,
        "discount": 6.66889,
        "itemName": "Ardo Amaryll Start Sacaleche manual ",
        "total": 27989,
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "sku": "AR127",
        "link": "/product/ardo-amaryll-start-sacaleche-manual",
        "productWebId": 8,
        "cartId": 6805,
        "taxList": [
          1
        ],
        "name": "Ardo Amaryll Start Sacaleche manual ",
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 6,
        "cd_item_name": "Ardo Amaryll Start Sacaleche manual ",
        "cd_sub_total": 27989,
        "cd_id": 44,
        "cd_id_discount": 9,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6805/detail/44.json"
      }
    ],
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6805.json"
  }
}
```

- **id**, Identificador único del carro (Integer).
- **createAt**, Fecha de creacion (String).
#### Detalle del carro
- **id**,Identificador único del item del carro (String).
- **quantity**, Cantidad de item que se lleva el carro (String).
- **unitValue**, Valor bruto del producto (String).
- **netUnitValue**, Valor neto del producto (String).
- **discount**, Discuento (Integer).
- **itemName**, Nombre del item (String).
- **total**, Total en bruto de este item(String).
- **discountId**, Id del descuento (hash).
- **image**, Url imagen (Integer).
- **idVarianteProducto**, Id de la variante del producto (Integer).
- **sku**, SKU de la variante (Integer).
- **link**, url del producto (Integer).
- **cartId**, Id del carro (Integer).
- **productWebId**, Id del producto en el market (Hash).
- **cartId**, Id del carro (Integer).
- **taxList**, Lista de id impuesto (Integer).
- **url**, Url del detalle del carro (String).


## GET lista de carro

* `GET /v1/cart.json` retornara todos los carros.

#### Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, por defecto el limit es 25, el máximo permitido es 50.
- *offset*, permite paginar los items de una respuesta JSON, por defecto el offset es 0.
- *expand*, permite expandir las dirreciones y de los carros. ej. expand=[cartDetails].
- *way*, Flujo como se despliega la información.
- *order*, Indica como se orderna el checkout, los valores son:id, createAt.

#### Ejemplos

* `GET /v1/cart.json?limit=10&offset=0`
* `GET /v1/cart.json?way=desc`

#### Respuesta
```json
{
  "code": "200",
  "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart.json",
  "count": 6817,
  "limit": 25,
  "offset": 0,
  "data": [
    {
      "id": 6824,
      "createAt": 1506442849,
      "cartDetails": [
        {
          "id": 77,
          "quantity": 1,
          "unitValue": 29990,
          "netUnitValue": 25201.6806722689,
          "discount": 6.66889,
          "itemName": "Ardo Amaryll Start Sacaleche manual ",
          "total": 27989,
          "discountId": 9,
          "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
          "idVarianteProducto": 1019,
          "sku": "AR127",
          "link": "/product/ardo-amaryll-start-sacaleche-manual",
          "productWebId": 8,
          "cartId": 6824,
          "taxList": [
            1
          ],
          "name": "Ardo Amaryll Start Sacaleche manual ",
          "value": 29990,
          "cd_q": 1,
          "cd_unit_value": 29990,
          "cd_discount": 6,
          "cd_item_name": "Ardo Amaryll Start Sacaleche manual ",
          "cd_sub_total": 27989,
          "cd_id": 77,
          "cd_id_discount": 9,
          "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
          "id_variante_producto": 1019,
          "codigo_variante_producto": "AR127",
          "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6824/detail/77.json"
        },
        {
          "id": 78,
          "quantity": 1,
          "unitValue": 29990,
          "netUnitValue": 25201.6806722689,
          "discount": 0,
          "total": 29990,
          "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
          "idVarianteProducto": 1019,
          "sku": "AR127",
          "link": "/product/ardo-amaryll-start-sacaleche-manual",
          "productWebId": 8,
          "cartId": 6824,
          "taxList": [
            1
          ],
          "value": 29990,
          "cd_q": 1,
          "cd_unit_value": 29990,
          "cd_discount": 0,
          "cd_sub_total": 29990,
          "cd_id": 78,
          "cd_id_discount": 0,
          "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
          "id_variante_producto": 1019,
          "codigo_variante_producto": "AR127",
          "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6824/detail/78.json"
        }
      ],
      "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6824.json"
    },
    ...
  ],
  "next": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart.json?limit=25&offset=25"
}
```
## GET un carro

* `GET /v1/cart/6805.json` retornara un carro.

#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 6805,
    "createAt": 1506426485,
    "cartDetails": [
      {
        "id": 44,
        "quantity": 1,
        "unitValue": 29990,
        "netUnitValue": 25201.6806722689,
        "discount": 6.66889,
        "itemName": "Ardo Amaryll Start Sacaleche manual ",
        "total": 27989,
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "sku": "AR127",
        "link": "/product/ardo-amaryll-start-sacaleche-manual",
        "productWebId": 8,
        "cartId": 6805,
        "taxList": [
          1
        ],
        "name": "Ardo Amaryll Start Sacaleche manual ",
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 6,
        "cd_item_name": "Ardo Amaryll Start Sacaleche manual ",
        "cd_sub_total": 27989,
        "cd_id": 44,
        "cd_id_discount": 9,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6805/detail/44.json"
      },
      {
        "id": 45,
        "quantity": 1,
        "unitValue": 29990,
        "netUnitValue": 25201.6806722689,
        "discount": 0,
        "total": 29990,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "sku": "AR127",
        "link": "/product/ardo-amaryll-start-sacaleche-manual",
        "productWebId": 8,
        "cartId": 6805,
        "taxList": [
          1
        ],
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 0,
        "cd_sub_total": 29990,
        "cd_id": 45,
        "cd_id_discount": 0,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6805/detail/45.json"
      }
    ],
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6805.json"
  }
}
```
## POST un carro

* `POST /v1/cart.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "cartDetails": [
        {
        "quantity": 1,
        "netUnitValue": 29990,
        "unitValue": 29990,
        "itemName": "Ardo Amaryll Start Sacaleche manual ",
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "productWebId": 8
        }
    ]
}
```
#### Donde
- **netUnitValue**, Si no viene lo crea (String).
- **unitValue**, obligatorio (Integer).
- **discountId**, Si viene valida que exista (Integer).

#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 6825,
    "createAt": 1506448632,
    "cartDetails": [
      {
        "id": 80,
        "quantity": 1,
        "unitValue": 29990,
        "netUnitValue": 25201.6806722689,
        "discount": 6.66889,
        "itemName": "Ardo Amaryll Start Sacaleche manual ",
        "total": 27989,
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "sku": "AR127",
        "link": "/product/ardo-amaryll-start-sacaleche-manual",
        "productWebId": 8,
        "cartId": 6825,
        "taxList": [
          1
        ],
        "name": "Ardo Amaryll Start Sacaleche manual ",
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 6,
        "cd_item_name": "Ardo Amaryll Start Sacaleche manual ",
        "cd_sub_total": 27989,
        "cd_id": 80,
        "cd_id_discount": 9,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6825/detail/80.json"
      }
    ],
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6825.json"
  }
}
```
## PUT un carro

* `PUT /v1/cart/6807.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "cartDetails": [
        {
        "id": 48,
        "quantity": 2,
        "unitValue": 29990,
        "itemName": "Ardo Amaryll Start Sacaleche manual ",
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "productWebId": 8
        }
    ]
}
```
#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 6807,
    "createAt": 1506430641,
    "cartDetails": [
      {
        "id": 48,
        "quantity": 2,
        "unitValue": 29990,
        "netUnitValue": 25201.6806722689,
        "discount": 6.66889,
        "itemName": "Ardo Amaryll Start Sacaleche manual ",
        "total": 55979,
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "sku": "AR127",
        "link": "/product/ardo-amaryll-start-sacaleche-manual",
        "productWebId": 8,
        "cartId": 6807,
        "taxList": [
          1
        ],
        "name": "Ardo Amaryll Start Sacaleche manual ",
        "value": 29990,
        "cd_q": 2,
        "cd_unit_value": 29990,
        "cd_discount": 6,
        "cd_item_name": "Ardo Amaryll Start Sacaleche manual ",
        "cd_sub_total": 55979,
        "cd_id": 48,
        "cd_id_discount": 9,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6807/detail/48.json"
      },
      {
        "id": 49,
        "quantity": 2,
        "unitValue": 29990,
        "netUnitValue": 25201.6806722689,
        "discount": 6.66889,
        "itemName": "Ardo Amaryll Start Sacaleche manual ",
        "total": 55979,
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "sku": "AR127",
        "link": "/product/ardo-amaryll-start-sacaleche-manual",
        "productWebId": 8,
        "cartId": 6807,
        "taxList": [
          1
        ],
        "name": "Ardo Amaryll Start Sacaleche manual ",
        "value": 29990,
        "cd_q": 2,
        "cd_unit_value": 29990,
        "cd_discount": 6,
        "cd_item_name": "Ardo Amaryll Start Sacaleche manual ",
        "cd_sub_total": 55979,
        "cd_id": 49,
        "cd_id_discount": 9,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6807/detail/49.json"
      }
    ],
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6807.json"
  }
}
```
## Get un detalle del carro

* `GET /v1/cart/6808/detail.json` Obtiene el detalle del carro.
```json
{
  "code": "200",
  "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6808/detail.json",
  "count": 1,
  "limit": 0,
  "offset": 20,
  "data": [
    {
      "id": 50,
      "quantity": 1,
      "unitValue": 29990,
      "netUnitValue": 25201.6806722689,
      "discount": 6.66889,
      "itemName": "Ardo Amaryll Start Sacaleche manual ",
      "total": 27989,
      "discountId": 9,
      "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
      "idVarianteProducto": 1019,
      "sku": "AR127",
      "link": "/product/ardo-amaryll-start-sacaleche-manual",
      "productWebId": 8,
      "cartId": 6808,
      "taxList": [
        1
      ],
      "name": "Ardo Amaryll Start Sacaleche manual ",
      "value": 29990,
      "cd_q": 1,
      "cd_unit_value": 29990,
      "cd_discount": 6,
      "cd_item_name": "Ardo Amaryll Start Sacaleche manual ",
      "cd_sub_total": 27989,
      "cd_id": 50,
      "cd_id_discount": 9,
      "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
      "id_variante_producto": 1019,
      "codigo_variante_producto": "AR127",
      "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6808/detail/50.json"
    }
  ],
  "previous": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6808/detail.json?limit=0&offset=-20"
}
```
## Get un detalle de un item en el carro

* `GET /v1/cart/6808/detail/50.jsonn` Obtiene el detalle de un item en el carro.
```json
{
  "code": "200",
  "data": {
    "id": 50,
    "quantity": 1,
    "unitValue": 29990,
    "netUnitValue": 25201.6806722689,
    "discount": 6.66889,
    "itemName": "Ardo Amaryll Start Sacaleche manual ",
    "total": 27989,
    "discountId": 9,
    "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
    "idVarianteProducto": 1019,
    "sku": "AR127",
    "link": "/product/ardo-amaryll-start-sacaleche-manual",
    "productWebId": 8,
    "cartId": 6808,
    "taxList": [
      1
    ],
    "name": "Ardo Amaryll Start Sacaleche manual ",
    "value": 29990,
    "cd_q": 1,
    "cd_unit_value": 29990,
    "cd_discount": 6,
    "cd_item_name": "Ardo Amaryll Start Sacaleche manual ",
    "cd_sub_total": 27989,
    "cd_id": 50,
    "cd_id_discount": 9,
    "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
    "id_variante_producto": 1019,
    "codigo_variante_producto": "AR127",
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6808/detail/50.json"
  }
}
```
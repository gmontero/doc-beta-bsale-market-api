## Estructura JSON

Al realizar una petición HTTP, el servicio retornara un JSON con la siguiente estructura:
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "usId": 1,
    "title": "Benjamin",
    "address": "Dona",
    "postCode": 123123,
    "addressComponent": {
      "dede": "ded"
    },
    "dynamicData": [
      222,
      222,
      232
    ],
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/address/2.json"
  }
}
```
- **href**, url del usuario (String).
- **id**, identificador único de la dirección (Integer).
- **usId**, identificador único del usuario (Integer).
- **title**, Titulo de la dirección (String).
- **address**, Direccion (String).
- **postCode**, Código postal (Integer).
- **addressComponent**, Compocición de la dirección del cliente (JSON).
- **dynamicData**, Datos dinamicos de la direcion (JSON).

## GET lista de direccion de un usuario

* `GET /v1/admin/users/1/address.json` Retorna todas las direcciones del usuario.

#### Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, por defecto el limit es 25, el máximo permitido es 50.
- *offset*, permite paginar los items de una respuesta JSON, por defecto el offset es 0.
- *title*, Permite filtrar el titulo de direciones.
- *postCode*, Permite filtrar código postal.
- *address*, Permite filtrar por las direcciones.
- *search*, Busca por titulo, código, apellido o direcciones.

#### Ejemplos

* `GET /v1/admin/users/1/address.json?limit=10&offset=0`
* `GET /v1/admin/users/1/address.json?titulo=benajmin`

#### Respuesta
```json
{
  "code": "200",
  "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/address.json",
  "count": 1,
  "limit": 25,
  "offset": 0,
  "data": [
    {
      "id": 2,
      "usId": 1,
      "title": "Benjamin",
      "address": "Dona",
      "postCode": 123123,
      "addressComponent": {
        "dede": "ded"
      },
      "dynamicData": [
        222,
        222,
        232
      ],
      "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/address/2.json"
    }
  ]
}
```
## GET una dirrección

* `GET /v1/admin/users/1/address/2.json` retornara una dirreción.

#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "usId": 1,
    "title": "Benjamin",
    "address": "Dona",
    "postCode": 123123,
    "addressComponent": {
      "dede": "ded"
    },
    "dynamicData": [
      222,
      222,
      232
    ],
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/address/2.json"
  }
}
```
## POST una dirrección

* `POST /v1/admin/users/1/address.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "title": "Casa",
    "address": "Nuncio Monseñor Sotero Sanz 100, Of. 401, Providencia, Chile",
    "postCode": "7500011",
    "addressComponent":[{"code":1,"name":"Chile"},{"code":3,"name":"Santiago"},{"code":4,"name":"Providencia"}],
    "dynamicData":{"departamento":"oficina 401","comment":"Tocar el timbre"}
}
```
#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 3,
    "usId": 1,
    "title": "Casa",
    "address": "Nuncio Monseñor Sotero Sanz 100, Of. 401, Providencia, Chile",
    "postCode": 7500011,
    "addressComponent": [
      {
        "code": 1,
        "name": "Chile"
      },
      {
        "code": 3,
        "name": "Santiago"
      },
      {
        "code": 4,
        "name": "Providencia"
      }
    ],
    "dynamicData": {
      "departamento": "oficina 401",
      "comment": "Tocar el timbre"
    },
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/address/3.json"
  }
}
```
## PUT una dirrección

* `PUT /v1/admin/users/1/address/3.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "title": "Oficina de Santiago",
    "address": "Nuncio Monseñor Sotero Sanz 100, Of. 401, Providencia, Chile",
    "postCode": "7500011",
    "addressComponent":[{"code":1,"name":"Chile"},{"code":3,"name":"Santiago"},{"code":4,"name":"Providencia"}],
    "dynamicData":{"departamento":"oficina 401","comment":"Tocar el timbre"}
}
```
#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 3,
    "usId": 1,
    "title": "Oficina de Santiago",
    "address": "Nuncio Monseñor Sotero Sanz 100, Of. 401, Providencia, Chile",
    "postCode": 7500011,
    "addressComponent": [
      {
        "code": 1,
        "name": "Chile"
      },
      {
        "code": 3,
        "name": "Santiago"
      },
      {
        "code": 4,
        "name": "Providencia"
      }
    ],
    "dynamicData": {
      "departamento": "oficina 401",
      "comment": "Tocar el timbre"
    },
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/address/3.json"
  }
}
```
## DELETE una dirrección 

* `DELETE /v1/admin/users/1/address/3.json` elimina la dirrección.
```json
{
  "code": "200",
  "data": {
    "id": 3,
    "usId": 1,
    "title": "Oficina de Santiago",
    "address": "Nuncio Monseñor Sotero Sanz 100, Of. 401, Providencia, Chile",
    "postCode": 7500011,
    "addressComponent": [
      {
        "code": 1,
        "name": "Chile"
      },
      {
        "code": 3,
        "name": "Santiago"
      },
      {
        "code": 4,
        "name": "Providencia"
      }
    ],
    "dynamicData": {
      "departamento": "oficina 401",
      "comment": "Tocar el timbre"
    },
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/address/3.json"
  }
}
```
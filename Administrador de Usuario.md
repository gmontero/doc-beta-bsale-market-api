## Estructura JSON

Al realizar una petición HTTP, el servicio retornara un JSON con la siguiente estructura:
```json
{
  "code": "200",
  "data": {
    "id": 1,
    "osuId": 2,
    "name": "Benjamins",
    "lastNames": "Donas",
    "phone": "123123",
    "dynamicData": [
      222,
      222,
      2324
    ],
    "createAt": 1504721448,
    "modifyAt": 1504721460,
    "address": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/address.json"
    ],
    "cart": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/cart.json"
    ],
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1.json"
  }
}
```
- **href**, url del usuario (String).
- **id**, identificador único del usuario (Integer).
- **osuId**, identificador único del usuario en bway (Integer).
- **name**, nombre del usuario (String).
- **lastNames**, Apellidos del usuario (String).
- **phone**, Numero del usuario (String).
- **dynamicData**, Datos dinamicos del usuario (JSON).
- **createAt**, Fecha de creacion del usuario (UNIX EPOCH ).
- **modifyAt**, Fecha de modificación del usuario (UNIX EPOCH ).
- **address**, End poind de direciones del cliente (String).
- **cart**,  End poind de carros del cliente (String).


## GET lista de usuarios

* `GET /v1/admin/users.json` retornara todos los usuarios.

#### Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, por defecto el limit es 25, el máximo permitido es 50.
- *offset*, permite paginar los items de una respuesta JSON, por defecto el offset es 0.
- *expand*, permite expandir las dirreciones y de los carros. ej. expand=[address,cart].
- *phone*, Permite filtrar el telefono de los usuario.
- *lastNames*, Permite filtrar los apellidos de los usuario.
- *osuId*, Permite filtrar por el usuario en bway (Integer).
- *userId*, Permite filtrar por el usuario en bsale (Integer).
- *email*, Permite filtrar por email de los usuario.
- *search*, Busca por nombre, telefono, apellido, nombre apellido o email.

#### Ejemplos

* `GET /v1/admin/users.json?limit=10&offset=0`
* `GET /v1/admin/users.json?expand=[address,cart]`
* `GET /v1/admin/users.json?name=benajmin`

#### Respuesta
```json
{
  "code": "200",
  "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users.json",
  "count": 1,
  "limit": 25,
  "offset": 0,
  "data": [
    {
      "id": 1,
      "osuId": 2,
      "email": "benajmin@lias.cl",
      "name": "Benjamins",
      "lastNames": "Donas",
      "phone": "123123",
      "dynamicData": [
        222,
        222,
        2324
      ],
      "createAt": 1504721448,
      "modifyAt": 1504790066,
      "address": [
        "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/user/1/address.json"
      ],
      "cart": [
        "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/carts.json"
      ],
      "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1.json"
    }
  ]
}
```
## GET un usuario

* `GET /v1/admin/users/1.json` retornara una usuario.

#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 1,
    "email": "benajmin@lias.cl",
    "name": "Benjamins",
    "lastNames": "Donas",
    "phone": "123123",
    "dynamicData": [
      222,
      222,
      2324
    ],
    "createAt": 1504721448,
    "modifyAt": 1504790066,
    "address": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/user/1/address.json"
    ],
    "cart": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/carts.json"
    ],
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1.json"
  }
}
```
## POST un usuario

* `POST /v1/admin/users.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "osuId": 2,
    "name": "Test",
    "email": "test@test.cl",
    "lastNames": "test",
    "phone": "123123",
    "dynamicData":{"rut": "19"}
}
```
#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "osuId": 2,
    "email": "test@test.cl",
    "name": "Test",
    "lastNames": "test",
    "phone": "123123",
    "dynamicData": {
      "rut": "19"
    },
    "createAt": 1504790470,
    "modifyAt": 1504790470,
    "address": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/user/2/address.json"
    ],
    "cart": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/2/carts.json"
    ],
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/2.json"
  }
}
```
## PUT un usuario

* `PUT /v1/admin/users/2.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "name": "TestModificado",
    "email": "test@test.cl",
    "lastNames": "test",
    "phone": "123123",
    "dynamicData":{"rut": "19"}
}
```
#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "osuId": 2,
    "email": "test@test.cl",
    "name": "TestModificado",
    "lastNames": "test",
    "phone": "123123",
    "dynamicData": {
      "rut": "19"
    },
    "createAt": 1504790470,
    "modifyAt": 1504790552,
    "address": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/user/2/address.json"
    ],
    "cart": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/2/carts.json"
    ],
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/2.json"
  }
}
```
## DELETE un usuario 

* `DELETE /v1/admin/users/2.json` elimina al usuario.
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "osuId": 2,
    "email": "test@test.cl",
    "name": "TestModificado",
    "lastNames": "test",
    "phone": "123123",
    "dynamicData": {
      "rut": "19"
    },
    "createAt": 1504790470,
    "modifyAt": 1504790552,
    "address": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/user/2/address.json"
    ],
    "cart": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/2/carts.json"
    ],
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/2.json"
  }
}
```
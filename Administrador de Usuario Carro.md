## Estructura JSON

Al realizar una petición HTTP, el servicio retornara un JSON con la siguiente estructura:
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "usId": 1,
    "cartId": 1,
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/carts/1.json"
  }
}
```
- **href**, url del usuario (String).
- **id**, identificador único de la dirección (Integer).
- **usId**, identificador único del usuario (Integer).
- **cartId**, Id del carro de compra en el ecommerce (Integer).

## GET lista los carros de un usuario

* `GET /v1/admin/users/1/carts.json` Retorna todas los carros del usuario.

#### Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, por defecto el limit es 25, el máximo permitido es 50.
- *offset*, permite paginar los items de una respuesta JSON, por defecto el offset es 0.
- *title*, Permite filtrar el titulo de direciones.
- *cartId*, Permite filtrar id del carro.
- *address*, Permite filtrar por las direcciones.
- *search*, Busca por cartId.

#### Ejemplos

* `GET /v1/admin/users/1/carts.json?limit=10&offset=0`
* `GET /v1/admin/users/1/carts.json?cartId=1`

#### Respuesta
```json
{
  "code": "200",
  "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/carts.json",
  "count": 1,
  "limit": 25,
  "offset": 0,
  "data": [
    {
      "id": 2,
      "usId": 1,
      "cartId": 1,
      "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/carts/1.json"
    }
  ]
}
```
## GET un carro

* `GET /v1/admin/users/1/carts/2.json` retornara un carro.

#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "usId": 1,
    "cartId": 1,
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/carts/1.json"
  }
}
```
## POST un carro

* `POST /v1/admin/users/1/carts.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "cartId": 1
}

```
#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "usId": 1,
    "cartId": 1,
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/carts/1.json"
  }
}
```
## DELETE un carro 

* `DELETE /v1/admin/users/1/carts/2.json` elimina el carro en el usuario.
```json
{
  "code": "200",
  "data": {
    "id": 2,
    "usId": 1,
    "cartId": 1,
    "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/admin/users/1/carts/1.json"
  }
}
```
## Estructura JSON

Al realizar una petición HTTP, el servicio retornara un JSON con la siguiente estructura:
```json
{
  "code": "200",
  "data": {
    "id": 5308,
    "token": "3796486d97797232e534050971e86338f8e9bb58",
    "clientName": "adsa",
    "clientLastName": "asdasd",
    "clientEmail": "benjamind@imaginex.cl",
    "clientPhone": "123123",
    "id_tipo_documento_tributario": 1,
    "clientCountry": "Chile",
    "clientState": "Región Metropolitana",
    "extrasUserData": {
      "user_rut": "19",
      "razon_social": "asdas",
      "giro_cliente": "asd",
      "direccion": "asd",
      "ciudad": "asd",
      "comuna": "asd"
    },
    "clientStreet": "las condes",
    "clientCityZone": "Las Condes",
    "clientPostcode": "",
    "clientBuildingNumber": "",
    "cartId": 6769,
    "cartDetails": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6769/detail.json"
    ],
    "spcId": 342,
    "ptId": 1,
    "createAt": 1504884328,
    "shippingCost": 0,
    "isMafs": 1,
    "active": 1,
    "shippingComment": "",
    "totalCart": 55980,
    "pickStoreId": "",
    "pickName": "",
    "pickCode": "",
    "id_venta_documento_tributario": 0,
    "documentNumber": 0,
    "storeId": 2,
    "marketId": 1,
    "isService": 0,
    "withdrawStore": 0,
    "payProcess": "pending",
    "integrationDetail": "https://bsale-ecommerce-benjamin007.c9users.io:8081/mercadolibre/123123.json",
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/checkout/5308.json"
  }
}
```

- **id**, identificador único del checkout (Integer).
- **token**, Hash identificador único del checkout (String).
- **clientName**, Nombre del cliente (String).
- **clientLastName**, Apellido del cliente (String).
- **clientEmail**, Email del cliente (String).
- **clientPhone**, Telefono del cliente (String).
- **id_tipo_documento_tributario**, Id del tipo documento tributario (Integer).
- **clientCountry**, Pais del cliente (String).
- **clientState**, Región del cliente (String).
- **extrasUserData**, Datos extras del documento tributario (hash).
- **clientStreet**, Calle del cliente (Integer).
- **clientCityZone**, Comuna del cliente (Integer).
- **clientPostcode**, Código postal del cliente (Integer).
- **clientBuildingNumber**, Numero de direccion del cliente (Integer).
- **cartId**, Id del carro (Integer).
- **cartDetails**, Detalle del carro (Hash).
- **spcId**, Id del costo del shipping (Integer).
- **ptId**, Id del medio de pago (Integer).
- **createAt**, Fecha de creacción (UNIX EPOCH).
- **isMafs**, El despacho es gratuito (bool).
- **active**, Activo (bool).
- **shippingComment**, Comentario del despacho (Integer).
- **totalCart**, Total bruto del carro (Integer).
- **pickName**, Nombre del que retira el pedido (Integer).
- **pickCode**, Rut del que retira el pedido (Integer).
- **pickStoreId**, Oficina donde se retira el pedido (Integer).
- **id_venta_documento_tributario**, Id del documento tributario (Integer).
- **documentNumber**, Numero de documento (Integer).
- **documentToken**, Token del docuemnto (Integer).
- **storeId**, Oficina que se genera el documento tributario(Integer).
- **marketId**, Id del market (Integer).
- **isService**, Indica si todos los producto del checkout son servicios (Integer).
- **payProcess**, Proceso del pedido (Integer).
- **payError**, Codigo de error (Integer).
- **payResponse**, Mensaje de error del medio de pago (Integer).
- **integrationDetail**, Url de integración del sistema (String)
- **url**, Url del checkout (String).


## GET lista el checkout

* `GET /v1/checkout.json` retornara todos los checkout.

#### Parametros

- *limit*, limita la cantidad de items de una respuesta JSON, por defecto el limit es 25, el máximo permitido es 50.
- *offset*, permite paginar los items de una respuesta JSON, por defecto el offset es 0.
- *expand*, permite expandir las dirreciones y de los carros. ej. expand=[cartDetails].
- *way*, Flujo como se despliega la información.
- *order*, Indica como se orderna el checkout, los valores son:id, clientName, token, totalCart o createAt .
- *clientName*, Permite filtrar por el nombre del cliente.
- *clientEmail*, Permite filtrar por el email del cliente.
- *token*, Permite filtrar por el tokent del pedido.
- *id_venta_documento_tributario*, Permite filtrar por id del docuemnto.
- *marketId*, Permite filtrar por market id.
- *search*, Busca por nombre, email, id venta documento, numero o id del medio de pago.

#### Ejemplos

* `GET /v1/checkout.json?limit=10&offset=0`
* `GET /v1/checkout.json?expand=[cartDetails]`
* `GET /v1/checkout.json?way=desc`

#### Respuesta
```json
{
  "code": "200",
  "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/checkout.json",
  "count": 5207,
  "limit": 25,
  "offset": 0,
  "data": [
    {
      "id": 5374,
      "token": "3409bd1e122e7a8909e38ad1fb4222a993d497af",
      "clientName": "adsa",
      "clientLastName": "asdasd",
      "clientEmail": "benjamind@imaginex.cl",
      "clientPhone": "123123",
      "id_tipo_documento_tributario": 1,
      "clientCountry": "Chile",
      "clientState": "Región Metropolitana",
      "extrasUserData": {
        "user_rut": "19",
        "razon_social": "asdas",
        "giro_cliente": "asd",
        "direccion": "asd",
        "ciudad": "asd",
        "comuna": "asd"
      },
      "clientStreet": "las condes",
      "clientCityZone": "Las Condes",
      "clientPostcode": "ss",
      "clientBuildingNumber": "123",
      "cartId": 6823,
      "cartDetails": [
        "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6823/detail.json"
      ],
      "spcId": 342,
      "ptId": 1,
      "createAt": 1506441661,
      "shippingCost": 0,
      "isMafs": 1,
      "active": 1,
      "shippingComment": "",
      "totalCart": 57979,
      "pickStoreId": 0,
      "pickName": "",
      "pickCode": "",
      "id_venta_documento_tributario": 18585,
      "documentNumber": 2512,
      "documentToken": "b94d918fedd6",
      "storeId": 2,
      "marketId": 1,
      "isService": 0,
      "withdrawStore": 0,
      "payProcess": "pending",
      "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/checkout/5374.json"
    },
    ...
  ],
  "next": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/checkout.json?limit=25&offset=25"
}
```
## GET un checkout

* `GET /v1/checkout/5308.json` retornara una checkout.

#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 5308,
    "token": "3796486d97797232e534050971e86338f8e9bb58",
    "clientName": "adsa",
    "clientLastName": "asdasd",
    "clientEmail": "benjamind@imaginex.cl",
    "clientPhone": "123123",
    "id_tipo_documento_tributario": 1,
    "clientCountry": "Chile",
    "clientState": "Región Metropolitana",
    "extrasUserData": {
      "user_rut": "19",
      "razon_social": "asdas",
      "giro_cliente": "asd",
      "direccion": "asd",
      "ciudad": "asd",
      "comuna": "asd"
    },
    "clientStreet": "las condes",
    "clientCityZone": "Las Condes",
    "clientPostcode": "",
    "clientBuildingNumber": "",
    "cartId": 6769,
    "cartDetails": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6769/detail.json"
    ],
    "spcId": 342,
    "ptId": 1,
    "createAt": 1504884328,
    "shippingCost": 0,
    "isMafs": 1,
    "active": 1,
    "shippingComment": "",
    "totalCart": 55980,
    "pickStoreId": 0,
    "pickName": "",
    "pickCode": "",
    "id_venta_documento_tributario": 0,
    "documentNumber": 0,
    "storeId": 2,
    "marketId": 1,
    "isService": 0,
    "withdrawStore": 0,
    "payProcess": "pending",
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/checkout/5308.json"
  }
}
```
## POST un checkout

* `POST /v1/checkout.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "clientName": "adsa",
    "clientLastName": "asdasd",
    "clientEmail": "benjamind@imaginex.cl",
    "clientPhone": "123123",
    "id_tipo_documento_tributario": 1,
    "clientCountry": "Chile",
    "clientState": "Región Metropolitana",
    "extrasUserData": {
        "user_rut": "19",
        "razon_social": "asdas",
        "giro_cliente": "asd",
        "direccion": "asd",
        "ciudad": "asd",
        "comuna": "asd"
    },
    "clientStreet": "las condes",
    "clientCityZone": "Las Condes",
    "clientPostcode": "ss",
    "clientBuildingNumber": "123",
    "cartDetails": [
        {
        "quantity": 1,
        "unitValue": 29990,
        "itemName": "Ardo Amaryll Start Sacaleche manual ",
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "productWebId": 8
        },
        {
        "quantity": 1,
        "unitValue": 29990,
        "name": "Ardo Amaryll Start Sacaleche manual ",
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "productWebId": 8
        }
    ],
    "spcId": 342,
    "ptId": 1,
    "createAt": 1504884328,
    "shippingCost": 0,
    "isMafs": 1,
    "active": 1,
    "shippingComment": "",
    "pickName": "",
    "pickCode": "",
    "id_venta_documento_tributario": 0,
    "documentNumber": 0,
    "storeId": 2,
    "marketId": 1,
    "withdrawStore": 0,
    "payProcess": "pending",
    "integrationDetail": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg"
}
```
#### Donde
- **token**, Si no viene lo crea.
- **id_tipo_documento_tributario**, Si viene valida que exista.
- **cartId**, Si no viene lo crea, Si viene valida que exista .
- **cartDetails**, Utiliza las reglas del carro.
- **spcId**,  Si viene valida que exista .
- **ptId**,  Si viene valida que exista .
- **createAt**, Es del sistema siempre se crea en el post.
- **totalCart**,  Si no viene se calcula .
- **pickStoreId**, Si viene valida que exista .
- **id_venta_documento_tributario**, Si viene valida que exista .
- **documentNumber**, Si viene valida que exista .
- **documentToken**, Si viene valida que exista .
- **storeId**, Si viene valida que exista.
- **marketId**, Si viene valida que exista .
- **isService**, Si no viene se calcula .

#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 5375,
    "token": "22ca947999fe2ddfba2b366d42f48c60a2797c51",
    "clientName": "adsa",
    "clientLastName": "asdasd",
    "clientEmail": "benjamind@imaginex.cl",
    "clientPhone": "123123",
    "id_tipo_documento_tributario": 1,
    "clientCountry": "Chile",
    "clientState": "Región Metropolitana",
    "extrasUserData": {
      "user_rut": "19",
      "razon_social": "asdas",
      "giro_cliente": "asd",
      "direccion": "asd",
      "ciudad": "asd",
      "comuna": "asd"
    },
    "clientStreet": "las condes",
    "clientCityZone": "Las Condes",
    "clientPostcode": "ss",
    "clientBuildingNumber": "123",
    "cartId": 6824,
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
    "spcId": 342,
    "ptId": 1,
    "createAt": 1506442849,
    "shippingCost": 0,
    "isMafs": 1,
    "active": 1,
    "shippingComment": "",
    "totalCart": 57979,
    "pickStoreId": 0,
    "pickName": "",
    "pickCode": "",
    "id_venta_documento_tributario": 0,
    "documentNumber": 0,
    "storeId": 2,
    "marketId": 1,
    "isService": 0,
    "withdrawStore": 0,
    "payProcess": "pending",
    "integrationDetail": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/checkout/5375.json"
  }
}
```
## PUT un usuario

* `PUT /v1/checkout/5358.json`

Se debe enviar un Json con la siguiente estructura.
```json
{
    "clientName": "adsa",
    "clientLastName": "asdasd",
    "clientEmail": "benjamind@imaginex.cl",
    "clientPhone": "123123",
    "id_tipo_documento_tributario": 1,
    "clientCountry": "Chile",
    "clientState": "Región Metropolitana",
    "extrasUserData": {
        "user_rut": "19",
        "razon_social": "asdas",
        "giro_cliente": "asd",
        "direccion": "asd",
        "ciudad": "asd",
        "comuna": "asd"
    },
    "clientStreet": "las condes",
    "clientCityZone": "Las Condes",
    "clientPostcode": "ss",
    "clientBuildingNumber": "123",
    "cartDetails": [
        {
        "id": 42,
        "quantity": 1,
        "unitValue": 29990,
        "itemName": "Ardo Amaryll Start Sacaleche manual test ",
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "productWebId": 8
        },
        {
        "quantity": 1,
        "unitValue": 29990,
        "name": "Ardo Amaryll Start Sacaleche manual ",
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "productWebId": 8
        }
    ],
    "spcId": 342,
    "ptId": 1,
    "createAt": 1504884328,
    "shippingCost": 0,
    "isMafs": 1,
    "active": 1,
    "shippingComment": "",
    "pickName": "",
    "pickCode": "",
    "id_venta_documento_tributario": 0,
    "documentNumber": 0,
    "storeId": 2,
    "marketId": 1,
    "isService": 0,
    "withdrawStore": 0,
    "payProcess": "pending",
    "integrationDetail": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg"
}
```
#### Respuesta
```json
{
  "code": "200",
  "data": {
    "id": 5358,
    "token": "c401b6d0b6e4a10884fe0909b83f249e9a03dffa",
    "clientName": "adsa",
    "clientLastName": "asdasd",
    "clientEmail": "benjamind@imaginex.cl",
    "clientPhone": "123123",
    "id_tipo_documento_tributario": 1,
    "clientCountry": "Chile",
    "clientState": "Región Metropolitana",
    "extrasUserData": {
      "user_rut": "19",
      "razon_social": "asdas",
      "giro_cliente": "asd",
      "direccion": "asd",
      "ciudad": "asd",
      "comuna": "asd"
    },
    "clientStreet": "las condes",
    "clientCityZone": "Las Condes",
    "clientPostcode": "ss",
    "clientBuildingNumber": "123",
    "cartId": 6804,
    "cartDetails": [
      {
        "id": 42,
        "quantity": 1,
        "unitValue": 29990,
        "netUnitValue": 25201.6806722689,
        "discount": 6.66889,
        "itemName": "Ardo Amaryll Start Sacaleche manual test ",
        "total": 27989,
        "discountId": 9,
        "image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "idVarianteProducto": 1019,
        "sku": "AR127",
        "link": "/product/ardo-amaryll-start-sacaleche-manual",
        "productWebId": 8,
        "cartId": 6804,
        "taxList": [
          1
        ],
        "name": "Ardo Amaryll Start Sacaleche manual test ",
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 6,
        "cd_item_name": "Ardo Amaryll Start Sacaleche manual test ",
        "cd_sub_total": 27989,
        "cd_id": 42,
        "cd_id_discount": 9,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6804/detail/42.json"
      },
      {
        "id": 43,
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
        "cartId": 6804,
        "taxList": [
          1
        ],
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 0,
        "cd_sub_total": 29990,
        "cd_id": 43,
        "cd_id_discount": 0,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6804/detail/43.json"
      },
      {
        "id": 46,
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
        "cartId": 6804,
        "taxList": [
          1
        ],
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 0,
        "cd_sub_total": 29990,
        "cd_id": 46,
        "cd_id_discount": 0,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6804/detail/46.json"
      },
      {
        "id": 47,
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
        "cartId": 6804,
        "taxList": [
          1
        ],
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 0,
        "cd_sub_total": 29990,
        "cd_id": 47,
        "cd_id_discount": 0,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6804/detail/47.json"
      },
      {
        "id": 79,
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
        "cartId": 6804,
        "taxList": [
          1
        ],
        "value": 29990,
        "cd_q": 1,
        "cd_unit_value": 29990,
        "cd_discount": 0,
        "cd_sub_total": 29990,
        "cd_id": 79,
        "cd_id_discount": 0,
        "cd_image": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
        "id_variante_producto": 1019,
        "codigo_variante_producto": "AR127",
        "href": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6804/detail/79.json"
      }
    ],
    "spcId": 342,
    "ptId": 1,
    "createAt": 1506425440,
    "shippingCost": 0,
    "isMafs": 1,
    "active": 1,
    "shippingComment": "",
    "totalCart": 147949,
    "pickStoreId": 0,
    "pickName": "",
    "pickCode": "",
    "id_venta_documento_tributario": 0,
    "documentNumber": 0,
    "storeId": 2,
    "marketId": 1,
    "isService": 0,
    "withdrawStore": 0,
    "payProcess": "pending",
    "integrationDetail": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/checkout/5358.json"
  }
}
```
## DELETE un checkout 

* `DELETE /v1/checkout/5358.json` desactiva un checkout.
```json
{
  "code": "200",
  "data": {
    "id": 5358,
    "token": "c401b6d0b6e4a10884fe0909b83f249e9a03dffa",
    "clientName": "adsa",
    "clientLastName": "asdasd",
    "clientEmail": "benjamind@imaginex.cl",
    "clientPhone": "123123",
    "id_tipo_documento_tributario": 1,
    "clientCountry": "Chile",
    "clientState": "Región Metropolitana",
    "extrasUserData": {
      "user_rut": "19",
      "razon_social": "asdas",
      "giro_cliente": "asd",
      "direccion": "asd",
      "ciudad": "asd",
      "comuna": "asd"
    },
    "clientStreet": "las condes",
    "clientCityZone": "Las Condes",
    "clientPostcode": "ss",
    "clientBuildingNumber": "123",
    "cartId": 6804,
    "cartDetails": [
      "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/cart/6804/detail.json"
    ],
    "spcId": 342,
    "ptId": 1,
    "createAt": 1506425440,
    "shippingCost": 0,
    "isMafs": 1,
    "active": 0,
    "shippingComment": "",
    "totalCart": 147949,
    "pickStoreId": 0,
    "pickName": "",
    "pickCode": "",
    "id_venta_documento_tributario": 0,
    "documentNumber": 0,
    "storeId": 2,
    "marketId": 1,
    "isService": 0,
    "withdrawStore": 0,
    "payProcess": "pending",
    "integrationDetail": "https://dojiw2m9tvv09.cloudfront.net/1680/product/home-productos-059963.jpg",
    "url": "https://bsale-ecommerce-benjamin007.c9users.io:8081/v1/checkout/5358.json"
  }
}
```
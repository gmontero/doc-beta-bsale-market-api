## BsaleMarket API

Esta API permite llamadas del tipo [REST] y utiliza [JSON] para el envío y recepción de información.

## Convenciones utilizadas

* Peticiones sobre SSL
* Se usan sustantivos, no verbos.
* Se utilizan dos urls base por recurso "/clients.json", "clients/1.json"
* Siempre se usa el nombre del recurso en plural.
* Se envía la url del recurso.
* Respuesta en una estructura JSON con los atributos en camelCase.
* todas las respuestas son en ingles (atributos y mensajes).
* Manejo de versiones en la url.
* Manejo de errores y estados en las respuestas.
* Paginacion de la respuesta JSON.
* Permitir acceder a las relaciones de un recurso a través de la variable expand en una sola petición.
* Permitir devolver solo los atributos requeridos a través de la variable fields.
* Las fechas se trabaja como enteros, por ejemplo 1388545200 corresponde a la fecha 2014-01-01, la conversión es realizada utilizando el [Tiempo Unix].

Si necesitas aprender como trabaja Bsale puedes revisar nuestros videos de [capacitación]

[REST]:http://es.wikipedia.org/wiki/Representational_State_Transfer
[JSON]:http://www.json.org/
[Tiempo Unix]:http://es.wikipedia.org/wiki/Tiempo_Unix
[capacitación]:https://www.youtube.com/playlist?list=PLPUKtN2zmQABmyQKwpWLPU0DFIQv3FMih
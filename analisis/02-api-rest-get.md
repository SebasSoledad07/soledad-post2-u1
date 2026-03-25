# Análisis 2: Petición GET a API REST Pública

Este análisis documenta la interacción con la API de pruebas JSONPlaceholder para entender cómo se transfieren datos estructurados (JSON) y cómo se manejan los códigos de error.

## Información general

- URL: https://jsonplaceholder.typicode.com/posts/1
- Método: GET
- Código de estado: 304 Not Modified (Validado por caché)

## Headers de Relevantes

| Header          | Valor                             | Significado                                                                           |
| --------------- | --------------------------------- | ------------------------------------------------------------------------------------- |
| Content-Type    | [application/json; charset=utf-8] | [Indica que el cuerpo de la respuesta contiene datos en formato JSON.]                |
| Cf-Cache-Status | [HIT]                             | [La respuesta fue entregada por el servidor perimetral de Cloudflare desde el caché.] |

## Cuerpo de la Respuesta (JSON)

```text
{
"userId": 1,
"id": 1,
"title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
"body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae..."
}
```

## Petición a Recurso Inexistente (/posts/999)

## Información general

- URL: https://jsonplaceholder.typicode.com/posts/999
- Método: GET
- Código de estado: 404 Not Found

## Análisis del error

El código 404 indica que el servidor fue capaz de comunicarse con el cliente, pero no encontró el recurso específico solicitado. A pesar de ser un error, el servidor responde con un Content-Type: application/json, aunque el cuerpo de la respuesta es un objeto vacío {} según se observa en la pestaña "Response".

## Comparación: Página HTML vs API REST

| Característica | Petición HTML (Example.com)                 | Petición API (JSONPlaceholder)                     |
| -------------- | ------------------------------------------- | -------------------------------------------------- |
| Content-Type   | [text/html]                                 | [application/json]                                 |
| Propósito      | [Visualización en navegador (Renderizado).] | [Intercambio de datos (Consumo por aplicaciones).] |
| Legibilidad    | [Estructura visual para humanos.]           | [Estructura lógica para máquinas/código.]          |

## Conclusión

A través de este ejercicio se comprobó la diferencia fundamental entre navegar por una página web y consumir una API. Mientras que la primera devuelve etiquetas HTML para ser renderizadas, la API devuelve objetos JSON que permiten la interoperabilidad entre sistemas. Se observó que el manejo de errores (como el 404) es consistente en las APIs, devolviendo tipos de contenido coherentes (JSON) incluso cuando el recurso no existe. Además, se reafirmó la importancia del sistema de caché mediante el código 304, optimizando la entrega de datos recurrentes.

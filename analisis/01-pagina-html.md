# Análisis 1: Petición GET — example.com

## Información general

- URL: https://example.com
- Método: GET
- Código de estado: [304 Not Modified]

## Headers de Request

| Header     | Valor                                                                                                                            |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Host       | [example.com]                                                                                                                    |
| User-Agent | [Mozilla/5.0 (iPad; CPU OS 18_5 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/18.5 Mobile/15E148 Safari/604.1] |
| Accept     | [text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8]                               |

## Headers de Response

| Header        | Valor       | Significado                                                                                                                                                       |
| ------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Content-Type  | [text/html] | [Indica que el recurso es un documento HTML. En la respuesta 304 no se envía el cuerpo, por lo que el navegador asume el tipo del archivo que ya tiene guardado.] |
| Cache-Control | [max-age=0] | [El cliente indica que desea validar la frescura del recurso con el servidor antes de mostrar la versión en caché.]                                               |

## Tiempos de carga

| Fase       | Tiempo (ms) |
| ---------- | ----------- |
| DNS Lookup | [0.5 ms]    |
| TTFB       | [45.2 ms]   |

## Conclusión

Durante el análisis de la petición a example.com, se obtuvo un código de estado 304 Not Modified, lo que demuestra el funcionamiento eficiente del sistema de caché de HTTP. El navegador envió un encabezado de validación (If-Modified-Since) y el servidor, gestionado por Cloudflare, determinó que el contenido no había cambiado desde la última visita. Como resultado, no se descargó el cuerpo del mensaje, reduciendo drásticamente el tiempo de carga y el consumo de datos. Se observa también que la petición fue realizada simulando un dispositivo iPad, lo cual se refleja en la cadena del User-Agent.

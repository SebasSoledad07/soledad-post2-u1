# Análisis de Peticiones HTTP — Unidad 1

## Descripción

Este repositorio contiene el análisis detallado de peticiones HTTP/HTTPS realizado mediante el uso de Chrome DevTools y Postman. El objetivo es inspeccionar el ciclo de vida de las peticiones, identificar códigos de estado, analizar encabezados (headers) y comprender la transferencia de datos en aplicaciones web.

Este trabajo forma parte del laboratorio 2 de la asignatura Programación Web (Séptimo Semestre) de la Ingeniería de Sistemas en la Universidad Francisco de Paula Santander.

## Herramientas utilizadas

- Google Chrome + DevTools: Panel Network para inspección de tráfico en tiempo real.
- Postman: Para la simulación de peticiones POST y ejecución de tests automatizados.
- VS Code: Entorno de desarrollo para la documentación.
- Git/GitHub: Control de versiones y publicación del análisis.

## Análisis realizados

| #   | Tipo               | URL                 | Código           | Resultado esperado  |
| --- | ------------------ | ------------------- | ---------------- | ------------------- |
| 1   | GET HTML           | https://example.com | 304 Not Modified | Éxito (Caché)       |
| 2   | GET JSON (exitoso) | /posts/1            | 304 Not Modified | Éxito (API)         |
| 3   | GET JSON (fallido) | /posts/999          | 404 Not Found    | Recurso inexistente |
| 4   | POST JSON          | /posts              | 201 Created      | Recurso creado      |

## Estructura del Proyecto

- analisis/: Contiene los reportes detallados de cada fase del laboratorio.

- capturas/: Evidencias visuales de los headers, códigos de estado y resultados de Postman.

## Conclusiones

A través de este laboratorio se logró comprender la importancia de los códigos de estado HTTP para el diagnóstico de aplicaciones web, identificando cómo el código 304 optimiza la red mediante el uso de caché y cómo el código 201 confirma la persistencia de datos tras un método POST. La comparación entre text/html y application/json permitió visualizar la diferencia entre el contenido destinado al usuario final y los datos estructurados para el intercambio entre sistemas. Finalmente, el uso de herramientas como Postman demostró ser vital para validar la lógica del lado del servidor mediante pruebas automatizadas que aseguran la integridad de las respuestas.

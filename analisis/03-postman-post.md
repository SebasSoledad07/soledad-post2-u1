# Análisis 3: Petición POST Simulada con Postman

En esta fase del laboratorio, se utilizó Postman para simular el envío de datos a un servidor, lo cual es fundamental en el desarrollo de aplicaciones que permiten crear recursos (como registros de usuarios, publicaciones, etc.).

## 1. Configuración de la Petición

- URL: https://jsonplaceholder.typicode.com/posts
- Método: POST
- Headers: Content-Type: application/json
- Cuerpo (Body - raw JSON):

```text
{
  "title": "Laboratorio Programacion Web",
  "body": "Analisis de peticiones HTTP con Postman.",
  "userId": 1
}

```

## 2. Respuesta del Servidor

- Código de estado: 201 Created
- Tiempo de respuesta: 335 ms
- Cuerpo de la respuesta:

```text
{
  "title": "Laboratorio Programacion Web",
  "body": "Analisis de peticiones HTTP con Postman.",
  "userId": 1,
  "id": 101
}
```

## 3. Pruebas Automáticas (Tests)

Se implementaron scripts de prueba en JavaScript dentro de Postman para validar la respuesta:

- Status 201 Created: Verifica que el código de estado sea exactamente 201.

- Respuesta incluye id asignado: Verifica que el objeto retornado tenga la propiedad id y que el título coincida con el enviado.

Resultado: PASS (2/2 tests aprobados).

## Diferencias entre GET y POST

| Característica     | GET                                             | POST                                                   |
| ------------------ | ----------------------------------------------- | ------------------------------------------------------ |
| **Propósito**      | Recuperar información del servidor.             | Enviar datos para crear un nuevo recurso.              |
| **Cuerpo (Body)**  | No suele incluir cuerpo de mensaje.             | Incluye los datos del recurso a crear.                 |
| **Código Exitoso** | Generalmente 200 OK.                            | Generalmente 201 Created.                              |
| **Idempotencia**   | Es idempotente (repetirlo no cambia el estado). | No es idempotente (repetirlo crea múltiples recursos). |

# Conclusión

El uso de Postman permitió validar que el endpoint de creación de la API funciona según lo esperado. Se confirmó que el método POST requiere una estructura de datos definida en el cuerpo y que, a diferencia de las peticiones de lectura (GET), el servidor responde con un código 201 para confirmar la creación exitosa. La implementación de pruebas automáticas asegura que la lógica del servidor (como la asignación de IDs) se mantenga consistente, facilitando la depuración y el desarrollo continuo de aplicaciones web.

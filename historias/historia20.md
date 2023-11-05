# Historia de usuario de ver partes del cuerpo para entrenar

Yo: como usuario de la aplicación,
Quiero: ver una lista de que partes del cuerpo puedo entrenar,
Para: poder posteriormente seleccionar los ejercicios que deseo realizar.

## Criterios de aceptación

- El usuario debe poder ver una lista de que partes del cuerpo puede entrenar.

#### Prototipo de baja fidelidad

- Dado: Que el usuario inicio sesión y se encuentra en la página de inicio de la aplicación.
- Cuando: El usuario cargue la página de inicio.
- Entonces: El usuario podrá ver una lista de que partes del cuerpo puede entrenar.

## Análisis y diseño

<img src="../assets/historia20.png" alt="Historia de usuario de ver partes del cuerpo para entrenar" width="500px" ><br/>

- El usuario debe poder ver una lista de que partes del cuerpo puede entrenar porque es una funcionalidad básica de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario ver una lista de las partes del cuerpo que puede entrenar. Todo con la finalidad de que el usuario pueda seleccionar la parte del cuerpo que desea entrenar y posteriormente ver los ejercicios que puede realizar. Cada una de las cards de las partes del cuerpo tendrá un botón que permitirá al usuario ver los ejercicios que puede realizar para esa parte del cuerpo.

### Lo que devuleve la API

#### Obtener lista de partes del cuerpo

- En la pantalla principal de la aplicación se devuelve un get del api externo donde se muestra todos los ejercicios que hay:

    Request:

        ```
        GET https://wger.de/api/v2/exercisecategory/
        Accept: application/json
        ```

    Response: Exitoso statusCode: 200
    
        ```
        [
            {
                "id": 1,
                "name": "Biceps"
            },
            {
                "id": 2,
                "name": "Pecho"
            },
            ... y así sucesivamente
        ]
        ```
    
    Response: Error statusCode: 404
    
        ```
        {
            "status": 404,
            "error": "Bad Request",
            "message": "No se encontró la lista de ejercicios",
            "path": "/api/v2/exercisecategory"
        }
        ```
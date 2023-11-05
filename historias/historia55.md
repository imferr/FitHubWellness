# Historia de usuario de poder ver tips en base a tu IMC

Yo: como usuario de la aplicación,
Quiero: poder ver tips en base a mi indice de masa corporal,
Para: poder saber que ejercicios me convienen más o que debo de hacer para mejorar mi salud.

## Criterios de aceptación

- El usuario debe poder ver tips en base a su indice de masa corporal o estado.

#### Prototipo de baja fidelidad

- Dado: Que el usuario inicio sesión.
- Cuando: El usuario seleccione la opción de IMC.
- Entonces: El usuario podrá ver tips en base a su indice de masa corporal o estado.

## Análisis y diseño

<img src="../assets/historia50.png" alt="Historia de usuario de poder ver tips en base a tu IMC" width="500px" ><br/>

- El usuario debe poder ver tips en base a su indice de masa corporal o estado porque es una funcionalidad básica de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario ver tips en base a su indice de masa corporal o estado. El usuario podrá ver tips en base a su indice de masa corporal o estado. Los tips estarán almacenados en una lista ya guardada en la base de datos y se mostrarán en base a su estado.

### Lo que devuleve la API

#### Ver tips en base a tu IMC

- Al momento de ver los tips en base a su indice de masa corporal o estado, la API devolverá una lista de tips en base a su estado.

    Request:
    
        ```
        GET http://localhost:8080/api/v1/users/1/tips
        Accept: application/json
        ```

    Response: Exitoso statusCode: 200
    
        ```
        {
            "tip": "Para mantener un peso saludable, equilibra las calorías que consumes con las que quemas (usa la calculadora de calorías para saber cuántas calorías debes consumir al día), aumenta tu consumo de frutas y verduras, y limita el consumo de alimentos procesados y bebidas azucaradas."
            "estado": "ideal"
        }
        ```
    
    Response: Error statusCode: 404
    
        ```
        {
            "status": 404,
            "error": "Not Found",
            "message": "",
            "path": "/api/v1/users/1/tips"
        }
        ```
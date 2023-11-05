# Historia de usuario de poder ver tu historial de IMC

Yo: como usuario de la aplicación,
Quiero: poder ver mi historial de indice de masa corporal,
Para: poder saber como fue mi progreso con respecto a mi peso.

## Criterios de aceptación

- El usuario debe poder ver su historial de indice de masa corporal.
- El usuario debe poder ver su peso y altura en cada registro de su historial de indice de masa corporal.
- El usuario debe poder ver la fecha en la que se registro cada indice de masa corporal.

#### Prototipo de baja fidelidad

- Dado: Que el usuario inicio sesión y se encuentra en la página de IMC de la aplicación.
- Cuando: El usuario seleccione la opción de ver historial.
- Entonces: El usuario podrá ver su historial de indice de masa corporal.

## Análisis y diseño

<img src="../assets/historia50.png" alt="Historia de usuario de poder ver tu historial de IMC" width="500px" ><br/>
<img src="../assets/historia60.png" alt="Historia de usuario de poder ver tu historial de IMC" width="500px" ><br/>

- El usuario debe poder ver su historial de indice de masa corporal porque es una funcionalidad básica de la aplicación.
- El usuario debe poder ver su peso y altura en cada registro de su historial de indice de masa corporal porque es una funcionalidad básica de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario ver su historial de indice de masa corporal. El usuario podrá ver su peso y altura en cada registro de su historial de indice de masa corporal. El usuario podrá ver la fecha en la que se registro cada indice de masa corporal. En la primera fotografia, en la parte de la derecha hay un botón que permite al usuario ver su historial de indice de masa corporal. En la segunda fotografia, se muestra el historial de indice de masa corporal del usuario.

### Lo que devuleve la API

#### Ver historial de IMC

- Al momento de ver su historial de indice de masa corporal, la API devolverá el peso, altura, indice de masa corporal, estado y fecha de cada registro de indice de masa corporal.

    Request:

        ```
        GET http://localhost:8080/api/v1/users/1/imc
        Accept: application/json
        ```

    Response: Exitoso statusCode: 200

        ```
        {
            "imcs": [
                {
                    "id": 1,
                    "peso": 56,
                    "altura": 1.56,
                    "estado": "ideal",
                    "imc": 20.00
                    “fechaCreacion”: “2022-05-05”
                },
                {
                    "id": 2,
                    "peso": 60,
                    "altura": 1.70,
                    "estado": "normal",
                    "imc": 20.76
                    “fechaCreacion”: “2022-05-05”
                },
                {
                    "id": 3,
                    "peso": 68,
                    "altura": 1.65,
                    "estado": "sobrepeso",
                    "imc": 24.98
                    “fechaCreacion”: “2022-05-05”
                }
            ]
        }
        ```

    Response: Error statusCode: 404

        ```
        {
            "status": 404,
            "error": "Not Found",
            "message": "",
            "path": "/api/v1/users/1/imc"
        }
        ```
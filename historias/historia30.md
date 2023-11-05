# Historia de usuario de ver rutina y ejercicios por rutina

Yo: como usuario de la aplicación,
Quiero: ver una lista de rutinas de entrenamiento y los ejercicios que hay dentro de cada rutina,
Para: poder seleccionar una rutina y ver los ejercicios que hay dentro de ella.

## Criterios de aceptación

- El usuario debe poder ver una lista de rutinas de entrenamiento y los ejercicios que hay dentro de cada rutina.

#### Prototipo de baja fidelidad

- Dado: Que el usuario inicio sesión y se encuentra en la página de mis rutinas de la aplicación.
- Cuando: El usuario cargue la página de mis rutinas y/o seleccione una rutina de entrenamiento.
- Entonces: El usuario podrá ver una lista de rutinas de entrenamiento y los ejercicios que hay dentro de cada rutina. 

## Análisis y diseño

<img src="../assets/historia35.png" alt="Historia de usuario de ver rutina y ejercicios por rutina" width="500px" ><br/>
<img src="../assets/historia30.png" alt="Historia de usuario de ver rutina y ejercicios por rutina" width="500px" ><br/>

- El usuario debe poder ver una lista de rutinas de entrenamiento y los ejercicios que hay dentro de cada rutina porque es una funcionalidad básica de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario ver una lista de rutinas de entrenamiento. Todo con la finalidad de que el usuario pueda seleccionar una rutina y ver los ejercicios que hay dentro de ella. Cada una de las cards de las rutinas tendrá un botón que permitirá al usuario ver los ejercicios que hay dentro de esa rutina. En la primera fotografia se muestra la interfaz de usuario para ver las rutinas. En la segunda fotografia se muestra la interfaz de usuario para ver los ejercicios que hay dentro de una rutina.

### Lo que devuleve la API

#### Obtener lista de rutinas

- Para las rutinas de un usuario, al momento de ingresar a ver las listas tenemos el siguiente get que nos devuelve las listas de las rutinas creadas por el usuario:

    Request:

        ```
        GET http://localhost:8080/api/v1/users/1/rutinas
        Accept: application/json
        ```

    Response: Exitoso statusCode: 200
    
        ```
        [
            {
                "rutinaId": 1,
                "nombreRutina": "Rutina de Fuerza",
                “fechaCreacion”: “2022-05-05”,
                "descripcion": "Con una barra sobre tus hombros, baja tu cuerpo hasta que tus muslos estén paralelos al suelo y luego regresa a la posición inicial."
            },
            {
                "rutinaId": 2,
                "nombreRutina": "Rutina de Flexibilidad",
                “fechaCreacion”: “2022-05-05”,
                "descripcion": "Sentado en el suelo, estira una pierna y flexiona la otra. Intenta tocar la punta del pie con las manos."
            }
        ]
        ```

    Response: Error statusCode: 404

    ```
    {
        "status": 404,
        "error": "Bad Request",
        "detail": "No se pudo obtener la lista de rutinas"
        "path": "/api/v1/users/1/rutinas
    }

#### Obtener ejercicios de una rutina

- Para obtener los ejercicios al momento de ingresar a una lista se tiene el siguiente get:

    Request:

        ```
        GET http://localhost:8080/api/v1/users/1/rutinas/1
        Accept: application/json
        ```

    Response: Exitoso statusCode: 200
    
        ```
        {
            "rutinaId": 1,
            "nombreRutina": "Rutina de Fuerza",
            "ejercicios": [
                {
                    "ejercicioId": 10,
                    "nombreEjercicio": "Press de Banca",
                    "descripcion": "Presiona una barra desde el pecho hasta la extensión completa de los brazos mientras estás acostado en una banca."
                },
                {
                    "ejercicioId": 11,
                    "nombreEjercicio": "Sentadillas",
                    "descripcion": "Con una barra sobre tus hombros, baja tu cuerpo hasta que tus muslos estén paralelos al suelo y luego regresa a la posición inicial."
                },
                {
                    "ejercicioId": 12,
                    "nombreEjercicio": "Deadlift",
                    "descripcion": "Levanta una barra desde el suelo hasta la altura de la cintura manteniendo la espalda recta."
                }
            ]
        }
        ```

    Response: Error statusCode: 404
    
        ```
        {
            "status": 404,
            "error": "Bad Request",
            "detail": "No se pudo obtener la lista de ejercicios de la rutina"
            "path": "/api/v1/users/1/rutinas/1
        }
        ```
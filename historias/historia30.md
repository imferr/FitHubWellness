# Historia de usuario de agregar y ver rutina

Yo: como usuario de la aplicación,
Quiero: poder agregar una rutina de entrenamiento,
Para: poder realizarla posteriormente y ver esa lista de rutinas.

## Criterios de aceptación

- El usuario debe poder crear una lista de rutinas nueva.
- El usuario debe poder ver una lista de rutinas de entrenamiento.

## Análisis y diseño

<img src="../assets/historia30.png" alt="Historia de usuario de agregar y ver rutina" width="500px" ><br/>

- El usuario debe poder crear una lista de rutinas nueva porque es una funcionalidad básica de la aplicación.
- El usuario debe poder ver una lista de rutinas de entrenamiento porque es una funcionalidad básica de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario crear una lista de rutinas nueva. Al mismo tiempo, el usuario podrá ver las rutinas de entrenamiento que ha creado y los ejercicios que hay dentro de cada rutina.

### Lo que devuleve la API

- Para las rutinas de un usuario, al momento de ingresar a ver las listas tenemos el siguiente get que nos devuelve las listas de las rutinas creadas por el usuario:

    ```
    GET http://localhost:8080/api/v1/users/1/rutinas
    [
    {
        "rutinaId": 1,
        "nombreRutina": "Rutina de Fuerza",
        “fechaCreacion”: “2022-05-05”,
        "descripcion": "Con una barra sobre tus hombros, baja tu cuerpo hasta que tus muslos estén
        paralelos al suelo y luego regresa a la posición inicial."
    },
    {
        "rutinaId": 2,
        "nombreRutina": "Rutina de Flexibilidad",
        “fechaCreacion”: “2022-05-05”,
        "descripcion": "Sentado en el suelo, estira una pierna y flexiona la otra. Intenta tocar la punta 
        del pie con las manos."
    }
    ]
    ```

- Para obtener los ejercicios al momento de ingresar a una lista se tiene el siguiente get:

    ```
    GET http://localhost:8080/api/v1/users/1/rutinas/1
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
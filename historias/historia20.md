# Historia de usuario de pagina de inicio

Yo: como usuario de la aplicación,
Quiero: ver una página de inicio donde se muestren todos los ejercicios que puedo realizar,
Para: poder añadirlos posteriormente a mi rutina de entrenamiento.

## Criterios de aceptación

- El usuario debe poder ver una lista de ejercicios.
- El usuario debe poder añadir un ejercicio a su rutina de entrenamiento.
- El usuario debe poder crear una lista de rutinas nueva.

## Análisis y diseño

<img src="../assets/historia20.png" alt="Historia de usuario de pagina de inicio" width="500px" ><br/>

- El usuario debe poder ver una lista de ejercicios porque es la funcionalidad principal de la aplicación.
- El usuario debe poder añadir un ejercicio a su rutina de entrenamiento porque es la funcionalidad principal de la aplicación.
- El usuario debe poder crear una lista de rutinas nueva porque es la funcionalidad principal de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario ver una lista de ejercicios que serán recibidas por la API externa de WGER. El usuario podrá añadir un ejercicio a su rutina de entrenamiento y podrá crear una lista de rutinas nueva si es que así lo desea.

### Lo que devuleve la API

- En la pantalla principal de la aplicación se devuelve un get del api externo donde se muestra todos los ejercicios que hay:

    ```
    GET https://wger.de/api/v2/exercisecategory/
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

- Al momento de seleccionar una de las categorías que vamos a entrenar obtendremos la lista de los ejercicios que hay en esa categoría:

    ```
    GET https://wger.de/api/v2/exercise/?language=2&category=[ID_CATEGORIA]
    {
    "count": 3
    "results": [
        {
        "id": 1,
        "name": "Martillo",
        "description": "Descripción detallada del ejercicio Martillo...",
        "category": [ID_CATEGORIA],
        },
        {
        "id": 2,
        "name": "Unilateral",
        "description": "Descripción detallada del ejercicio Unilateral...",
        "category": [ID_CATEGORIA],
        },
        {
        "id": 3,
        "name": "Prono",
        "description": "Descripción detallada del ejercicio Prono...",
        "category": [ID_CATEGORIA],
        }
    ]
    }
    ```
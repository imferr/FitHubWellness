# Historia de usuario de agregar ejercicio a rutina

Yo: como usuario de la aplicación,
Quiero: poder agregar un ejercicio a mi rutina de entrenamiento,
Para: poder realizarlo posteriormente y ver esa lista de ejercicios de mi rutina.

## Criterios de aceptación

- El usuario debe poder agregar un ejercicio a su rutina de entrenamiento.
- El usuario debe poder eliminar un ejercicio de su rutina de entrenamiento.

#### Prototipo de baja fidelidad

- Dado: Que el usuario inicio sesión y se encuentra en la página de mis rutinas/inicio de la aplicación.
- Cuando: El usuario seleccione un ejercicio de la lista de ejercicios.
- Entonces: El usuario podrá agregar ese ejercicio a su rutina de entrenamiento.

## Análisis y diseño

<img src="../assets/historia40.png" alt="Historia de usuario de agregar ejercicio a rutina" width="500px" ><br/>
<img src="../assets/historia41.png" alt="Historia de usuario de agregar ejercicio a rutina" width="500px" ><br/>

- El usuario debe poder agregar un ejercicio a su rutina de entrenamiento porque es una funcionalidad básica de la aplicación.
- El usuario debe poder eliminar un ejercicio de su rutina de entrenamiento porque es una funcionalidad básica de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario agregar un ejercicio a su rutina de entrenamiento. Todo con la finalidad de que el usuario pueda realizarlo posteriormente y ver esa lista de ejercicios de su rutina. En la primera fotografia se ve la interfaz de inicio cuando se seleccionó una categoria y se muestra la lista de ejercicios, cada ejercicio tiene un botón que permite agregarlo a la rutina. En la segunda fotografia se ve la interfaz de 'mis rutinas' donde al momento de estar dentro de una rutina donde se muestran los ejercicios que se agregaron a la rutina, en la parte inferior hay un botón que permite agregar un ejercicio a la rutina y en cada card de ejercicio hay un botón que permite eliminar el ejercicio de la rutina.

### Lo que devuleve la API

#### Agregar ejercicio a rutina

- Al momento de agregar un ejercicio a la lista de ejercicios de la rutina se manda la solicitud del id que tiene el ejercicio y para eso es el siguiente post dentro de la lista:

    Request:
    
        ```
        POST http://localhost:8080/api/v1/users/1/rutinas/1/ejercicios
        Content-Type: application/json
        Accept: application/json
        {
            "ejercicioId": 14
        }
        ```

    Response: Exitoso statusCode: 201

        ```
        {
            "rutinaId": 1,
            "nombreRutina": "Rutina de Fuerza",
            “fechaCreacion”: “2022-05-05”,
            "descripcion": "Con una barra sobre tus hombros, baja tu cuerpo hasta que tus muslos estén paralelos al suelo y luego regresa a la posición inicial.",
            "ejercicios": [
                {
                    "ejercicioId": 14,
                    "nombreEjercicio": "Sentadilla",
                    "descripcion": "Con una barra sobre tus hombros, baja tu cuerpo hasta que tus muslos estén paralelos al suelo y luego regresa a la posición inicial."
                }
            ]
        }
        ```
    
    Response: Error statusCode: 400

        ```
        {
            "detail": "No se pudo agregar el ejercicio a la rutina"
        }
        ```

#### Eliminar ejercicio de rutina

- Al momento de eliminar un ejercicio de la lista de ejercicios de la rutina se manda la solicitud del id que tiene el ejercicio y para eso es el siguiente delete dentro de la lista:

    Request:
    
        ```
        DELETE http://localhost:8080/api/v1/users/1/rutinas/1/ejercicios/14
        Content-Type: application/json
        Accept: application/json
        {
            "ejercicioId": 14
        }
        ```

    Response: Exitoso statusCode: 200

        ```
        {
            "rutinaId": 1,
            "nombreRutina": "Rutina de Fuerza",
            “fechaCreacion”: “2022-05-05”,
            "descripcion": "Con una barra sobre tus hombros, baja tu cuerpo hasta que tus muslos estén paralelos al suelo y luego regresa a la posición inicial.",
            "ejercicios": []
        }
        ```

    Response: Error statusCode: 400

        ```
        {
            "detail": "No se pudo eliminar el ejercicio de la rutina"
        }
        ```
# Historia de usuario de agregar ejercicio a una nueva rutina

Yo: como usuario de la aplicación,
Quiero: poder agregar un ejercicio a una nueva rutina de entrenamiento,
Para: poder realizarlo posteriormente y ver esa lista de ejercicios de mi rutina.

## Criterios de aceptación

- El usuario debe poder agregar un ejercicio a una nueva rutina de entrenamiento.
- El usuario debe poder eliminar un ejercicio de una nueva rutina de entrenamiento.

## Análisis y diseño

<img src="../assets/historia40.png" alt="Historia de usuario de agregar ejercicio a una nueva rutina" width="500px" ><br/>

- El usuario debe poder agregar un ejercicio a una nueva rutina de entrenamiento porque es una funcionalidad básica de la aplicación.
- El usuario debe poder eliminar un ejercicio de una nueva rutina de entrenamiento porque es una funcionalidad básica de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario agregar un ejercicio a una nueva rutina de entrenamiento. Al mismo tiempo, el usuario podrá eliminar un ejercicio de una nueva rutina de entrenamiento.

### Lo que devuleve la API

- Al momento de seleccionar un ejercicio se da la opcion de seleccionar una lista existente o nueva, si es nueva primero se crea la lista de rutinas y luego se agrega el ejercicio a la lista de rutinas:
    
    ```
    POST http://localhost:8080/api/v1/users/1/rutinas
    Content-Type: application/json
    Accept: application/json
    {
        "nombreRutina": "Rutina de Fuerza",
        "descripcion": "Con una barra sobre tus hombros, baja tu cuerpo hasta que tus muslos estén paralelos al suelo y luego regresa a la posición inicial."
    }
    ```
    
    ```
    POST http://localhost:8080/api/v1/users/1/rutinas/1/ejercicios
    Content-Type: application/json
    Accept: application/json
    {
        "ejercicioId": 14
    }
    ```
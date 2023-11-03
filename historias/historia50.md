# Historia de usuario de poder ver tu IMC

Yo: como usuario de la aplicación,
Quiero: poder ver mi indice de masa corporal y agregar mi peso y altura,
Para: poder saber si estoy en un peso saludable o no.

## Criterios de aceptación

- El usuario debe poder ver su indice de masa corporal.
- El usuario debe poder agregar su peso y altura.

## Análisis y diseño

<img src="../assets/historia50.png" alt="Historia de usuario de poder ver tu IMC" width="500px" ><br/>

- El usuario debe poder ver su indice de masa corporal porque es una funcionalidad básica de la aplicación.
- El usuario debe poder agregar su peso y altura porque es una funcionalidad básica de la aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario ver su indice de masa corporal. El usuario podrá agregar su peso y altura para poder calcular su indice de masa corporal.

### Lo que devuleve la API

- Al momento de ver su indice de masa corporal, la API devolverá el peso, altura, indice de masa corporal y el estado en el que se encuentra el usuario.

    ```
    GET http://localhost:8080/api/v1/users/1/imc 
    {
    "id": 1,
    "peso": 56,
    "altura": 1.56,
    "estado": "ideal",
    "imc": 20.00
    }
    ```

- Al presionar NUEVO se habilitan los campos para añadir un nuevo peso y altura, un post:
    
    ```
    POST http://localhost:8080/api/v1/users/1/imc/register
    Content-Type: application/json
    Accept: application/json
    {
        "peso": "56",
        "altura": "1.65",
    }
    ```
# Historia de usuario 50: Crear nueva rutina

- Yo: como usuario de la aplicación,
- Quiero: poder crear una nueva rutina de ejercicios,
- Para: poder seguir una rutina de ejercicios personalizada.

## Especificación de requerimientos

- El sistema debe permitir al usuario crear una nueva rutina de ejercicios.
- (Aún no definido) El usuario puede añadir n ejercicios a la rutina de ejercicios.
- Los campos de nombre y descripción deben ser obligatorios.

## Análisis

A continuación se presenta la pantalla de crear nueva rutina, cuyo funcionamiento es:

1. El usuario hace click en el botón de "Nueva rutina".
2. El sistema muestra al usuario la opción de crear una nueva rutina de ejercicios, donde se le pide nombre y descripción.

<img src="../assets/historia50.png" alt="Pantalla de crear nueva rutina" heigth="300"/>

A continuación se presenta la pantalla de inicio, cuyo funcionamiento es:

1. El sistema muestra al usuario en la página de inicio la opción de añadir un ejercicio a su rutina de ejercicios.
2. El usuario hace click en el botón de "Añadir ejercicio".
3. El sistema muestra al usuario la opción de añadir un ejercicio a una rutina de ejercicios existente o crear una nueva rutina de ejercicios.
4. El usuario puede selecciona una rutina de ejercicios nueva.

<img src="../assets/historia30.png" alt="Pantalla de crear nueva rutina" width="500"/>

## Critertios de aceptación

#### Prototipo de baja fidelidad

- Dado: que el usuario está en la página de inicio.
- Cuando: el usuario hace click en el botón de "Añadir ejercicio".
- Entonces: el sistema muestra al usuario la opción de añadir un ejercicio a una rutina de ejercicios existente o crear una nueva rutina de ejercicios.

#### Prototipo de baja fidelidad

- Dado: que el usuario está en la página de mis rutinas.
- Cuando: el usuario hace click en el botón de "Nueva rutina".
- Entonces: el sistema muestra al usuario la opción de crear una nueva rutina de ejercicios, donde se le pide nombre y descripción.

## Diseño

### Integración con las APIs

#### Al momento de crear una nueva rutina de ejercicios

- Request: `POST /api/v1/rutinas/`

```json
{
    "name": "Rutina 1",
    "description": "Descripcion de la rutina 1"
}
```

- Response: `200 OK`

```json
{
    "id": 1,
    "name": "Rutina 1",
    "description": "Descripcion de la rutina 1"
}
```

#### Si ya hay una rutina de ejercicios creada con el mismo nombre

- Request: `POST /api/v1/rutinas/`

```json
{
    "name": "Rutina 1",
    "description": "Descripcion de la rutina 1"
}
```

- Response: `400 Bad Request`

```json
{
    "error": "Ya existe una rutina de ejercicios con el nombre 'Rutina 1'"
}
```
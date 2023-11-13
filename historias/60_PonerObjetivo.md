# Historia de usuario 60: Poner objetivo de fitness

- Yo: como usuario de la aplicación,
- Quiero: poder poner crear uno o varios objetivos de fitness,
- Para: poder ver los objetivos de fitness que he puesto.

## Especificación de requerimientos

- El sistema debe permitir al usuario poner uno o varios objetivos de fitness.
- El sistema tendrá dos tipos de objetivos de fitness: lograr levantar un peso determinado, y lograr hacer una cantidad de repeticiones determinada.
- El usuario puede seleccionar en que ejercicio quiere poner un objetivo de fitness.
- El sistema debe permitir al usuario ver los objetivos de fitness que ha puesto.
- Los campos son obligatorios al momento de llenar el formulario de poner objetivo de fitness.

## Análisis

A continuación se presenta la pantalla de poner objetivo de fitness, cuyo funcionamiento es:

1. El usuario esta en la página de objetivos.
2. El usuario hace click en el botón de "Más".
3. El sistema muestra al usuario un formulario para poner un objetivo de fitness (tipo de objetivo, ejercicio, peso, repeticiones).
4. El usuario llena el formulario y hace click en el botón de "Guardar".
5. El sistema guarda el objetivo de fitness y muestra al usuario la lista de objetivos de fitness que ha puesto.

<img src="../assets/historia60.png" alt="Pantalla de poner objetivo de fitness" width="500"/>

## Critertios de aceptación

#### Prototipo de baja fidelidad

- Dado: que el usuario está en la página de objetivos.
- Cuando: el usuario hace click en el botón de "Más".
- Entonces: el sistema muestra al usuario un formulario para poner un objetivo de fitness (tipo de objetivo, ejercicio, peso, repeticiones).

## Diseño

### Integración con las APIs

#### Al momento de poner un objetivo de fitness

- Request: POST `/api/objetivos-fitness/`

```json
{
    "tipo": "levantar peso",
    "ejercicioid": "1",
    "peso": 100,
    "repeticiones": 0
}
```

- Response: 201

```json
{
    "id": 1,
    "tipo": "levantar peso",
    "ejercicioid": "1",
    "peso": 100,
    "repeticiones": 0
}
```

#### Al momento de ver los objetivos de fitness

- Request: GET `/api/objetivos-fitness/`

- Response: 200

```json
[
    {
        "id": 1,
        "tipo": "levantar peso",
        "ejercicioid": "1",
        "peso": 100,
        "repeticiones": 0
    }
]
```

- Response: 404

```json
{
    "message": "No se encontraron objetivos de fitness."
}
```
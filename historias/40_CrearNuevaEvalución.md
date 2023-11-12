# Historia de usuario 40: Crear nueva evaluación

- Yo: como usuario de la aplicación,
- Quiero: poder registrar una nueva evaluación de mi condición física actualizando mi peso y altura,
- Para: poder obtener sugerencias de ejercicios y alimentación más personalizadas.

## Especificación de requerimientos

- El sistema debe permitir al usuario registrar una nueva evaluación de su condición física actualizando su peso y altura.
- Los campos de peso y altura deben ser obligatorios.

## Análisis

A continuación se presenta la pantalla de crear nueva evaluación, cuyo funcionamiento es:

1. El usuario hace click en el botón de "Nueva evaluación".
2. El sistema muestra al usuario la opción de registrar una nueva evaluación de su condición física, donde se le pide peso y altura.

<img src="../assets/historia40.png" alt="Pantalla de crear nueva evaluación" heigth="500"/>

## Critertios de aceptación

#### Prototipo de baja fidelidad

- Dado: que el usuario ha está en la página de inicio.
- Cuando: el usuario hace click en el botón de "Nueva evaluación".
- Entonces: el sistema muestra al usuario la opción de registrar una nueva evaluación de su condición física, donde se le pide peso y altura.

#### Otras consideraciones

- El sistema pide los datos de peso, altura y fecha de nacimiento si es la primera vez que el usuario entra a la aplicación, posteriormente solo pide el peso y altura.
- El usuario puede actualizar su peso y altura en cualquier momento.

## Diseño

### Integración con las APIs

- Request: `POST /api/v1/evaluaciones/`

```json
{
    "peso": 70,
    "altura": 1.70
}
```

- Response: `200 OK`

```json
{
    "id": 1,
    "peso": 70,
    "altura": 1.70,
}
```

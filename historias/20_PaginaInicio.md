# Historia de usuario 20: Página de inicio

- Yo: como usuario de la aplicación,
- Quiero: poder ver la página de inicio de la aplicación,
- Para: poder obtener los ejercicios y sugerencias que el sistema me recomienda.

## Especificación de requerimientos

- El sistema debe mostrar al usuario en la página de inicio los ejercicios obtenidos de la API externa de WGER.
- El sistema debe mostrar al usuario en la página de inicio las sugerencias de ejercicios o alimentación obtenidas de la API externa de ChatGPT, en base a las preferencias y datos del usuario.
- El sistema debe mostrar al usuario en la página de inicio la opción de añadir un ejercicio a su rutina de ejercicios.
- El sistema debe mostrar al usuario en la página de inicio la opción de registrar una nueva evaluación de su condición física.

## Análisis

A continuación se presenta la pantalla de inicio, cuyo funcionamiento es:

1. El sistema muestra al usuario los ejercicios obtenidos de la API externa de WGER.
2. El sistema muestra al usuario las sugerencias de ejercicios o alimentación obtenidas de la API externa de ChatGPT, en base a las preferencias y datos del usuario.
3. El usuario puede añadir un ejercicio a su rutina de ejercicios.
4. El usuario puede registrar una nueva evaluación de su condición física, donde se le pide peso y altura.

<img src="../assets/historia20.png" alt="Pantalla de inicio" width="500"/>

## Critertios de aceptación

#### Prototipo de baja fidelidad

- Dado: que el usuario ha entrado a la aplicación.
- Cuando: el sistema carga la página de inicio.
- Entonces: el usuario puede ver los ejercicios y sugerencias que el sistema le recomienda.

#### Prototipo de baja fidelidad

- Dado: que el usuario ha entrado a la aplicación.
- Cuando: el usuario hace click en el botón de "Añadir ejercicio".
- Entonces: el sistema muestra al usuario la opción de añadir un ejercicio a su rutina de ejercicios.

#### Prototipo de baja fidelidad

- Dado: que el usuario ha entrado a la aplicación.
- Cuando: el usuario hace click en el botón de "Nueva evaluación".
- Entonces: el sistema muestra al usuario la opción de registrar una nueva evaluación de su condición física, donde se le pide peso y altura.

#### Prototipo de baja fidelidad

- Dado: que el usuario ha entrado a la aplicación.
- Cuando: el usuario hace click en el botón de "Añadir ejercicio".
- Entonces: el sistema muestra al usuario la opción de añadir un ejercicio a su rutina de ejercicios.

## Diseño

### Integración con las APIs

#### API de WGER para detalles de ejercicios

La API de WGER ofrece un endpoint para obtener los detalles de los ejercicios, incluyendo el nombre y la descripción. El endpoint `/api/v2/exercise/` proporciona un JSON con los siguientes atributos para cada ejercicio:

- `id`: Identificador único del ejercicio.
- `name`: Nombre del ejercicio.
- `description`: Descripción del ejercicio.
- Otros atributos relacionados con el ejercicio (categoría, equipo necesario, músculos trabajados, etc.).

#### API de WGER para imágenes de ejercicios

Además, la API de WGER proporciona un endpoint para las imágenes de los ejercicios. El endpoint `/api/v2/exerciseimage/` devuelve un JSON que incluye:

- `id`: Identificador único de la imagen.
- `exercise_base`: Identificador del ejercicio asociado a la imagen.
- `image`: URL de la imagen del ejercicio.

Esta información es crucial para presentar a los usuarios una interfaz visualmente atractiva y detallada de los ejercicios recomendados.

### Consideraciones de diseño

Al integrar estas APIs en la aplicación, se debe tener en cuenta:

- La correspondencia entre los `id` de los ejercicios y las `exercise_base` de las imágenes para garantizar que las imágenes mostradas coincidan con los ejercicios adecuados.
- La presentación de la información de manera clara y accesible, priorizando la experiencia del usuario al interactuar con la lista de ejercicios y sus detalles.

Con la integración exitosa de estas APIs, los usuarios tendrán acceso a una amplia gama de ejercicios con descripciones detalladas y representaciones visuales, mejorando su experiencia en la planificación y ejecución de sus rutinas de ejercicios.

```
{
  "results": [
    {
      "id": 345,
      "name": "Sentadillas",
      "description": "Ejercicio para fortalecer piernas y glúteos. Consiste en doblar las rodillas manteniendo la espalda recta.",
      "category": 9,
      "equipment": [8],
      "muscles": [10, 11],
      "muscles_secondary": [2],
      "images": [
        {
          "image_id": 789,
          "image": "https://wger.de/static/images/exercises/345/sentadillas.jpg"
        }
      ]
    },
    {
      "id": 678,
      "name": "Press de banca",
      "description": "Ejercicio para fortalecer el pecho, hombros y tríceps. Se realiza empujando una barra desde el pecho hacia arriba.",
      "category": 8,
      "equipment": [7],
      "muscles": [4, 5],
      "muscles_secondary": [3],
      "images": [
        {
          "image_id": 1012,
          "image": "https://wger.de/media/exercise-images/91/Crunches-1.png",
        }
      ]
    }
  ]
}
```

#### API de ChatGPT para sugerencias de ejercicios

La API de ChatGPT ofrece un endpoint para obtener sugerencias de ejercicios o alimentación en base a las preferencias del usuario. El endpoint `/api/v1/chatbot` proporciona un JSON con los siguientes atributos:

Por ejemplo, si el usuario tiene como objetivo la pérdida de peso, y sus métricas son 70 kg de peso y 175 cm de altura, la API de ChatGPT devuelve un JSON con las siguientes sugerencias:

```
{
  "user_id": 12345,
  "recommendations": {
    "fitness_goals": "Pérdida de peso",
    "user_metrics": {
      "weight": 70,
      "height": 175
    },
    "exercise_suggestions": [
      {
        "exercise_id": 101,
        "name": "Caminata rápida",
        "description": "Caminar a un ritmo rápido durante 30 minutos. Ideal para mejorar la salud cardiovascular y quemar calorías.",
        "duration": "30 minutos",
        "calories_burned": 150
      },
      {
        "exercise_id": 102,
        "name": "Ejercicios de fuerza básica",
        "description": "Rutina de 20 minutos de ejercicios de fuerza centrados en el core. Ayuda a mejorar la tonificación muscular.",
        "duration": "20 minutos",
        "calories_burned": 100
      }
    ],
    "nutrition_suggestions": [
      {
        "meal_type": "Desayuno",
        "description": "Avena con frutas y nueces. Una opción rica en fibras y proteínas para empezar el día.",
        "calories": 350
      },
      {
        "meal_type": "Almuerzo",
        "description": "Ensalada de pollo asado con verduras mixtas. Una comida equilibrada para energía sostenida.",
        "calories": 450
      }
    ]
  }
}
```
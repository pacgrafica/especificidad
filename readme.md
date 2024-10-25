# Especificidad en CSS

La especificidad en CSS es un concepto clave para entender cómo se aplican los estilos a los elementos HTML. Se refiere a la prioridad que tienen las reglas CSS cuando hay múltiples que podrían aplicarse a un mismo elemento. La especificidad se calcula en función de diferentes tipos de selectores.

## Niveles de Especificidad

La especificidad se mide con un sistema de puntuación que considera tres categorías:

1. **Selectores de tipo (elemento)**: Se refiere a las etiquetas HTML, como `div`, `p`, `h1`, etc. Tienen una puntuación de 1 punto.
  
2. **Selectores de clase, atributos y pseudo-clases**: Incluyen clases (como `.mi-clase`), atributos (como `[type="text"]`), y pseudo-clases (como `:hover`). Cada uno de estos tiene una puntuación de 10 puntos.
  
3. **Selectores de ID**: Son selectores únicos para un elemento, como `#mi-id`. Tienen una puntuación de 100 puntos.
  
4. **Selectores en línea**: Si aplicas estilos directamente en un elemento con el atributo `style`, tienen la mayor puntuación de 1000 puntos.
  
5. **Importante (`!important`)**: Se utiliza para forzar que una regla se aplique, independientemente de la especificidad. Sin embargo, su uso debe ser evitado en la medida de lo posible.

## Ejemplo de Especificidad

Si tienes estas reglas CSS:

```css
p {
  color: blue; /* 1 punto */
}

.mi-clase {
  color: red; /* 10 puntos */
}

#mi-id {
  color: green; /* 100 puntos */
}

p.mi-clase#mi-id {
  color: yellow; /* 111 puntos (1 + 10 + 100) */
}

Si un elemento <p class="mi-clase" id="mi-id"> se encuentra en tu HTML, el color final será amarillo, porque esa regla tiene la mayor especificidad.

Ejercicios
Aquí tienes 5 ejercicios para practicar la especificidad en HTML y CSS:

Ejercicio 1: Selectores de tipo
Crea un archivo HTML que tenga varios elementos <h1>, <h2> y <p>. Aplica un color diferente a cada tipo de elemento usando solo selectores de tipo.

Ejercicio 2: Selectores de clase
Crea varias clases en CSS y aplícalas a diferentes elementos en tu HTML. Cambia el color de fondo y el tamaño de la fuente utilizando solo selectores de clase.

Ejercicio 3: Selectores de ID
Agrega un ID a un elemento específico en tu HTML y aplica estilos solo a ese elemento usando un selector de ID. Asegúrate de que el estilo sea diferente al de los demás elementos.

Ejercicio 4: Combinación de selectores
Crea un elemento con un ID y una clase, y luego aplica estilos diferentes utilizando combinaciones de selectores. Observa cuál estilo se aplica y por qué.

Ejercicio 5: Uso de !important
Aplica un estilo a un elemento utilizando un selector de tipo, y luego intenta sobrescribirlo utilizando una clase con !important. Observa cómo afecta esto a la aplicación de estilos.

Plantilla básica de HTML
Puedes usar la siguiente plantilla básica para comenzar:

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ejercicios de Especificidad CSS</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>Título Principal</h1>
    <h2>Título Secundario</h2>
    <p>Este es un párrafo.</p>
    <p class="mi-clase">Este párrafo tiene una clase.</p>
    <div id="mi-id">Este div tiene un ID.</div>
    <p class="mi-clase" id="mi-id">Este párrafo tiene una clase y un ID.</p>
</body>
</html>

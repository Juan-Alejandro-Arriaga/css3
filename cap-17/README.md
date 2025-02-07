# Diseño de cuadrícula (Grid Layout)
Las cuadriculas han existido desde demasiado tiempo atrás y en CSS sus propiedades son bastante amplias.

## Terminología de Grid
En CSS se usan estas Terminologías en el "*Grid Layout Module*":

*   **Grid container**: El elemento que dimensiona la cuadricula y limita los elementos.
*   **Grid lines**: Lineas que dividen filas y columnas.
*   **Grid tracks**: Son los espacios entre las líneas (Filas y columnas).
*   **Grid cells**: Cada intersección entre una fila y una columna.
*   **Grid items**: Cada elemento colocado dentro de la cuadricula.

## Declarando y definiendo la Cuadricula 
Se define con la propiedad `display` con la palabra clave `grid`.

##### Sintaxis:
```css
    E {
        display : grid;
    }
```

### Creación de cuadrículas explícitas mediante el tamaño del tamaño de la pista

Las cuadriculas se establecen colocando valores para cada fila/columna , si se quieren crear columnas se usa la propiedad `grid-template-columns` y para crear filas se usa `grid-template-rows` , los valores que pueden llevar son:
*   **porcentajes**: 1%
*   **pixeles**: 1px
*   **Divirla en fracciones**: 1fr

##### Sintaxis: 
```css
    E {
        grid-template-columns:"valor" "valor" ...;
        grid-template-rows:"valor" "valor" ...;
    }
```

### Colocando artículos en una cuadrícula explícita
Para colocar elementos en un cuadro especifico se ocupan las propiedades `grid-column-start` y `grid-row-start` los cuales indican donde iniciaran.

Y para indicar las cuadriculas que se va a extender el elemento se ocupan las propiedades `grid-column-end` y `grid-row-end`

Se puede usar la palabra `span` para que el elemento que quede sobre la línea inicial de un elemento de la cuadricula.

##### Sintaxis:
```css
    E {
        grid-column-end:"value";
        grid-row-end:"value";
    }
```

>   Estos atributos se colocan al contenedor

### La abreviatura del posicionamiento de la cuadricula
Para acortar el código se puede usar su abreviación basada en la siguiente sintaxis:

```css
    E {
        grid-column: "column-start" / "column-end";
        grid-row: "row-start" / "row-end";
    }
```

O aún se puede acortar mucho mas con la propiedad `grid-area`:

```css
    E {
        grid-area:"row-start" / "column-start" / "row-end" / "column-end";
    }
```

### Repetir líneas de cuadrícula
Es común ver 12 columnas para grandes cuadriculas ya que con esta se tiene un mejor control , y para evitar tener que crear cada cuadricula con sus especificaciones , algo como esto: 

```css
    E {
        grid-template-columns: 1fr 10px 1fr 10px 1fr 10px 1fr 10px 1fr 10px 1fr
        10px 1fr 10px 1fr 10px 1fr 10px 1fr 10px 1fr 10px 1fr;
    }
```

Se puede usar la propiedad `repeat()` , esta función toma 2 argumentos:
1.  **Un entero**: Establece el numero de repeticiones
2.  **Una coma de separación**
3.   **La especificación de tamaño (opcional) y la fraccion en la que se va a dividir**

##### Ejemplo:
```css
    E {
         grid-template-columns:repeat(11, 10px 1fr);
    }
```
### Áreas de cuadrícula nombradas
Se les puede agregar nombres a cada bloque de la cuadricula con la propiedad `grid-template-areas` se puede realizar eso colocando equitativamente tanto los nombres , tanto como las divisiones de la cuadricula.

##### Sintaxis:
```css
    E {
       grid-template-areas:'nombres separados por espacios'; 
    }
```
Para representar las filas , solamente tienes que añadir una nueva fila a la propiedad anterior , y para colocar un elemento en algún espacio del contenedor , se usa la propiedad `grid-area` con el nombre del espacio.

##### Ejemplo:

```css
    E {
        grid-template-areas:
            'a b c'
            'a b c'; 
    }
    
    F {
        grid-area: b;
    }
```
### La abreviatura de grid-template
Se usa la siguiente sintaxis:

```css
    E {
         grid-template: "grid-template-columns" / "grid-template-rows";
    }
```

### Cuadrículas implícitas
Estas se definen en base a su contenido y en el caso de no existir la necesidad de tener columnas y filas en especifico se usan las propiedades `grid-auto-columns` y `grid-auto-rows` y los valores a especificar el ancho de la fila o columna

##### Sintaxis:
```css
    E {
        grid-auto-columns:"valor";
        grid-auto-rows:"valor";
    }
```
### Artículos de cuadrícula sin un lugar declarado
La propiedad `grid-auto-flow` hace que los elementos sin lugar establecido se inserte en algún espacio disponible.

##### Sintaxis
```css
    E {
        grid-auto-flow:"keyword";
    }
```
"*Keywords*":
*   **column**: Aquí se indica que se colocara en base a las columnas disponibles.
*   **row**: Aquí se indica que se colocara en base a las filas disponibles.

## Combinando cuadrículas explícitas e implícitas 
Estas 2 se pueden combinar para tener un mejor control de los elementos dentro del contenedor y las propiedades no requieren arreglo especifico para ser colocadas juntas.

### La abreviatura de grid
##### Sintaxis:
```css
    E {
         grid: 
            "grid-auto-flow" 
            "grid-auto-columns" 
            / 
            "grid-auto-rows";
    }
```

## Orden de apilamiento de artículos de cuadrícula
La propiedad `z-index` establece el orden de los elementos y entre mayor sea el valor de la propiedad , mas al frente se pondra.

##### Sintaxis:
```css
    E {
        z-index:"valor";
    }
```

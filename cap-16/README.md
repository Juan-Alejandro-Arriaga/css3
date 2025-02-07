# Valores y dimensionamiento

## Unidades de longitud relativa
Es aquella cuyo valor es relativamente basada en otra propiedad y CSS2 tiene 2 unidades de esas:
*   **em**: Se calcula a partir de la propiedad `font-size` de un elemento
*   **ex**:  Se calcula a partir de la altura `x` de la fuente de un elemento

### Unidades relativas a la raíz
Las nueva propiedad relativa de CSS3 nuevas es:
*   **rem**: Esta es relativa al tamaño de la fuente del documento.

##### Sintaxis de uso:
```css
    E {
        font-size: "valor"rem;
    }
```

Funciona multiplicando el tamaño de fuente del documento por el tamaño de la fuente raíz.

### Unidades relativas a la ventana gráfica
Se pueden valores porcentuales para adaptar el tamaño del texto a la pantalla y que tenga una mejor visualización.

Las dos nuevas unidades relativas a la ventana son: 
*   **vh** : Representa la altura de la ventana
*   **vw** : Representa lo ancho de la ventana

Cada unidad representa 1 por ciento de la ventana gráfica.

Y existen sus limitantes `vmax` que limita lo máximo y `vmin` que limita lo mínimo.

## Valores calculados
Los cálculos en CSS se hacen con la función `calc()` y toma cualquiera de las expresiones matemáticas. 
##### Ejemplo de uso:
    
Para calcular  el ancho de un elemento menos su borde:
```css
    E {
        border: 10px;
        width: calc(75% - 2em);
    }
```

En resumen esta función sirve con cualquier expresión matemática. 

## Elementos de dimensionamiento
### Dimensionamiento de la caja
La W3C dictaba que el valor del ancho era del ancho del cuadro del contenido y cualquier relleno y bordes eran adicionales

Se puede usar la propiedad `box-sizing` para definir como se calculan las dimensiones en un elemento.

##### Sintaxis:
```css
    E {
        box-sizing: "keyword";
    }
```
"*Keywords*":
*   **content-box**: Amplia el ancho o la altura , al cuadro del contenido.
*   **border-box**: Amplia el ancho o la altura incluye el relleno y los cuadros del borde

### Dimensionamiento intrínseco y extrínseco
El tamaño intrínseco se basa en elementos secundarios de un elemento y el extrínseco en el tamaño del elemento primario.

Estos se aplican mediante las propiedades `width` o `height`

##### Sintaxis
```css
    E {
        width: "keyword";
        height:"keyword";
    }
```
#### max-content y min-content
Estos son dos "*keywords*" posibles hace que algún elemento sea tan ancho o alto como el contenido mas grande o como el contenido mas pequeño

Es decir `max-content` hace que los elementos se ajusten al tamaño el elemento hermano mas grande y `min-content` hace que se ajuste al elemento mas pequeño.

#### fit-content
Esta ajusta el elemento a la cantidad justa para poder mostrar el contenido sin que exista un desbordamiento.

#### fill
Este hace que un elemento llene todo el espacio de su elemento padre sin desbordamientos.
# Múltiples columnas
Tener múltiples columnas de texto facilita la lectura y hace menos difícil el leer múltiples lineas de texto.

## Métodos de diseño de columnas
Se pueden dividir el contenido usando dos métodos , ya sea de forma:
*   **prescriptiva**:Estableciendo un numero de columnas
*   **forma dinámica**:Permitiendo al navegador calcular el ancho del elemento 

### Columnas prescriptivas: column-count
La forma mas sencilla de dividir el contenido equitativamente es con la propiedad `column-count`.
##### Sintaxis
```css
    E {
        column-count: 'columns';
    }
```
El elemento "*E*" debe ser un elemento padre ,el cual se dividirá sus elementos hijos en columnas

### Columnas dinámicas: column-width
Con la propiedad `column-width` se indica el ancho de cada columna haciendo que se creen dentro del cuerpo del padre las que quepan a lo ancho

##### Sintaxis

```css
    E {
        column-width: 'lenght';
    }
```

### Distribución variable del contenido en las distintas columnas
El contenido se distribuirá en columnas de manera igual , y en el caso que el mismo navegador no pueda organizarlas , la ultima columna se acortara.

La propiedad `column-fill` tiene 2 valores posibles:
*   **balance**: El cual intenta hacer todas las columnas del mismo tamaño.
*   **auto**: El cual llena las columnas secuencialmente.

>   El valor auto aplica solo cuando el elemento padre tiene una propiedad fija  

##### Sintaxis:
```css
    E {
        column-fill: 'keyword' ;
    }
```

### Combinando column-count y column-width
Ambas propiedades se pueden establecer en un mismo elemento  haciendo que `column-count` actué como máximo.
##### Ejemplo:
```css
    .columns {
        column-count: 3;
        column-width: 150px;
    }
```
Ademas se pueden usar dentro de la propiedad `columns`.
```css
    E {
        /*columns: "column-width" "column-count";*/
        columns: 150px 3;
    }
```
## Reglas y espacios entre columnas
El navegador coloca un espacio predeterminado de "*1em*" entre cada columna, aunque es posible modificarlo.

>   1em :Es un valor aproximado a 16px 

Para eso existen 2 propiedades `column-gap` y `column-rule`.

##### column-gap:
Esta establece espacio entre sus columnas.
```css
    E { 
        column-gap: 'length' ; 
    }
```
#### column-rule
Es una abreviatura de tres subpropiedades:
*   **column-rule-width**
*   **column-rule-style**
*   **column-rule-color**

##### Sintaxis
```css
    E {
        column-rule-width: "longidut";
        column-rule-style: "estilo-borde";
        column-rule-color: "color";
        column-rule: "longitud" "estilo-borde" "color";
    }
```
## Elementos que abarcan varias columnas
Si se desea que algún elemento ocupe varias columnas se usa la propiedad `column-span`.
##### Sintaxis
```css
    E {
        column-span: value;
    }
```
El "*value*" puede ser una de dos:
*   **all**:Proporciona una interrupción en el flujo de las columnas
*   **none**:Mantiene el flujo de columnas.
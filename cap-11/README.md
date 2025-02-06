# Degradados

Esto son las transiciones entre colores de manera gradual implementadas en 2008 en "*webkit*"

## Degradados lineares
Este es un tipo de degradado que cambia de color a lo largo de 2 puntos siguiendo una linea recta.

##### Sintaxis
```css
    E {
        Attr: linear-gradient("color-1","color-2");
    }
```
### Configuración de la dirección del gradiente
Se puede establecer la dirección del degradado mediante unas "*keywords*" por ejemplo:

*   **top**
*   **bottom**
*   **left**
*   **right**

>   Todas las keywords deben iniciar con "to" y lo demás como: "to top"

##### Sintaxis
```css
    E {
        background-image: linear-gradient(to top, rgb(0,0,0), rgb(255,255,255));
    }
```
Se pueden usar dos "*keywords*" juntas para crear algunos efectos direccionales.

##### Ejemplo
```css
    E {
        background-image: linear-gradient(to left top, rgb(0,0,0), rgb(255,255,255));
    }
```

También se puede colocar con mas precisión la dirección de los degradados usando grados (*deg*) los cuales van de 0 a 360.

##### Ejemplo de uso:
```css
    E {
        background-image: linear-gradient(120deg, rgb(0,0,0), rgb(255,255,255));
    }
```

### Adición de valores de parada de color adicionales
Las paradas de color te permiten colocar reglas establecidas a los colores como que algún color ocupe cierto porcentaje del tamaño del degradado colocando el valor ya sea en pixel o en porcentaje después del color.
##### Ejemplo
```css
    E {
        background: linear-gradient(rgb(0,0,0) , rgb(255,255,255) 50%,rgb(0,0,0);
    }
```

### Repetición de gradientes lineales
Se puede usar la propiedad `repeating-linear-gradient()` para repetir el degradado aceptando los mismos valores de `linear-gradient()` añadiendo que requiere un valor de longitud o porcentaje colocado en el color final.
##### Ejemplo
```css
    E {
        background-image: repeating-linear-gradient(rgb(0,0,0), rgb(255,255,255) 25%);
    }
```
El valor final establece el final del degradado.

## Degradados radiales
Funciona de la misma manera que `linear-gradient` solamente que este se extiende en todas las direcciones como una elipse.

##### Sintaxis
```css
    E {
        background: radial-gradient(rgb(0,0,0), rgb(255,255,255));
    }
```
### Usando degradados radiales
Por medio de una "*keyword*" se puede dar la forma a un degradado radial.

##### Ejemplo
```css
    E {
         background: 
            radial-gradient(
                circle
                ,
                rgb(0,0,0)
                ,
                rgb(255,255,255)
            );
    }
```
>   De forma predeterminada viene la keyword ellipse

Los degradados inician desde el centro del elemento, aún así se puede cambiar agregando un argumento , y funciona igual que con `background-position`.

##### Ejemplo
```css
    E {
        background: 
            radial-gradient(
                circle /*Indicador de forma*/
                at  
                100% /*Indica que parte desde el centro*/ 
                50% /*Indica que va hacia la derecha*/
                , 
                rgb(0,0,0) /*Colores*/
                , 
                rgb(255,255,255) /*Colores*/
            );
    }
```

Se puede establecer la distancia que tendrá el degradado por ejemplo:
```css
    E {
        background: 
            radial-gradient(
                circle 
                50px /*Distancia del degradado*/
                , 
                rgb(0,0,0)
                , 
                rgb(255,255,255) 
            );
    }
```

Se pueden añadir una de 4 posibles "*keywords*":
*   **closest-corner**: El gradiente llega hasta la esquina más cercana del contenedor.
*   **closest-side**: El gradiente se extiende hasta el lado más cercano del contenedor.
*   **farthest-corner**(Predeterminado): El gradiente se extiende hasta la esquina más lejana del contenedor.
*   **farthest-side**: El gradiente se extiende hasta el lado más lejano del contenedor.

### Uso de múltiples valores de parada de color
Es similar a los degradados lineales aceptando los mismos valores de la siguiente manera:
```css
    E {
         background-image: 
            radial-gradient(
                farthest-side 
                circle
                , 
                rgb(0,0,0)
                ,
                rgb(255,255,255)
                ,
                rgb(0,0,0)
            );
    }
```
Y de igual manera se pueden colocar valores indicando el rango de distancia que tendrá cada color.

### Gradientes radiales repetitivos
Con la propiedad `repeating-linear-gradient()` y funciona de la misma manera que lo hace con `linear-gradient()`.
##### Sintaxis:
```css
    E {
        background-image: 
            repeating-radial-gradient(
                circle
                ,
                rgb(0,0,0)
                ,
                rgb(255,255,255)
                20%  /*Indicador del final*/
            ); 
    }
```

## Degradados múltiples
En CSS3 se pueden aplicar múltiples degradados a un contenedor estableciendo cada degradado.

##### Ejemplo:
```css
    E {
        background-image:
            linear-gradient(
                to right bottom,
                black,
                white 50%,
                transparent 50%
            ),
            linear-gradient(
                to left bottom, 
                black, 
                white 50%,
                black 50%
            );
    }
```
Cabe decir que es necesario usar `background-blend-mode:` con la "*keyword*" `overlay`
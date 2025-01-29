# Efectos del texto y estilos tipográficos 
El texto es el objeto central de los sitios web y en CCS3 amplia de gran manera las herramientas que se pueden utilizar para darle un mejor estilo de textos , por ejemplo agregar sombras al texto.

## Comprensión de ejes y coordenadas
CSS usa un sistema de coordenadas cartesianas, que consta de dos líneas , una horizontal y una vertical se les conoce por ejes "*x*" y "*y*" , ademas se miden en pixeles.
*   **x**: Linea horizontal.
*   **y**: Linea vertical.

>La mayoría de elementos se miden en pixeles

## Aplicación de efectos dimensionales: sombra de texto
Gracias a la propiedad `text-shadow` se permite agregar sombras paralelas al texto , usando las coordenadas "*x*" y "*y*".

Ademas se puede colocar el color en especifico a la sombra , generalmente viene predefinido el color negro.
##### Sintaxis:
```css
    E {
        text-shadow: x y color;
    }
```
Se pueden colocar algunos atributos extras tales como el efecto `blur` justo después de los atributos de ejes.
```css
    E {
        text-shadow: x y blur-radius:color ;
    }
```
### Múltiples sombras
La misma sintaxis de sombras permite agregar varias sombras a un mismo nodo , solamente añadiendo una propiedad extra separando por comas:
```css
    E {
        text-shadow: value ,value ,value;
    }
```

## Restringir el desbordamiento
Ahora en CSS3 existe la propiedad `text-overflow` con la que podemos manejar de mejor manera el texto en lugares donde es espacio es limitado.

##### Sintaxis:
```css
    E {
        text-overflow: "keyword";
    }
```
Los valores que se pueden colocar como "*keyword*" pueden ser:
*   **clip**:El texto se corta en el punto donde el elemento se sobrellena el contenedor.
*   **ellipsis**:Reemplaza el ultimo carácter completo o parcial antes del desbordamiento.

##### Ejemplo:
```css
    p {
        overflow:hidden;
        text-overflow:ellipsis;
        white-space:nowrap;
    }
```
Se puede colocar de igual manera para controlar el desbordamiento al inicio y al final , tan solo colocando la instrucción nuevamente.
```css
    E {
        text-overflow: ellipsis ellipsis;/*El primero es para el incio y el segundo es para el final*/
    }
```
Ademas se pueden colocar caracteres para que sustituyan al texto desbordado, solo colocando el carácter en comillas.

>Usando comillas simples  -> ' ' <- 
>

## Texto alineado
La propiedad `text-aling` con sus propieded `start` y `end` , son equivalentes a los valores `left` y `right` ,su uso mas destacable es que se puede usar el texto de izquierda a derecha.

La propiedad `text-aling-last` permite establecer la alineación de la última linea de texto.
##### Sintaxis:
```css
    E {
        text-align-last: 'keyword';
    }
```
## Control del ajuste de línea
Un problema que se presenta al trabajar contexto dinámico es la aparición en lugares inadecuados, para eso se implementaron nuevas propiedades para resolver esos problemas.

### Rompiendo palabras
La propiedad `word-wrap` indica al navegador si se puede dividir la palabra y reorganizarla para que quepan dentro del elemento padre.
##### Sintaxis
```css
    E {
        word-wrap: 'keyword';
    }
```
Valores:
*   **normal**:Hace que las lineas se dividan solo entre palabras.
*   **break-word**: Hace posible que se puedan partir las palabras.

### Palabras con guiones
Se puede usar la separación de palabras y para eso existe la propiedad `hyphens`.
##### Sintaxis:
```css
    E {
        hyphens:'keyword';
    }
```
Tiene 3 posibles "*keywords*":
*   **manual**:Separa las palabras según sugerencia de separación
*   **auto**:Separa las palabras automáticamente
*   **none**: Nunca las separa

## Cambiar el tamaño de los elementos
La propiedad `resize` te permite controlar las dimensiones de algún elemento añadiendo un controlador para arrastrar el elemento a un tamaño diferente.
##### Sintaxis:
```css
    E {
        resize :'keyword';
    }
```
Las palabras clave indican hacia donde se puede redimensionar:
*   **horizontal**
*   **vertical**
*   **both**
*   **none**

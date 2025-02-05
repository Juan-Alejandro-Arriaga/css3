# Efectos de borde y cuadro
## Dando esquinas redondeadas a los bordes
Con CSS ahora se pueden crear esquinas redondeadas gracias a el módulo de fondos.

Para colocarlo se usa la propiedad `border-radius` usando la siguiente sintaxis:

```css
    E {
        border-radius: 'x' 'y';
    }
```
*   **x**: Significa los lados izquierdo y derecho
*   **y**:Significa los lados de arriba y abajo

De igual manera se pueden colocar especificados los lados que se modificaran con ayuda de las siguientes propiedades:

`border-top-left-radius`:Modifica esquina superior izquierda

`border-top-right-radius`:Modifica esquina superior derecha

`border-bottom-right-radius`:Modifica esquina inferior derecha

`border-bottom-left-radius`:Modifica esquina inferior izquierda 

### La abreviatura de border-radius
Se puede especificar las 4 propiedades dentro de una sola `border-radius` con la siguiente sintaxis: 
```css
    E { 
        border-radius: [top-left] [top-right] [bottom-right] [bottom-left]; 
    }
```
### Usando valores de porcentaje
Se pueden usar valores de porcentaje , esto sirve para crear un circulo perfecto con CSS.

##### Ejemplo:
```css
    E {
        border-radius:50%;
    }
```
## Uso de imágenes para los bordes
### border-image-source
De igual manera se pueden colocar imágenes en los bordes gracias a CSS3.
##### Sintaxis:

```css
    E {
        border-image-source: url('ruta del archivo');
    }
```
>   Esta propiedad acepta el uso de degradados

### border-image-slice
Esta propiedad acepta entre 1-4 valores ,cada uno asigna un lado a un elemento , para establecer una distancia a cada borde de la imagen.

##### Ejemplo
```css
    E {
         border-image-slice:'value';
    }
```
El valor puede ser porcentaje o pixel.

Esta propiedad tiene el valor `fill` con el cual se aplicara un relleno al elemento sobreponiéndose al fondo establecido.

### border-image-width
Para ajustar el ancho y la altura del borde se usa la propiedad `border-image-width` 
  
##### Sintaxis:
```css
    E {
        border-image-width: 'value';
    }
```
Puede poseer hasta 4 valores y pueden ser  longitud o porcentaje, y este solo tiene impacto en el diseño del mismo borde, no en lo que se encuentre dentro de la caja.

### border-image-outset
Esta propiedad nos permite que se pueda mostrar la imagen fuera del cuadro del borde , como si fuera un `padding` incrementando su tamaño del contenedor.

###### Sintaxis:
```css
    E {
        border-image-outset:valor("top and bottom") valor("right and left");
    }
```
### border-image-repeat
Esta propiedad controla su ajuste de longitud de la imagen en cada lado.

##### Sintaxis
```css
    E {
        border-image-repeat:'keyword';
    }
```
Tiene 3 valores para la "*keyword*":

*   **stretch**:Con esta se estira para llenar la longitud del borde.
*   **repeat**:Con esta se repite la imagen con su proporción original para cubrir todo el borde y en caso de sobrellenarse este cortara la ultima imagen.
*   **round**: Escala la imagen para ajustarse al borde

Y se pueden usar 2 "*keywords*" con el fin que la primera modificaría el eje horizontal y la segunda el eje vertical.

### La propiedad abreviada border-image
Se puede abreviar la usando solo `border-image`
##### Sintaxis:
```css
    E {
        border-image: source slice / width /outset repeat;
    }
```
##### Ejemplo:
```css
    E {
        border-image: 
            url('foo.png')  /*src*/
            25 10 fill      /*slice*/
            /
            25px 10px       /*width and height*/
            / 
            5px             /*outset*/
            round;          /*repeat*/
    }
```
## Sombras proyectadas
Las sombras se pueden agregar de igual manera con `box-shadow`, es similar a `text-shadow`.
##### Sintaxis
```css
    E { 
        box-shadow: "inset" "horizontal" "vertical" "blur-radius" "spread" "color"; 
    }
```
*   **inset**:Valor opcional para establecer si la sombra esta fuera o dentro del elemento.
*   **horizontal y vertical**:Valores obligatorios que establecen la distancia horizontal y vertical de la sombra.
*   **blur-radius**:Valor opcional que indica el nivel de desenfoque de la sombra
*   **spread**:Valor opcional que establece la distancia con la que se extiende la sombra.
*   **color**:Valor opcional que pone el color del que sera la sombra.

## Sombras interiores
`inset` da el efecto de voltear la sombra , es decir esta aparecerá en la parte superior izquierda.

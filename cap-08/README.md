# Imágenes de fondo
En CSS3 se añadieron nuevas propiedades con la finalidad de hacer decoraciones mucho mas simples.

Ademas nos permite cambiar el tamaño de las imágenes sobre la marcha

## Actualizaciones de propiedades de fondo existentes

### backgound-position
En CSS3 esta propiedad acepta 4 valores.
##### Ejemplo:
```css
    E { 
        background-position: right 10em bottom 50%; 
    }
```
Se puede especificar un lado , y valores de longitud.

### background-attachment
La forma en que el fondo se desplaza a lo largo de la ventana se determina por medio de la propiedad `background-atachment`, 
Esta propiedad tiene como predeterminado el valor `scroll` que significa que la imagen no se desplaza con el elemento , y `fixed` la cual es lo contrario a `scroll`.

```css
    E { 
        background-attachment:fixed;
    }
```
### background-repeat
Esta propiedad acepta uno de una serie valores posibles,y no se permiten mas de uno:
*   **no-repeat**:No deja que se repita el fondo.
*   **repeat**:Hace que se repita el fondo.
*   **repeat-x**:Hace que se repita el fondo en dirección horizontal.
*   **repeat-y**:Hace que se repita el fondo en dirección vertical.
*   **space**:Hace que la imagen del fondo de repita tantas veces como sea posible sin recortar.
*   **round**:Hace que la imagen se escale para llenar el fondo.

##### Sintaxis:
```css
    E {
        background-repeat:'keyword';
    }
```
## Varias imágenes de fondo
En CSS3 las propiedades `background-*` aceptan varios valores, así que se pueden colocar muchas imágenes a un fondo.

##### Sintaxis para cargar imágenes en css:
```css
    E {
        background-image:'valor' , 'valor';
    }
```
Y a estas mismas se le pueden agregar algunos valores para especificar posiciones , tamaño , repetición , fondo.

##### Ejemplo:
```css
    E {
        background-image: 
            url('landscape.jpg') no-repeat 50% 50% #000;
    }
```

## Imágenes de fondo escaladas dinámicamente
La propiedad `background-size` permite establecer el tamaño de las imágenes del fondo y se le pueden colocar los dos valores de `width` y `height` o solo 1 .
##### Sintaxis:
```css
    E { 
        background-size: 'width' 'height';
    }
```
>   Para colocarlas en conjunto de diferentes imágenes cargadas , se deben colocar en el mismo orden de las imágenes cuando fueron cargadas

Ademas hay 2 "*keywords*" :
*   **contain**:Hace que se escale lo mas posible , sin exceder el ancho ni alto del contenedor.
*   **cover**:Hace que la imagen se escale al tamaño de la altura o el ancho del elemento contenedor.

## Clip de fondo y origen
### background-clip
 Establece el limite donde se muestra la imagen dependiendo la caja donde se encuentre contenida la imagen.

##### Sintaxs:
```css
    E { 
        background-clip: box;        
    }
```
El valor de "*box*" puede ser una de 3 "*keywords*":
*   **border-box**:Muestra el fondo detrás del borde(*Es el predeterminado*).
*   **content-box**:El fondo se detiene en el relleno del elemento.
*   **padding-box**:Muestra el fondo solo hasta el borde.


### background-origin
Con esta puedes establecer desde donde se calcula el fondo.
##### Sintaxis:
```css
    E { 
        background-origin: box; 
    }
```
Las "*keywords*" son las mismas que acepta `background-clip`, y la imagen se va a colocar dependiendo de donde se desplieque su origen.

> El origen se puede indicar en el atributo background.

> Si la posición se establece "fixed" esta propiedad no tendra efecto y usa la misma sintaxis que se usa en el apartado "Varias imágenes de fondo"

## Acceso directo de fondo actualizado

La propiedad `background` puedes colocar los valores para usar menos lineas de código  , y se colocan en el siguiente orden:
```css
    E { 
        background: 
            url('bar.png') /*Ubicacion del archivo*/
            no-repeat /*Del background-repeat*/
            50% 
            50%  /*background-position*/
            /   /*Barra escencial para separar los 2 valores*/
            50% /*background-size*/
            auto; /*background-origin*/ 
    }
``` 

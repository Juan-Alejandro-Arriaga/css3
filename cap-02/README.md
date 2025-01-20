# Consultas de medios
CSS permite que los estilos se puedan repetir en distintas paginas web mediante al elemento `<link>`:
```html
    <link 
        href="style.css" 
        rel="stylesheet" 
        media="screen"
    >
```
Dentro de CSS3 se pueden usar consultas de medio definidas, lo cual permite ofrecer estilos mucho mas específicos al dispositivo del usuario.

El modulo ya se encuentra bien implementado en IE a partir de la versión 9 

## Las ventajas de las consultas de medios

Los sitios web se pueden optimizar para navegadores.

Los elementos de navegación pueden involucrar funcionalidades especiales para los móviles.

En ocasiones el mantenimiento implica la duplicación de código para mantener sincronizadas las versiones.

Las modificaciones hacen que sea posible adaptar las imágenes y texto al tamaño del dispositivo haciendo que su visualización sea mas clara.

## Sintaxis
En la consulta de medios se establece un parámetro, existen 3 maneras de hacer una consulta de medios.
*   La primera es llamar a una hoja de estilo externa mediante un elemento `<link>`.
```html
    <link 
        href="file" 
        rel="stylesheet" 
        media="logic media and (expression)"
    >
```
*   La segunda manera es llamando a una hoja de estilo externa usando la directiva `@import`:
```css
   @import url('file') logic media and (expression);
```
*   La tercera es utilizar consultas de medios con la regla @media extendida:
```css
    @media logic media and (expression) {
        rules
    }
```
El atributo *media* declarara los tipos de medios a los cuales se aplican los estilos , al igual que en la etiqueta de enlace `<link>`.
```html
    <link
       href="styles.css"
       rel="stylesheet"
       media="screen"
    >
```
Se pueden colocar comas para crear una lista y elegir varios tipos de medio.

No es necesario especificarlas dentro del constructor de consultas de medios, ejemplo:
```css
    @media all and (expression) {
        rules 
    }
    @media (expression) { 
        rules
    }
```
Un nuevo atributo para la regla de "**@media**" son palabras opcionales con el valor opcional de "*only*" o "*not*" 
##### Ejemplo de uso:
```css
    @media only media and (expression) { 
        rules 
    }
    @media not media and (expression) { 
        rules 
    }
```
##### Requisitos
*   **only**:Sirve principalmente para ocultar las reglas a los navegadores mas antiguos.
*   **not**:Se usa para negar la consulta en el caso de que no se cumplan con los parámetros establecidos.

Se tiene que usar el operador "**and**" para combinarlos con el atributo de expresión, ademas se usa para establecer funciones mas allá del tipo de medio.

## Características de los medios

Estas son la información del dispositivo que se esta usando para mostrar la pagina web , son cosas como:
*   Sus dimensiones.
*   Resolución.

Son usadas para determinar las reglas a donde se aplicaran los estilos y la mayoría requiere un valor.
```css
    @media (feature: value) { 
        rules 
    }
```
Con algunas características se pueden colocar sin algún valor.

Las siguientes son funciones de multimedia mas destacadas que se usan mas a menudo:
### Width and Height 
La función *width* describe en ancho del dispositivo donde se visualiza la página y requiere un valor de longitud.
```css
    @media (width: 600px) {
        rules
    }
```
### Pixel Ratio 
Existe una relación de pixeles físicos a pixeles CSS conocida como (DPR), funciona de manera que por ejemplo:
    
        1 pixel CSS es igual a 4 pixeles físicos,
        2 horizontales y 2 verticales.

Se puede implementar una función *resolution* con la cual permite orientar dispositivos según su tamaño.
```css
    @media media and (resolution: value) {
        rules
    }
``` 
El valor que lleva es un numero con unidad de resolución:
>*   (DPI):Dots Per Inch [Puntos Por Pulgada]
>*   (DPCM):Dots Per Centimeter [Puntos Por Centimetro]
>*   (DPPX):Dots Per Pixel [Puntos Por Pixel]

De igual manera se puede detectar el máximo y el mínimo.
```css
    @media (max-resolution:number){
        rules
    }
    @media (min-resolution:number){
        rules
    }
``` 
### Device Width and height
Las dimensiones de alto y ancho  deben coincidir con las dimensiones de la ventana gráfica del navegador y para eso se usa la etiqueta:
```html
    <meta 
        name="viewport" 
        content="width=device-width"
    >
```
Dependiendo el navegador usando como ejemplo los navegadores móviles entraran en "modo móvil" ajustándose a las dimensiones del dispositivo.

### Orientation
Si se quiere optimizar en su visualización horizontal se usa la función `orientation` y su sintaxis es:
```css
    @media (orientation: value) { 
        rules 
    }
```
El valor puede 1 de dos opciones `landscape` o `portrait`

### Aspectos de proporción
También puede crear consultas que se apliquen cuando se cumpla una determinada relación de ancho a alto, se usa `aspect-ratio` para probar la relación de aspecto del dispositivo usando la siguiente sintaxis:
```css
    @media (aspect-ratio: horizontal/vertical) { 
        rules
    }
    @media (device-aspect-ratio: horizontal/vertical) { 
        rules 
    }
```
Los valores horizontales y verticales son números enteros positivos que representan
la relación entre el ancho y la altura.

De igual manera se pueden colocar los prefijos `min-` y `max-` y usar proporciones como por ejemplo 16/9 que seria una toma panorámica.
```css
    @media (min-device-aspect-ratio: 16/9) {
        ...
    }
```
## Multiple media features
Se pueden usar múltiples características usando operadores como `and` y `or` con la posibilidad de crear muchas combinaciones de sintaxis.

## Desarrollo web que prioriza los dispositivos móviles
El método actual recomendado para el desarrollo actual es iniciar en pantallas de menor tamaño y cada vez agrandar la pantalla y trabajar con recursos mas grandes.

Lo ideal es crear una hoja de estilos para todos los dispositivos e ir añadiendo nuevos elementos progresivamente.

## Consultas de medios: compatibilidad con navegadores
<table>
    <thead>
        <tr>
            <th>
                
            </th>
            <th>
                Chrome 
            </th>
            <th>
                Firefox
            </th>
            <th>
                Safari
            </th>
            <th>
                IE
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                Media Queries
            </td>
            <td>
                Yes
            </td>
            <td>
                Yes
            </td>
            <td>
                Yes
            </td>   
            <td>
                Yes
            </td>
        </tr>
    </tbody>
</table>

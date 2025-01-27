# Pseudoclase y PseudoElementos
Las "*Pseudoclases*" diferencian entre los diferentes estados o tipos de un elemento.

Un "*Pseudoelemento*" brindan acceso a la subparte de un elemento

CSS3 permite lograr una diversidad de resultados visuales sin tener la necesidad de colocar muchas clases y mejora la optimización al momento de agregar nuevos elementos .

## Pseudoclases estructurales
Proporciona una manera de especificar un elemento que no esta especificado en el árbol de documentos, existen una gran variedad de `subtypes` , el mas común es el estructural.

##### Usando como ejemplo:
```html
    <div>
        <p>
            Hello   <!--Primer elemento hijo-->
        </p>
        <p>
            World   <!--Segundo elemento hijo-->
        </p>
    </div>
```
En CSS2 para aplicarle un estilo al primer elemento hijo se introdujo la regla: `:first-child` y su sintaxis de uso es:
```css
    E:first-child {
        ...
    }
```

Ahora en CSS3 se amplia de gran manera el rango de alcance.

## El :nth-* pseudoclase
Hay 4 "*pseudoclases*" que usan un contador para encontrar la posición de algún elemento y se usa la sintaxis `:nth-*`, su contador inicia en 0 y existe una gran variedad de formas de uso:
*   *Se puede aumentar mediante sumatoria*
*   *Se puede indicar que exclusivamente a los múltiplos de cierto numero*
##### Ejemplo de uso:
```css
    E:nth-*(n+1) {  /*Este se incrementara de 1 en 1*/
        ...
    }
    E:nth-*(2n) {   /*Este lo colocara a todos multiplos de 2*/
        ...
    }
    E:nth-*(3n-1) {   /*Este lo colocara a todos los multiplos de 3 menos 1*/
        ...
    }
```
Existen 2 valores de palabras clave especiales las cuales son `even` y `odd` , que pueden reemplazar `2n` y `2n+1`

### :nth-child() and :nth-of-type()
Estas dos *pseudoclases* tienen caracteristicas similares , aun así lo que lo diferencia es que: 
*   `:nth-child()`:Selecciona algún elemento basándose en el elemento padre.
*   `:nth-of-type()`:Se basa en el tipo de elemento especificado.

##### Ejemplo explicado:
```css
    E:nth-child(n) {    /*1*/
        ...
    }
    E:nth-of-type(n) {  /*2*/
        ...
    }
    E:nth-child(2n) {   /*3*/
        ...
    }
    E:nth-of-type(2n) { /*4*/
        ...
    }
```
El ejemplo 1 y 2 ambas son iguales, cambia en los ejemplos 3 y 4 , en el ejemplo 3 toma a todos los elementos que estén en un lugar múltiplo de 2 basándose en el elemento padre , y el ejemplo 4 solo cuenta elementos del mismo tipo, ejemplo:  
```html
    <div>
        <span>  <!--Este elemento <span> es el que se cuenta como primero-->
            E 1
        </span>
        <p>
            E 2
        </p>
        <span>  <!--Por lo tanto en base a la instruccion se le aplicaran las reglas a este-->
            E 3
        </span>
        <p>
            E 4
        </p>
    </div>
```
### :nth-last-child() and :nth-last-of-type()
Estos son relativamente lo mismo que los elemento `:nth-last-child()` y `:nth-last-of-type()` solamente que estos se cuentan a partir del ultimo elemento que se tenga.
##### sintaxis
```css
    E:nth-last-child(n){
        ...
    }
    E:nth-last-of-type(n){
        ...
    }
```
### :first-of-type, :last-child, and :last-of-type

`:first-of-type` es mas especifico y se aplica exclusivamente al primer elemento hijo.

`:last-child` y `:last-of-type` seleccionan el último elemento hijo

##### Sintaxis
```css
    E:first-of-type { /*Solo se cambia la pseudoclase*/
        ...
    }
```
### : only-child and : only-of-type
Estos se utilizan para seleccionar elementos específicos del árbol de documentos con un elemento padre y sin elementos hermanos.

Especificamente `:only-of-type` permite elegir un elemento entre otros y `:only-child` requiere que el elemento este solo.
```html
    <h1>
        Título
    </h1>
    <p>     <!-- A este se le aplica exclusivamente :only-of-type -->
        Lorem Impsum
    </p>
    <blockquote>
        <p> <!-- En este se aplica los dos pseudo-clases -->
            Lorem Impsum 
        </p>
    </blockquote>
```
## Otras pseudoclases
Existen *pseudoclases* que permiten seleccionar elementos con base a otros criterios como:
*   **Destinos de enlaces**
*   **Elementos de interfaz**

### :target
Dentro de la páginas puede haber enlaces los cuales redireccionan a una parte dentro de la misma página,ejemplo:
```html
    <h4 id="h4_1">
        Lorem Ipsum
    </h4>
    <a href="page.html#h4_1">
        Lorem
    </a>
```
Esta *pseudoclase* le permite aplicar estilos al elemento cuando se ha seguido la URI.
##### Sintaxis:
```css
    E:target{
        ...
    }
```
### :empty
Esta selecciona algún elemento que no tenga elementos secundarios, como:
```html
    <table>
        <tr>
            <td>
                <!--Este elemento no tiene elementos secundarios-->
            </td>
            <td>
                Lorem
            </td>
        </tr>
    </table>
```
### :root
Esta selecciona el primer elemento de un árbol de documentos, sirve para establecer un elemento `html` que no debería modificarse.
##### Sintaxis
```css
    E:root{
        ...
    }
```
### :not
Esta selecciona todos los elementos excepto aquellos que se indican e inclusive puedes colocar otras *pseudoclases* dentro de su instrucción.
##### Sintaxis:
```css
    E:not(F){
        ...
    }
    E:not(:first-child){/*Ejemplo de colocación de otra pseudoclase*/
        ...
    }
```
### Estados de elementos de la interfaz de usuario
A los elementos de `html` se le pueden colocar atributos de estado que indican características en especifico como:
*   **:checked**: Para indicar que el elemento esta seleccionado.
*   **:disabled**: Para que los elementos estén marcados como desactivados.

### Pseudoclases de validación de restricciones
Esas son atributos que se pueden utilizar para hacer una validación de ciertos requisitos en el contenido de un formulario, son:
*   **:required**:Indica que es requerido el llenado de este elemento.
*   **:optional**:Indica que es opcional el llenado de este elemento.
*   **:valid**:Indica elementos que se puedan validar.
*   **:invalid**:Indica elementos que no se puedan validar.
*   **:in-range y : out-of-range**: son determinados por el máximo y el mínino.

## Pseudoelementos
Estos usan condiciones "*fantasma*" y permiten aplicar estilos a algún elemento que no existe dentro del árbol de documentos, los *pseudoelementos* son estos:
```css
    E::first-line {
        ...
    }
    E::first-letter {
        ...
    }
    E::after {
        ...
    }
    E::before {
        ...
    }
```
### El pseudoelemento ::selection
Este se utiliza para darle estilo a algún elemento que ya ha sido seleccionado por el usuario,ejemplo:
```css
    p::selection {
        background-color: black;
            color: white;
    }
```
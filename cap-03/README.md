#   Selectores
En CSS existen los selectores los cuales se dividen en 2 categorías generales.
*   La primera son aquellos que actúan sobre elementos definidos en el árbol de documentos. tales como elementos `<p>` y atributos `href=""`
*   La segunda contiene "*pseudoselectores*" los cuales actúan sobre elementos que se encuentran fuera el árbol de documentos.

## Selectores de atributo 

El selector de atributos simple solamente aplican las reglas al atributo especificado ,independientemente del valor del atributo, ejemplo:
```css
    a[rel]{
        color:rgb(255,0,0);
    }
```
De igual manera existe un selector de atributos parcial con el que se busca el valor dentro de una lista separada por espacios, ejemplo de uso:
```html
    <li rel="friend met"><!--Valores a buscar-->
        Peter
    </li>
``` 
```css
    a[rel~='friend'] { /*El elemento "~" indica que se busque en una lista separada por espacios*/
        color: red;
    }
```
## Nuevos Selectores de atributo en CSS3
CSS3 permite una mayor flexibilidad en cuanto a los selectores de atributos.

### Selector de valor de atributo de subcadena inicial
El primer nuevo selector hace que busque elementos que comienzan con la cadena que se proporcione como argumento,sintaxis:
```css
    E[attr^='value'] {
        ...
    }
```
##### Ejemplo practico:
```html
    <!--Primer elemento-->
    <a  
        href="http://example.com/" 
        title="Image Library"
    >
        Example
    </a>
    <!--Segundo elemento-->
    <a  
        href="http://example.com/" 
        title="Free Image Library"
    >
        Example
    </a>
```
```css
    a[title^='image'] {
    ...
    }
```
En este caso solamente se aplicara al primer elemento de la lista , ya que es el único elemento que cumple con las reglas.

Este selector es muy usado para agregar información visual a los `hyperlinks` ejemplo:
```html
    <a href="http://example.com/">
        hyperlink
    </a>
```
```css
    a[href^='http'] {
        background: url('link.svg') no-repeat left center;
        display: inline-block;
        padding-left: 20px;
    }
```
### Selector de valor de atributo de subcadena final
Este básicamente es lo mismo que el selector de inicio ,solo cambia que este este va al final y se usa el signo "*$*" ,sintaxis:
```css
    E[attr$='value'] {
        ...
    }
```
Igual este sirve para aplicar un elemento visual a los `hyperlinks`.

### Arbitrary Substring Attribute Value Selector
Este selector busca dentro de la cadena de atributos independientemente su lugar, el selector es el "*",sintaxis:
```css
    E[attr*='value'] {
        ...
    }
```

Este selector es el mas flexible en cuanto a uso ya que puede hacer coincidir diversos elementos sin importar donde aparezcan.

### Multiple Attribute Selectors
Se pueden colocar diversas reglas de selectores en un mismo elemento con la finalidad de aplicar a un mayor rango de elementos `html`,ejemplo:
```css
    a
        [href^='http://']
        [href*='/folder2/']
        [href$='.pdf'] 
    {
    ...
    }
```
## The General Sibling Combinator
Es una extensión del "*Adjacent Sibling Combinator*", el cual solo cambia 1 carácter:
```css
    /* Adjacent Sibling Combinator */
    E + F {
        ...
    } 
    /* General Sibling Combinator */
    E ~ F {
        ...
    } 
```
Sus diferencias son:
*   **Adjacent Sibling**: Coloca las reglas de estilo al elemento hermano mas cercano.
*   **Genral Sibling**:Coloca las reglas de estilo a todos los elementos hermanos.

# Disposición de caja flexible
Se ha implementado el modelo "*flexbox*" el cual hace que los elementos cambien de tamaño para adaptarse mejor a su espacio disponible.

## Declarando el modelo de caja flexible
Para usar "*flexbox*" se debe primero crear el contenedor.

##### Sintaxis:
```css
    E {
        display: flex;
    }
```
`flex` crea un contenedor en bloque , `inline-flex` crea un contenedor en linea.

## Alineación de la Flexbox
Esta se basa en 2 ejes , eje vertical y horizontal y para marcarlos se `row` que se basa en el eje horizontal y `column` que se basa en el eje vertical.

## Invertir el orden del contenido
Gracias a `flexbox` se puede cambiar el orden de los elementos sin importar su orden en el DOM , y para eso esta `flex-direction`.

##### Sintaxis
```css
    E {
        flex-direction:"keyword";
    }
```
"*Keyword*":
*   **row-reverse**:Invierte el orden cuando la alineación se haya usado `row`
*   **column-reverse**:Invierte el orden cuando la alineación se haya usado `column`

## Reordenamiento completo del contenido
Con la propiedad `order` se puede modificar el orden de aparición de los elementos dentro del contenedor flexbox y su orden de aparición es del mas bajo al mas alto.

##### Sintaxis:
```css
    E {
        order:"lugar en el orden";
    }
```

## Añadiendo flexibilidad
### La propiedad flex-grow
Esta propiedad ayuda a llenar encajar a la medida los elementos dentro de los contenedores.

##### Sintaxis:
```css
    E {
        flex-grow:"value";
    }
```
Es valor es una proporción la cual se usa para distribuir el espacio vació entre los elementos flexibles dentro del contenedor, haciendo que se expandan , y si se especifica a algún elemento en especial un valor mayor , este se expandirá mas que los otros.

### La propiedad flex-shrink
Este se usa para encoger elementos y adaptarlos al contenedor.

##### Sintaxis:
```css
    E {
        flex-shrink: "value";
    }
```
Funciona como `flex-grow` pero en la dirección contraria ,y entre mayor sea el numero mayor sera la reducción de un elemento.

### La propiedad de flex-basis
Este se usa para establecer un valor para cambiar la forma del ajuste del ancho del elemento.

##### Sintaxis:
```css
    E {
        flex-basis: "value";
    }
```
Este se sobrepone ante el tamaño establecido a cada elemento.

### La abreviatura flex
##### Sintaxis:
```css
    E {
        flex: "-grow" "-shrink" "basis";
    }
```
## Alineación dentro del contenedor
### Alineación horizontal con contenido justificado
Con la propiedad `justify-content` permite redistribuir el espacio no utilizado.

##### Sintaxis:
```css
    .flex-container {
        justify-content:"keyword";
    }
```
"*Keywords*":
*   **flex-start**: Alinea los elementos a la izquierda 
*   **flex-end**: Alinea los elementos a la derecha
*   **center**: Coloca los elementos en el punto medio del contenedor
*   **space-between**: Agrega un espacio entre cada elemento
*   **space-around**: Coloca una cantidad igual de espacio en ambos lados de cada elemento

>   Se le aplica al contenedor

### Alineación vertical con align-items
Esta propiedad sirve para ajustar elementos cuando la altura es mayor a la de los elementos del contenedor.

##### Sintaxis:
```css
    E {
        align-items:"keyword";
    }
```
"*Keyword*":
*   **stretch**: Ajusta los elementos para que tengan la misma altura que el elemento principal.
*   **flex-start**: Alinea los elementos en la parte de arriba del contenedor
*   **flex-end**: Alinea los elementos en la parte inferior del contenedor
*   **center**: Alinea los elementos en la mitad del contenedor

>   Se le aplica al contenedor

### Alineación de ejes transversales con align-self
Esta propiedad ayuda a controlar la alineación transversal , esta propiedad se le aplica al elemento y sus valores son los mismo que `align-items` y solo se le aplica al elemento que se le coloco.

##### Sintaxis:
```css
    E {
        align-self: "keyword";
    }
```
### Envolver y fluir (Wrap and flow)
Con ayuda de la propiedad `flex-wrap` se pueden acomodar los elementos usando filas o columnas.

##### Sintaxis:
```css
    E {
        flex-wrap:"keyword";
    }
```
"*Keyword*":
*   **no-wrap**: Conserva los elementos de la misma manera.
*   **wrap**: Divide los elementos en lineas adicionales.
*   **wrap-reverse**: Coloca los elementos al final del contenedor.

### La abreviatura de flex-flow
`flex-flow` es una combinación de `flex-wrap` y `flex-direction`
##### Sintaxis:
```css
    E {
        flex-flow: "flex-direcion" "flex-wrap";
    }
```
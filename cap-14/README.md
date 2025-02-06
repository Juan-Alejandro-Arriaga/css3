# Transiciones y animaciones
Estos módulos permiten la animación de elementos dentro de la pagina.

*   **transiciones**:Solo tienen efecto cuando la propiedad a la que fue aplicada cambia de valor.
*   **animaciones**: Se ejecutan explícitamente al elemento.

## Transiciones
Es una animación que cambia la propiedad entre 2 estados, para que se cumpla un valor debe de cumplirse 4 condiciones:
*   **Un valor inicial**
*   **Un valor final**
*   **La transición**
*   **Un disparador**

##### Ejemplo:
```css
    E {
        background: rgb(255,0,0);/*Valor inicial*/
        transition:background-color 2s;/*Transicion*/
    }
    E:hover {/*:hover actua como disparador*/
        background:rgb(0,0,255);/*Valor final*/
    }
```

### transition-property
Esta especifica que propiedad es la que se animara.
##### Sintaxis:
```css
    E {
        transition-property: "keyword";
    }
```
Puede tener valores como `all` lo que hará que se anime toda propiedad valida, `none` o alguna propiedad en especifico.

##### Ejemplo:
```css
    h1 {
        font-size: 150%;
        transition-property:font-size;
    }
```

### transition-duration
Esta propiedad define el tiempo que tarda la transición en completarse.
##### Sintaxis:
```css
    E {
        transition-duration: "time";
    }
```
El valor del tiempo puede estar definido en segundos `s` o milisegundos `ms` , su valor predeterminado es `0`.

##### Ejemplo:
```css
    h1 {
        font-size: 150%;
        transition-property:font-size;
        transition-duration: 2s;
    }
```
### transition-timing-function
Se puede controlar la forma con la que un elemento cambia de estado usando la propiedad `transition-timing-function` permitiendo variaciones a la velocidad a lo largo de su duración, posee 3 tipos de valor diferentes:
*   **keyword**
*   **cubic-beizer()**
*   **steps()**

### Palabras clave de función de temporización
##### Sintaxis:
```css
    E {
        transition-timing-function: "keyword";
    }
```
Los posibles valores de "*keywords*" son:
*   **ease**:Comienza lentamente y se va acelerando rápidamente y se ralentiza al final.
*   **linear**:Mantiene su ritmo constante de inicio a final.
*   **ease-in**:Comienza lento y se acelera hasta llegar al final.
*   **ease-out**:Comienza rápido y desacelera hasta llegar al final.

##### Ejemplo:
```css
    h1 {
        font-size: 150%;
        transition-property: font-size;
        transition-duration: 2s;
        transition-timing-function: ease-out;
    }
```
#### La curva cúbica de Bézier
##### Sintaxis:
```css
    E {
        transition-timing-function: cubic-bezier(x1, y1, x2, y2);
    }
```
La curva de Béizer es una curva que pasa por cuatro puntos trazados en una cuadricula , se trazan con coordenadas "*x*" y "*y*" y el primero siempre esta en (0,0), y sus valores se colocan en fracción.

##### Ejemplo:
```css
    E {
        transition-timing-function: cubic-bezier(0.0,0.4,0.7, 1.0);
    }
```
#### La funcion steps()
Ejecuta la animación en intervalos escalonados

##### Sintaxis
```css
    E {
         transition-timing-function: steps("conteo", "dirección");
    }
```
*   **conteo**:Indica los intervalos que recorre la animación
*   **dirección**:Valor opcional que indica el punto en el que se produce el cambio en cada intervalo.

##### Ejemplo:
```css
    E {
        transition-timing-function: steps(4);
    }
```

"*dirección*" ayuda a seleccionar cuando ocurre el cambio paso por paso tiene 2 "*keywords*" posibles:
*   `end` significa que el cambio ocurre al final del paso  
*   `start` indica que el cambio ocurre al inicio del paso.

## transition-delay
Este establece el momento en el cual comienza la transición.
##### Sintaxis
```css
    E {
        transition-delay:"time";    
    }
```
El tiempo se mide igual que en `transition-duration`.

##### Ejemplo de uso:
```css
    h1 {
        font-size: 150%;
        transition-property: font-size;
        transition-duration: 2s;
        transition-timing-function: ease-out;
    }
```

Se pueden colocar valores negativos para crear efectos como partir desde la mitad de la transición , ejemplo:
```css
    E {
        transition-duration: 4s;
        transition-delay: -2s;
    }
```

### La propiedad de transición abreviada
Al igual que muchas propiedades tiene su versión abreviada y su sintaxis es esta:
```css
    E {
         transition: property duration timing-function delay;
    }
```
##### Ejemplo de uso:
```css
    E {
         transition: font-size 2s ease-out 250ms;
    }
```
### Múltiples transiciones 
Se pueden agregar varias transiciones , separando por comas.

## Animations
Estas permiten que se apliquen directamente a los elementos con una sintaxis más flexible.

### Keyframes
Para crear animaciones , es importante definir los fotogramas clave , puntos que marcan inicio y final de la transición, los fotogramas se declaran con la regla `@keyframes`.

##### Sintaxis:
```css
    @keyframes "name" { 
        "selector" { 
            property : value; 
        }
    }
```
*   **name**: Sirve como identificador único y para llamar a la animación.
*   **selector**: Establece la posición a lo largo de la duración de la animación, su valor es un porcentaje, y se puede usar palabras clave como : `from` o `to`.

### animation-name
Esta es la que hace referencia al nombre que se definió en la regla `@keyframes`.

##### Sintaxis:
```css
    E {
        animation-name:"name";
    }
```
Su único valor es el nombre de la animación.

### animation-duration
Es similar a `transition-duration` y acepta los mismos valores.

##### Sintaxis:
```css
    E {
        animation-duration:"time";
    }
```` 

### animation-timing-function
Funciona de manera idéntica a `transition-timing-funtcion`.

##### Sintaxis:
```css
    E {
        animation-timing-function:"value";
    }
```
### animation-delay
Funciona de manera idéntica a `transition-delay`.

##### Sintaxis:
```css
    E {
        animation-delay:"time";
    }
```

### animation-iteration-count
Las animaciones se pueden repetir cualquier cantidad de veces con esta propiedad.

##### Sintaxis:
```css
    E {
        animation-iteration-count:"cantidad";
    }
```

### animation-direction
Con esta propiedad se pueden establecer la dirección en la que se va a reproducir la animación.

##### Sintaxis:
```css
    E {
        animation-direction:"keyword";
    }
```
La "*keyword*" pueder ser:
*   **normal**:Inicia la animación de inicio a fin.
*   **alternate**:Inicia la animación de inicio a fin y de fin a inicio.

### animation-fill-mode
En el caso de no tener una valor para la propiedad  `animation-iteration-count` ya que no se quiere que se termine la animacion, se puede usar la propiedad `animation-fill-mode`.

##### Sintaxis:
```css
    E {
        animation-fill-mode:"keyword";
    }
```
"*Keywords*":
*   **none**
*   **towards**:Esta hará que se apliquen las especificaciones al elemento antes que comience la animación.
*   **fowards**:Esta hará que las especificaciones se apliquen cuando finalice la animación.
*   **both**:Sucederá lo de las 2 *keywords*

### animation-play-state
Esta establece si la animación esta activa.

##### Sintaxis
```css
    E {
        animation-play-state:"keyword";
    }
```
"*Keyword*":
*   **running**: Indica que la animación esta corriendo.
*   **paused**: Indica que la animación esta pausada.

##### Caso de uso:
```css
    E:hover { 
        animation-play-state: paused; 
    }
```
Aquí la animación estará activa ,hasta que el puntero del ratón pase por encima del elemento.

### La propiedad de animación abreviada
##### Sintaxis:
```css
    E { 
        animation: 
            name
            duration
            timing-function 
            delay 
            iteration-count
            direction
            fill-mode 
            play-state; 
    }
```

##### Ejemplo:
```css
    div { 
        animation: 
            expand 
            6s 
            ease-in 
            2s 
            10 
            alternate 
            both 
            running;
    }
```
### Múltiples animaciones
Se pueden agregar varias transiciones , separando por comas.

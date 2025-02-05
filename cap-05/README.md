# Fuentes en la web
Las fuentes son el estilo tipográfico que se le da a las letras dentro de las paginas web.

Las fuentes para la web fueron una idea que se retomo hasta hace no mucho tiempo ,aún así IE fue el primer navegador el cual permitió fuentes en la web.

## La regla del @font-face
Para mostrar fuentes primero deben ser definidas mediante la regla "*@font-face*", con esta se establece el nombre y tipo de fuente, ademas de su ubicación de la fuente.
##### Sintaxis:
```css
    @font-face {
        font-family: FontName; /*Se nombra la propiedad*/
        src:
            wlocal('Nombre de la fuente'),/*Comprueba si la fuente ya esta instalada la maquina del usuario*/
            url('/directorio/nombre-fuente.otf') /*Da la ubicación del archivo de la fuente*/  
            format('opentype');/*Indica el formato de la fuente*/
    }
```
Una vez ya definida solamente se llama a la fuente,sintaxis:
```css
    E {
        font-family:NomFuente;
    }
```
### Definiendo diferentes caras
Para definir varios tipos de fuente , se debe hacer individualmente , cada una dentro de su regla de `@font-face`.
##### Ejemplo:
```css
    @font-face {
        font-family: 'Classic By Ale';
        src: url('CByA.woff') format('woff');
    }
    @font-face {
        font-family: 'Classic By Ale';
        font-style: italic;
        src: url('CByA.woff') format('woff');
    }
```
### Tipos de letra auténticos y artificiales
En el caso de que no se tenga un buen enlace al archivo de la fuente , el navegador intentara recrearla de manera artificial.

##### Un ejemplo del como NO se debe hacer:
```css
    @font-face  {
        font-family: 'Gentium Basic';
        src: url('GenBasR.woff') format('woff');
    }
    h1 {
        font-family: 'Gentium Basic', sans-serif;
        font-style: italic;
    }
``` 
## Una sintaxis @font-face “a prueba de balas”
Los formatos de fuente pueden causar errores de compatibilidad con navegadores de versiones antiguas, y los siguen tes son problemas que se presentan.

### Using Local Fonts
`local()` es un atributo del `src` que comprueba si la fuente ya la posee el navegador, aunque no es compatible con ninguna versión de IE 9 anterior , así que es mejor saltar de lado este atributo.

### Formatos de fuentes
Anteriormente solo se admitía el tipo de fuente "*Embed Open Type(EOT)*" propiedad de Microsoft.

Mozilla creo el formato "*Web Open Format(WOOFF)*" el cual son fuentes de uso sin licencia , volviéndose compatible con todos los navegadores principales.

### La sintaxis definitiva “a prueba de balas”
Esta es la sintaxis:
```css
    @font-face {
        font-family: 'Gentium Basic';
        src: url('GenBkBasR.eot');
        src: 
            url('GenBasR.eot?#iefix') format('embedded-opentype'),
            /*Fuente para IE y versiones anteriores*/
            url('GenBkBasR.woff') format('woff'),
            /*Para la mayoria de los navegadores*/
            url('GenBkBasR.ttf') format('truetype');
            /*Para navegadores mas antiguos*/
    }
```
## Licencias de fuentes para uso web
Algunos creadores de fuentes prohíben colocar fuentes en paginas web con `@font-face` ya que se pueden descargar y usar ilegalmente, debido a eso se creo el formato "*WOFF*" el cual es solo para web y con el se puede rastrear a cualquier infractor de derechos de autor.

Se debe verificar que la fuente que se usa tenga una licencia que permita la incrustación en la web.

## Controlar la carga de fuentes
Las fuentes web se cargan como recursos externos y el navegador debe las descargarlas , antes que se cargue el archivo ,es probable apreciar un "destello" antes de que la fuente se cargue

## Más propiedades de fuentes
Las siguientes fuentes proporcionan un control a las fuentes.

### font-size-adjust 
Las fuentes pueden variar al usar pilas, y puede alterar la visualización , para eso esta la propiedad `font-size-adjuts` el cual garantiza una apariencia regular:
##### Sintaxis:
```css
    E {
        font-size-adjust: number ;
    }
```
El valor es sobre la proporción de la altura total que ocupa un carácter.

##### Ejemplo:
```css
    p {
        font-size-adjust: 0.5 ;
    }
```
Facilita la lectura sin importar la fuente que se muestre.

### font-stretch
Con esta propiedad permite acceder a variantes de fuentes condensadas o expandidas.
##### Sintaxis:
```css
    E {
        font-stretch: keyword ;
    }
```
El "*keyword*" puede ser cualquiera de los siguientes:
*   **normal**
*   **ultra-condensed**
*   **extra-condensed**
*   **condensed**
*   **semi-condensed**
*   **semi-expanded**
*   **expanded**
*   **extra-expanded**
*   **ultra-expanded**

Cada "*keyword*" se relaciona con una variante de fuente dentro de una familia.

## Caracteristidas de "OpenType"
Este tipo de formato son sumamente capaces ya que poseen diversos aspectos como ,ligaduras, caracteres especiales y mas.

### Habilitación de funciones de fuentes
Se implemento la propiedad `font-feature-settings` con la cual permite explorar las funciones que ofrece "*Open Type*"
##### Sintaxis:
```css
    E {
        font-feature-settings: "parámetros";
    }
```
Los "*parámetros*" son serie de cadenas que contienen códigos abreviados, ademas es posible activarlo y desactivarlo con *on* y *off*.

>On: Para activar
>Off: Para desactivar

Se pueden colocar múltiples parámetros solo separando con una coma.

### Propiedades de las características de fuente
Las características vistas anteriormente también se especifican como propiedades individuales , conocidas como propiedades `font-variant-*`.

##### Ejemplo de uso:
```css
    E {
        font-variant-ligatures: no-discretionary-ligatures;
    }
    
```
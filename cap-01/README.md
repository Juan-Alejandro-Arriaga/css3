# Introduciéndonos a CSS3
Es importante conocer cada nueva propiedad que se llegue a agregar para tener una mejor comprensión de su uso actual y a futuro.

## ¿Qué es CSS3 y cómo surgió?
### Una breve historia de CSS3
Las siglas "**CSS**" son una acrónimo que significa "*Cascading Style Sheets*"

La versión mas importante de "*CSS*" fue la "*CSS2.1*" siendo esta la recomendación oficial del "*W3C*" en 2011.

El primer navegador el cual soportaba "*CSS2.1*" fue "*Internet Explorer*" lanzado en 2008.

La especificación "*CSS3*" en el momento que se publicó el libro se encontraba en desarrollo activo , y una gran variedad de navegadores se encontraban implementandola.

### CSS3 es modular 
Debido a la dificultad para crear el lenguaje de estilo predeterminado para todos los documentos basados en marcado, se tuvo que dividir en diversos módulos para que se pudiera trabajar por diferentes autores y a diferentes ritmos.

### No hay CSS3

Como tal "*CSS3*" no existe ya que como esta dividido en módulos, este solamente es una abreviatura para decir "*CSS features developed since CSS2.1*" , así que se puede decir que "*CSS4*" nunca existirá.

## Estado del módulo y proceso de recomendación

Los estados de cada modulo son establecidos por el "*W3C*",además que indica el proceso del módulo por medio del proceso de recomendación.

En el momento que un documento propuesto se acepta por primera vez como parte de "*CSS3*" ,el estado se designa como borrador de trabajo.

Antes de que deje de ser un borrador de trabajo , este cambia su estado al de ultima convocatoria (*Last Call*) ,dando a entender que el documento esta listo para pasar al siguiente proceso.

En ocasiones un modulo puede estar implementado en los navegadores y aún así estar en fase de borrador.

## Introduciendo la sintaxis
Su sintaxis básica es algo como esto:
```css
    E {
        property:value;
        /*propiedad:valor;*/
    }
```
En donde se encuentra la letra "*E*" se puede colocar cualquier selector.

Algunas propiedades aceptan múltiples valores,por ejemplo:
```css
    E {
        propiety : first second third;
    }
```
##### EJEMPLO DE USO:

```css
    E {
        flex : 1 ;
    }
```
## Prefijos de proveedores
Cuando un módulo se encuentra bajo revisión activa algunas propiedades pueden modificarse o eliminarse por completo.

Para evitar el problema que había acerca de que existieran diferentes maneras de implementar las funcionalidades de "*CSS*" cada navegador colocaba un código al comienzo de las propiedades experimentales.
```css
    E{
        -moz-monkeys: value; /* Firefox */
        -ms-monkeys: value; /* Internet Explorer */
        -webkit-monkeys: value; /* Chrome/Safari */     
    }
```
Con esto hace que todos los navegadores puedan interpretar correctamente la funcionalidad.

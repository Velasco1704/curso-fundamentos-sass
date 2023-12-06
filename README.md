# Curso de Fundamentos SASS

## Que es SASS

<p>Sass es un lenguaje de hojas de estilo en cascada (CSS) con superpoderes. Es una extensión de CSS que agrega características y funcionalidades adicionales para facilitar la escritura y el mantenimiento de estilos en un sitio web. Sass permite utilizar variables, anidamiento de selectores, mixins, funciones y más, lo que ayuda a reducir la repetición de código y a crear estilos más eficientes y modulares.

Sass se compila en CSS estándar antes de ser utilizado en un sitio web. Esto significa que los navegadores web pueden interpretar y mostrar los estilos escritos en Sass como si fueran CSS normales.</p>

## Características de SASS

<ul>
  <li><strong>Variables</strong>: Sass permite definir variables para almacenar valores reutilizables, lo que facilita la actualización y el mantenimiento de estilos.</li>
  <li><strong>Anidamiento de selectores</strong>: Sass permite anidar selectores CSS dentro de otros selectores, lo que ayuda a organizar y estructurar el código de manera más clara.</li>
  <li><strong>Mixins</strong>: Los mixins son bloques de código reutilizables que se pueden incluir en diferentes selectores. Esto permite definir estilos comunes una vez y reutilizarlos en múltiples lugares.</li>
  <li><strong>Funciones</strong>: Sass proporciona funciones predefinidas y también permite crear funciones personalizadas para realizar cálculos y manipulaciones en los estilos.</li>
  <li><strong>Importación</strong>: Sass permite importar archivos Sass en otros archivos, lo que facilita la modularidad y la organización del código.</li>
  <li><strong>Operaciones matemáticas</strong>: Sass permite realizar operaciones matemáticas en los estilos, lo que puede ser útil para calcular tamaños, márgenes, colores, etc.</li>
  <li><strong>Directivas de control</strong>: Sass ofrece directivas de control, como condicionales y bucles, que permiten generar estilos de manera dinámica y basada en ciertas condiciones.</li>
</ul>

## Top-level statements

<p>Son declaraciones que solo se pueden usar en la parte superior de la hoja de estilos</p>

<ul>
  <li>Imports</li>
  <li>Definición de un Mixin</li>
  <li>Definición de una Función</li>
  <li>Módulos</li>
</ul>

## Universal statements

<p>Son statements que podemos usar en cualquier parte de la hoja de estilos.</p>

<ul>
  <li>Variables, estructuras de control y las reglas @error, @warn y @debug.</li>
  <li>Declaraciones CSS: Reglas de estilo, At-rules y Mixis.</li>
</ul>

## Diferencias en Variables en CSS y SASS

### CSS Variable

<ul>
  <li>Pueden tener diferentes valores para distintos elementos.</li>
  <li>Son Declarativas</li>
</ul>

### Sass Variables

<ul>
  <li>Tienen un valor único correspondiente a un elemento</li>
  <li>Son imperativas (en el momento en el que actualicemos el valor de nuestra variables va a cambiar en automático)</li>
</ul>

## Scope dentro de SASS

<p>Hace referencia al contexto en el que son declaradas las variables y donde es posible hacer uso de las mismas, hay dos tipos de variables</p>

<ul>
  <li><strong>Locales</strong>: Declaradas dentro de un bloque { }Cualquier selector anidado puede acceder a las variables locales declaradas dentro del selector.</li>
  <li><strong>Globales</strong>: Todas las variables declaradas fuera de un selector son globales, esto significa que se puede acceder a ellas en cualquier parte de nuestra hoja de estilos.<li>
</ul>

## Shadowing

<p>Las variables locales y globales pueden tener el mismo nombre ya que se encuentran en diferentes niveles del scope para evitar que se modificquen por error las variables globales.</p>

## !global flag

<p>Se usa en caso de querer modificar el valor global de una variable dentro del scope de una variable local.</p>

## At Rules CSS

<ul>
  <li><strong>@use</strong>: importa, módulos estilos y funciones de otras hojas de estilos. La diferencia con @import es que @use se encarga de hacer los estilos globales.</li>
  <li><strong>@function</strong>: permite crear funciones personalizadas, sin embargo, Sass cuenta con funciones ya existentes.</li>
  <li><strong>@forward</strong>: Recibe como parámetro una URL y nos ayuda a cargar los estilos de nuestra hoja de estilos. Es muy importante hacer uso de @use para que los módulos estén disponibles en nuestra hoja de estilos.</li>
  <li><strong>@extend</strong>: tiene que ver con el concepto de herencia.</li>
  <li><strong>@at-root</strong>: se encarga de cargar nuestros estilos en el root del CSS.</li>
  <li><strong>@include</strong>: nos ayuda a invocar los mixins.</li>
  <li><strong>@error, @warn, @debug</strong>: sirven para cuando hay un error, una advertencia o se quiere debugear, respectivamente.</li>
  <li><strong>@for, @if, @each, @while</strong>: tienen que ver con estructuras de control, se pueden usar dentro de una función.</li>
</ul>

## Expresiones Literales

<p>Una expresión es todo aquello que va del lado derecho de una variable, admitiendo varios tipos de valores. Las expresiones son mucho más poderosas que los valores CSS simples, ya que se pasan como argumentos a mixins y funciones.</p>

<ul>
  <li>Números</li>
  <li>Strings</li>
  <li>Colores</li>
  <li>Booleanos</li>
  <li>Null</li>
  <li>Listas</li>
  <li>Mapas</li>
</ul>

## Que son los Mixins

<p>Los mixins en Sass son una característica que permite definir y reutilizar bloques de código CSS. Los mixins son similares a las funciones en otros lenguajes de programación, ya que permiten definir un conjunto de estilos que se pueden incluir en diferentes selectores.

Al utilizar mixins, puedes evitar repetir código y mantener un código más limpio y modular. Puedes definir un mixin con un nombre descriptivo y luego incluirlo en diferentes selectores utilizando la directiva @include.<p>

![image](https://static.platzi.com/media/user_upload/mixin-sass-22108b1f-baac-4a93-a11a-fbeeb97ad95d.jpg "image")

![image](https://static.platzi.com/media/user_upload/argumentos-sass-7e2d1101-aed9-4553-abcb-048d3ef88032.jpg "image")

## Funciones en SASS

<p>Las funciones se definen utilizando la regla @function, que se escribe @nombre de función (argumentos...) {...}. El nombre de una función puede ser cualquier identificador de Sass. Solo puede contener declaraciones universales, así como la regla @return at que indica el valor a usar como resultado de la llamada a la función. Las funciones se llaman utilizando la sintaxis normal de funciones CSS.</p>

### Jerarquía de operaciones

<ul>
  <li>Los operadores unarios<strong>not,+ y -</strong></li>
  <li>Operadores<strong>*, / y %</strong></li>
  <li>Operadores<strong>*, / y %</strong></li>
  <li>Operadores<strong>+ y -</strong></li>
  <li>Operadores<strong>>, >=, <, <=</strong></li>
  <li>Operadores de comparación <strong>== y !=</strong></li>
  <li>Operadores de lógicos <strong>and</strong></li>
  <li>Operadores de lógicos <strong>or</strong></li>
  <li>Operadores de asignación <strong>=</strong></li>
</ul>

![image](https://static.platzi.com/media/user_upload/funciones-sass-33763e1a-15e2-409e-b947-33721261300b.jpg "image")

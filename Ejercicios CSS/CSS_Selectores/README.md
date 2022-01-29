# SELECTORES CSS: PSEUDO-CLASES  

En este apartado, vamos a hablar sobre las pseudo-clases, que nos permiten aplicar estilos en función de la interacción del usuario, o la posición el mismo dentro de la estructura del documento.  

A continuación vamoa aprender cómo utilizar selectores para identificar elementos en función de su estado, o incluso para seleccionar un determinado rango de ellos. Todo esto lo haremos con la ayuda de las pseudo-clases.  

## Pseudo-clases

Las pseudo-clases son parecidas a las clases de HTML, con la diferencia de que no están indicadas explícitamente en la etiqueta, ya que son consecuencia del resultado de la interacción del usuario con determinados elementos, o el estado de los mismos.  

Su sintaxis es sencilla: tienes que poner a la izquierda el selector, seguido de dos puntos **:**, y la pseudo clase. Por ejemplo, a través de a:hover podremos establecer los estilos que se aplicarán a los enlaces **a** cuando se pase el ratón por encima de ellos **:hover**.

### Relacionadas con acciones del usuario

Como en el ejemplo anterior, en este punto tratamos las pseudo-clases que se aplican dinámicamente a un elemento en función de determinadas acciones del usuario. Aquí nos encontramos con **:hover**, **:active** y **:focus**.  

> **:hover**, tal y como explicamos antes, se aplica cuando el usuario pasa el cursor encima del elemento. Normalmente se utiliza en enlaces y botones.  

> **:active** es aplicado cuando el usuario interactúa con el elemento, por ejemplo, haciendo click sobre él.  

> **:focus** se aplica a un elemento cuando tiene el foco de la página. Lo más común es cuando se está editando un campo del formulado (tenemos el foco sobre él para escribir) y cuando navegamos entre elementos mediante la tecla tab.

```CSS
a:hover {...}
a:active {...}
a:focus {...}
```

### De enlaces
Las pseudo-clases **:link** y **:visited** definen si un link ha sido o no visitado (es decir, si se ha pulsado o no sobre él). Para dar estilos a un enlace que todavía no ha sido visitado, usaremos **:link**, y para el que ya haya sido visitado, **:visited**.

```CSS
a:link {...}
a:visited {...}
```

### Del estado de la interfaz
Estas pseudo-clases tienen un comportamiento muy similar a las anteriores, pero son aplicadas a elementos de formularios. En esta categoría nos encontramos con **:enabled**, **:disabled**, **:checked** e **:indeterminate**.

> **:enabled** se aplica a aquellos elementos del formulario que se encuentren activos (es decir, que se pueda interactuar con ellos). Por defecto, los elementos suelen están activos.

> **:disabled** es el caso contario. Se aplica a elementos que no están activos, normalmente porque tienen el atributo disabled en su etiqueta de HTML.

> **:checked** se aplica a los elementos checkbox y radio button de un formario, cuando están seleccionados.

>**:indeterminate** también se aplica a checkbox y radio button. En este caso, a través de esta pseudo-clase podremos establecer los estilos de estos elementos cuando su estado sea indeterminado. Según la MDN, el estado de un checkbox puede ser indeterminado cuando se establece esta propiedad a true mediante JavaScript. A su vez, un radio button es indeterminado cuando todos los que tienen el mismo valor name no están marcados. Como podrás imaginar, esta propiedad es mucho más inusual que las anteriores.

```CSS
input:enabled {...}
input:disabled {...}
input:checked {...}
input:indeterminate {...}
```
### Relacionadas con la estructura y posición
Estas son las pseudo-clases más potentes, ya que nos permiten hacer una gran cantidad de cosas ahorrándonos estableces clases y atributos innecesarios en nuestro código HTML.

Como su nombre indica, se basan en cómo están posicionados los elementos del árbol del documentos.

#### **:first-child**, **:last-child** y **:only-child**

Vamos a empezar por la relacionadas con la posición como hijo: **:first-child**, **:last-child** y **:only-child**.

> **:first-child** selecciona al elemento solo si es el primer hijo.

> **:last-child** es al contrario, selecciona al elemento que es el último hijo.

> **:only-child** seleccina solo a elementos que son hijos únicos, es decir, que no tienen hermanos.

```CSS
p:first-child {...}
p:last-child {...}
h2:only-child {...}
```
```HTML
<section>
	<p>Elemento seleccionado por :first-child</p>
    <p>...</p>
    <article>
        <h2>Elemento seleccionado por :only-child</h2>
        <span>...</span>
    </article>
    <p>...</p>
    <article>
        <h2>...</h2>
        <span>...</span>
        <h2>...</h2>
        <span>...</span>
    </article>
    <p>Elemento seleccionado por :last-child</p>
</section>
```

#### **:first-of-type**, **:last-of-type** y **:only-of-type**

Los siguientes son muy similares y son los relacionados con la posición como hijo del mismo tipo: **:first-of-type**, **:last-of-type** y **:only-of-type**.

Como se puede imaginar, seleccionar el primero, último y único hijo de un elemento puede ser muy útil. Pero, ¿y qué pasa si queremos seleccionar solo el que es de un mismo tipo? Para eso tenemos estas pseudo-clases.

> **:first-of-type** selecciona al elemento de su tipo que sea el primer hijo.

> **:last-of-type** es al contrario, selecciona al elemento del mismo tipo que sea último hijo.

> **:only-of-type** seleccina al elemento que sea el único hijo de su tipo.

Al principio, puede parecer igual que los anteriores, pero veamos un ejemplo:

```CSS
p:first-of-type {...}
p:last-of-type {...}
h2:only-of-type {...}
```
```HTML
<section>
    <h1>...</h1>
    <p>Elemento seleccionado por :first-of-type</p>
    <p>...</p>
    <p>Elemento seleccionado por :last-of-type</p>
    <article>
    	<h2>Elemento seleccionado por :only-of-type</h2>
    	<span>...</span>
    </article>
</section>
```

Como se puede ver, solo se tiene en cuenta el tipo de elemento, ignorando el resto de hermanos de distinto tipo. Si en lugar de :first-of-type, :last-of-type y :only-of-type hubiéramos utilizado :first-child, :last-child y :only-child, no se habría seleccionado ningún elemento. ¿Se entiende ahora la diferencia?

Siguiendo con las pseudo-clases relacionadas con la estructura y la posición. Hasta ahora sabemos seleccionar los primeros hijos, los últimos y los únicos. ¿Qué pasa con resto? ¿Podemos seleccionar el hijo que queramos, esté donde esté? La respuesta es sí, gracias a :nth-child(n), :nth-last-child(n), :nth-of-type(n) y :nth-last-of-type(n). En estas pseudo-clases utilizaremos números y expresiones algebraicas (será lo que incluirás dentro de los paréntesis) para realizar las selecciones, como vamos a ver a continuación.

:nth-child(n) y :nth-last-child(n)

:nth-child(n) selecciona elementos contando desde el primer hijo, sin importar el tipo de este, ni del resto de hijos. Por ejemplo, si quieres un elemento de cada tres, puedes usar la expresión 3n.

```CSS
p:nth-child(3n) {...}
```
```HTML
<div>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
</div>
```
Como se puede ver, aquí empezamos a contar desde cero.

También se puede seleccionar un elemento de cada tres, pero empezando por uno en concreto. Por ejemplo, si se quiere, al igual que antes, seleccionar uno de cada tres, pero empezando por el primero, se usaría la expresión (3n+1).

```CSS
p:nth-child(3n+1) {...}
```
```HTML
<div>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
</div>
```
Otra posibilidad de este tipo de pseudo-clase es que podemos seleccionar únicamente un hijo según su posición. Por ejemplo, si en vez de seleccionar un elemento de cada tres, solo queremos seleccionar el tercero, usaríamos (3).

```CSS
p:nth-child(3) {...}
```
```HTML
<div>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
</div>
```
¿Hay más? ¡Pues sí!

¿Qué pasa si queremos seleccionar los tres primeros? Para eso, podemos usar la expresión (-n+3).

```CSS
p:nth-child(-n+3) {...}
```
```HTML
<div>
    <p>Elemento seleccionado</p>
    <p>Elemento seleccionado</p>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
</div>
```
¿Es potente o no es potente? Imagina todas las posibilidades.

Ahora vamos a pasar de :nth-child(n) a :nth-last-child(n).

:nth-last-child(n) funciona prácticamente igual que :nth-child(n) , con la única diferencia de que, en vez de empezar a contar desde el principio, empieza por el final.

Por ejemplo, para seleccionar el tercero empezando desde el final:

```CSS
p:nth-last-child(3) {...}
```
```HTML
<div>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
</div>
```
O para seleccionar los tres últimos.

```CSS
p:nth-last-child(-n+3) {...}
```
```HTML
<div>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
    <p>Elemento seleccionado</p>
    <p>Elemento seleccionado</p>
</div>
```
:nth-of-type(n) y :nth-last-of-type(n)

Si has llegado hasta aquí y lo has estado entendiendo todo, probablemente ya te imaginarás el funcionamiento de :nth-of-type(n) y :nth-last-of-type(n). Si no es así, ¡no pasa nada! Voy a explicarlo también.

:nth-of-type(n) cuenta solo los hijos del mismo tipo (es decir, como si los de otros tipos no existieran), comenzando desde el principio.

```CSS
p:nth-of-type(3) {...}
```
```HTML
<section>
	<h1>...</h1>
    <p>...</p>
    <p>...</p>
    <p>Elemento seleccionado</p>
</section>
```
¿Ves la diferencia? Si hubiéramos utilizado :nth-last-child(n) se habría seleccionado el elemento p anterior, ya que se empezaría a contar desde el primero si importar el tipo, que en este caso sería el h1 .

:nth-last-of-type(n) funciona de forma muy similar, pero contando desde el final (recuerda, del mismo tipo).

```CSS
p:nth-last-of-type(3) {...}
```
```HTML
<section>
    <p>Elemento seleccionado</p>
    <p>...</p>
    <p>...</p>
    <span>...</span>
</section>
```
target
Seguro que en muchas ocasiones habrás utilizado enlaces para acceder a secciones de una misma página. Una URL con el símbolo # seguido de un texto enlaza a un elemento concreto de la página, cuyo ID corresponde con el del enlace.

Se conoce como elemento target a aquel que ha sido enlazado (es decir, cuando ya aparece en la URL el símbolo # seguido de su ID).

La pseudo-clase :target nos permite aplicar estilos al elemento target en cuestión. Puede parecer un poco confuso el concepto en un principio, pero con el siguiente ejemplo seguro que te queda todo mucho más claro.

```CSS
:target {
  background-color: #0288D1;
  color: #fafafa;
  border-radius: 5px;
}
```

empty
Esta pseudo-clase nos permite identificar elementos que no contienen ningún hijo o nodo de texto.

Es útil para elementos dinámicos. Por ejemplo, para mostrar un mensaje de No se han encontrado resultados cuando se hace una búsqueda y no se muestra ningún elemento.

```CSS
section:empty {...}
```
```HTML
<section>
    <h1>...</h1>
</section>
<section></section> <!-- Elemento seleccionado -->
```
not(x)
También conocida como pseudo-clase de negación. :not(x) recibe como argumento (x), el filtro que usará para descartar elementos en la selección. Por ejemplo, div:not(.content) seleccionará todos los divs, excepto los que estén identificados con la clase content.

Otro ejemplo útil puede ser :not(p), a través del cual seleccionamos todos los elementos del documento, a excepción de los párrafos.
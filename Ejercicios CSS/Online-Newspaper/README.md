# CSS EJERCICIOS: Online-Newspaper

## 1. DISEÑO DE UN PERIÓDICO ONLINE

Para la resolución de este ejercicio se utilizarán los archivos de la carpeta *news* que se encuentra en este mismo repositorio.
Como puedes comprobar en su interior hay 4 archivos:  
>
> * index.html (la página principal del periódico)  
> * item.html (una página que representa una de las noticias del periódico),  
> * register.html y
> * login.html (páginas para que los usuarios se puedan registrar y acceder).

Antes de continuar, toma un momento para analizar detenidamente la estructura de los archivos y su contenido.  
Como habrás podido comprobar, todas las páginas tienen referencias a 5 archivos css:  

> * style.css ( estilo de los componentes principales),  
> * layout.css ( posicionamiento de los componentes),  
> * responsive.css ( permite hacer la página responsive),  
> * comments.css (diseño de la sección de comentarios) y  
> * forms.css ( diseño de los formularios de login y registro).

Sin cambiar el código HTML de los ficheros, intenta desarrollar un diseño siguiendo los siguientes 5 pasos:

### 1.1 MAIN STYLE

Ahora vamos a comenzar a diseñar los componentes de la página principal sin preocuparnos por el posicionamiento. Utiliza el fichero *style.css* para crear un diseño lo más parecido a este [diseño base](./step1.html)

A continuación se Some helper values:

>* Colores de la estructura principal: #2A2F33, #046DD5 y #F4655F.
>* Colores para las secciones: #E1493E, #8ABA56, #5B4282, #FF8932,#19B6E9 y #E84C8B.
>* Fuentes usadas: Verdana y Georgia.
>* La mayoría de paddings y margins con 1em.
>* Tip: Te habrás dado cuenta que la sección *nav* contiene un *input* y una etiqueta (*label*). Ambos elementos son parte del punto 1.3 del ejercicio y por ahora puedes obviarlos o esconderlos usando CSS mediante la etiqueta *hidden*

### 1.2 POSICIONAMIENTO

En este segundo apartado se han de colocar los elementos dibujados en sus posiciones correspondientes (layout.css). El resultado final debe ser similar a [este]("./step2.htlm") .

A continuación se dan los valores de colores y tamaños para la web:
>
> * El color del background es #EDEFF0.
> * El width de la página es 60em.
> * Los sidebar ocupan 1⁄5 del width total.
> 
> Tip: Usa flexbox para el menú y un grid para posicionar los elementos en la página.


### 1.3 RESPONSIVE DESIGN
We will now make the design responsive by establishing two break points (responsive.css):

When the width of the window reaches 60em, the sidebar should disappear and the page should occupy the full width (100%) of the window. The final result should be this .
When the width of the window reaches 30em, the menu should collapse into a pull-down menu, the subtitle should not be shown and each news item title should be moved to above the item image. The final result should be this .
Some helper values:

Characters for the hamburger menu: \2630 (☰) and \2715 (✕).
Tip: Start by making the menu without any animations (using display to hide and show the menu items). After that, try using transitions to change the height of each menu item instead.

### 1.4 COMMENTS DESIGN  

Add CSS rules (comments.css) to create the design for the comment section that can be seen in the item.html page. The final result should be this .

Some helper values:

Quote character for each comment: \201C (“).

### 1.5 DISEÑO DE FORMULARIOS  

Añade las Add CSS rules (forms.css) to create the design for the register and login forms that can be seen in the register.html and login.html pages. The final result should be this.  

Make sure that in smaller screens, the form fills the content area like this.  

## 2. FLEXBOX/GRID DESIGN  

Without using the flexbox and grid CSS layouts, try to recreate some designs.

Copy the following HTML code: news.html into a new .html file.
Open it and observe its structure.
As you might have noticed, this document references a, not yet created, file named style.css as its style sheet. Create that file and modify it so that the page appearance becomes as similar to the following designs as possible: style 1 , style 2 and style 3
Style 2 uses the following image: 
Extra: Now try the same exercises, this time using flexbox and grid layouts.

## 3. BLOCKS
Unzip the following file into some folder: blocks.zip
Inside a file called style.css, try recreating each one of the four following designs using flexbox and grid layouts:
3.1

Tips:

Use a flexbox layout for this one.
Orange block uses the remaining space.
3.2

3.3

Tips:

First item in yellow block is three times the size of the others.
Items in red block are reversed.
Left column has 1⁄4 of the total width.
3.4

Tips:

Green and orange blocks have half the height of the red and yellow ones.
=======
> * El width de la página es 60em.
> * Los sidebar ocupan 1⁄5 del width total.
> * Tip: Usa flexbox para el menú y un grid para posicionar los elementos en la página.
>>>>>>> 13498f3ba1d5ce81aac277dc2badb843f06ab623

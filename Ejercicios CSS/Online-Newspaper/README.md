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

> style.css ( estilo de los componentes principales),  
> layout.css ( posicionamiento de los componentes),  
> responsive.css ( permite hacer la página responsive),  
> comments.css (diseño de la sección de comentarios) y  
> forms.css ( diseño de los formularios de login y registro).

Sin cambiar el código HTML de los ficheros, intenta desarrollar un diseño siguiendo los siguientes 5 pasos:

### 1.1 MAIN STYLE

Ahora vamos a comenzar a diseñar los componentes de la página principal sin preocuparnos por el posicionamiento. Utiliza el fichero *style.css* para crear un diseño lo más parecido a este [diseño base](./step1.html)

A continuación se Some helper values:

>Colores de la estructura principal: #2A2F33, #046DD5 y #F4655F.
>Colores para las secciones: #E1493E, #8ABA56, #5B4282, #FF8932,#19B6E9 y #E84C8B.
>Fuentes usadas: Verdana y Georgia.
>La mayoría de paddings y margins con 1em.
>Tip: Te habrás dado cuenta que la sección *nav* contiene un *input* y una etiqueta (*label*). Ambos elementos son parte del punto 1.3 del ejercicio y por ahora puedes obviarlos o esconderlos usando CSS mediante la etiqueta *hidden*

### 1.2 POSICIONAMIENTO

En este segundo apartado se han de colocar los elementos dibujados en sus posiciones correspondientes (layout.css). El resultado final debe ser similar a [este](./step2.htlm) .

A continuación se dan los valores de colores y tamaños para la web:
>
> * El color del background es #EDEFF0.
> El width de la página es 60em.
> Los sidebar ocupan 1⁄5 del width total.
> Tip: Usa flexbox para el menú y un grid para posicionar los elementos en la página.

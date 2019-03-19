# Buenas prácticas en maquetación

## Qué cosas deben definirse inicialmente a partir del diseño

### Línea base del grid
Es necesario definir la línea base del grid que es el tamaño de la cuadrícula usada a la hora de diseñar la web.

Solemos usar la línea base de [Material Design](https://material.io/design/layout/understanding-layout.html#) que consiste en:
* Un grid de **8x8** para alinear los componentes y el layout en general.
* Un grid de **4x4** para alinear pequeños componentes como la tipografía y los iconos.

![grid](img/grid.png)

### Paleta de colores
Un listado de todos los colores principales con sus variantes y la escala de grises a usar en la web.

### Breakpoints
Los breakpoints son las anchuras del viewport donde necesitaremos ajustar partes del layout y componentes para ajustarte a un tamaño diferente de pantalla.

Habitualmente se suelen tener:

| breakpoint    | Desde  | Hasta    |
|---------------|--------|----------|
| mobile small  | 0px    | 575px    |
| mobile large  | 576px  | 767px    |
| tablet        | 768px  | 991px    |
| laptop        | 992px  | 1199px   |
| desktop       | 1200px | infinito |

### Colección de tamaños de textos con su velocidad de crecimiento en cada breakpoint

Definimos todos los tamaños de texto y su velocidad de crecimiento que tendrán en cada breakpoint. Para ello crearemos una tabla similar a la siguiente:

|Tamaño | mobile small | mobile large | tablet | desktop | desktop large|
|-------|:------------:|--------------|--------|---------|--------------|
|h1     |  29px/32px   |              |        |         |              |
|h2     |  24px/28px   |              |        |         |              |
|h3     |  20px/24px   |              |        |         |              |
|h4     |  16px/20px   |              |        |         |              |
|h5     |  14px/20px   |              |        |         |              |
|h6     |  12px/16px   |              |        |         |              |
|large  |  16px/20px   |              |        |         |              |
|base   |  14px/20px   |              |        |         |              |
|small  |  12px/16px   |              |        |         |              |
|tiny   |  10px/12px   |              |        |         |              |

Los tamaños `large`, `base`, `small` y `tiny` se usarán para el texto común y el resto para títulos.

Hay que tener en cuenta que, dependiendo de la anchura a la que se muestra un texto con un mismo tamaño la altura de línea necesaria puede ser diferente.

Es habitual comenzar definiendo una escala de fuentes para poder sacar el contenido de la tabla. Para ello podemos usar https://www.modularscale.com/

#### Escala de espacios

TODO

## Estilos globales

Los estilos globales se dividen en 3 categorías:
* **reset**: se encargan de neutralizar los estilos por defecto de los diferentes navegadores.
* **reboot**: se establecen unos estilos globales base que complementan el reset.
* **fuentes**: se registran las diferentes fuentes de la web.

## Estructura de carpetas

ITCSS nos ayuda a definir una arquitectura para el código CSS fácil de mantener y evolucionar y ayudando a evitar problemas relacionados con la herencia de estilos.

La estructura de carpetas para los estilos es:

* **01_tools**: Mixins y funciones comunes para todo el proyecto.
* **02_settings**: Contiene las variables globales, configuración, colores, etc. común para todo el proyecto. 
* **03_generic**: Los estilos globales para unificar la visualización en navegadores e impresoras y declaración de fuentes.
* **04_elements**: Estilos a etiquetas de HTML.
* **05_components**: Patrones de layout estructurales repetitivos, sin ningún aspecto visual y piezas de la interfaz de usuario reconocibles, con estilos visuales propios. También llamados componentes.
* **06_themes**: Estilos para cambiar el aspecto de componentes y elementos en base a la clase del theme.
* **07_specifics**: Estilos específicos de partes de una página que aún no se ha encontrado el patrón para convertirlo en componente. 
* **08_utilities**: Clases totalmente especializadas que aportan estilos que sobreescriben cualquiera de los anteriores si fuera necesario. Cada clase contiene un único estilo, a diferencia de los componentes.

Recursos:
* [Manage large CSS projects with ITCSS](http://www.creativebloq.com/web-design/manage-large-css-projects-itcss-101517528)
* [Post de xfive](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/)

## Patrones de nombres de clases

Para ayudar a identificar el objetivo de una clase concreta, en algunas de ellas seguiremos el siguiente patrón:

* `theme-light`: Las clases de **themes** comienzas por `theme-`
* `s-some`: Las clases de estilos **específicos** comienzas por `s-`
* `is-active`: Las clases que especifiquen un estado o condición de un componente o elemento comienzan por `is-` o `has-`.
* `js-carousel`: No son clases que den ningún estilo, son nombres usados para referenciar elementos del DOM desde código javascript.

Recursos:
* [More transparent UI code with namespaces](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)

### Notación BEM

Nos da patrones y reglas para nombrar los estilos de nuestros componentes de interfaz. Nos proveen de estilos fáciles de saber cuándo y cómo deben ser usados, que evitan conflictos de nombres y nos permiten definir variantes de los componentes.

Recursos:
* [BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
* [BEMIT: Taking the BEM Naming convention a step further](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)

### Patrón de nombres

Cuando vamos a crear una escala de espacio o tipografía unos nombres que podemos usar son, del más pequeño al más grande:

* tiny
* mini
* (xsmall)
* small
* regular
* medium
* large
* (xlarge)
* huge

Para una escala de colores, la escala es:
* darkest
* darker
* dark
* base
* light
* lighter
* lightest



# Estrategias de creación de clases

Existen dos variantes, principalmente, a la hora de pensar en la estrategia de clases a crear para usarlas en el HTML:

* component first
* utility first
* utility first + components

Hay un artículo de Adam Wathan que habla sobre [las clases de utilidad y la "separation of concerns"](https://adamwathan.me/css-utility-classes-and-separation-of-concerns/) y explica, en la fase 5, la estrategia recomendada.

## Buenas prácticas

Te en cuenta los siguientes puntos cuando vayas a maquetar:

* Usa la base de "reset" y "reboot" en cada proyecto para normalizar los estilos de todos los navegadores.

* Por defecto usa REM's para todo excepto para casos puntuales donde no tenga sentido un crecimiento basado en el tamaño fuente del navegador como: border radius, breakpoins, shadows, etc.

* Comienza maquetando la versión móvil para que los estilos bases sean esos. Luego sigue para el resto de breakpoints añadiendo media queries.

* Para iconos en línea, si no está contenido en flexbox, añade `line-height: 0` a un elemento en línea cuando no quieras que la altura de línea le afecte y tenga un tamaño mayor del esperado.

* Define el tamaño base del texto a la etiqueta `<body />`

* Reserva siempre el hueco de cada imagen definiendo su `width` y `height` a fin de evitar _reflows_ del navegador que merman el rendimiento.


# Blogs de referencia
* [Harry Roberts (CSS wizardry)](https://csswizardry.com/)

# Recursos formativos
## Iniciación

* Introducción a HTML y CSS:
  * [Cursos interactivos en Code Cademy](https://www.codecademy.com/learn/all)
  * [Curso interactivo de introducción a HTML y CSS en Udacity](https://www.udacity.com/course/intro-to-html-and-css--ud304)
  * [Curso interactivo de introducción a HTML/CSS en KhanAcademy](https://www.khanacademy.org/computing/computer-programming/html-css)
  * http://librosweb.es/libro/xhtml/ 
  * http://librosweb.es/libro/css/
  * http://librosweb.es/libro/css_avanzado/

* Entender el modelo de cajas, layout (display, position, float), especificad, herencia y cascada:
  * http://learnlayout.com/
  * http://adamschwartz.co/magic-of-css/
  * http://lifeonlars.com/coding/css-xhtml/ten-things-you-should-know-about-css/
  * http://learn.shayhowe.com/html-css/

## Avanzado
  * [Curso interactivo sobre fundamentos de diseño web responsivo](https://www.udacity.com/course/responsive-web-design-fundamentals--ud893)
  * [Blog de Harry Roberts](http://csswizardry.com/)
  * [codepen.io](http://codepen.io/): Code snippets para aprender, analizar y jugar: 
  * [caniuse.com](http://caniuse.com/): Conocer la compatibilidad de características en los diferentes navegadores web: 


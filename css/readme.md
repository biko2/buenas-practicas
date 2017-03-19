# Buenas prácticas con CSS

## Atomic design

Nos ayuda a escribir código modular e ir creando, a partir de pequeñas piezas, otras más complejas.

Recursos:
* [Atomic Design por Brand Frost](http://bradfrost.com/blog/post/atomic-web-design/)

## ITCSS

Nos ayuda a definir una arquitectura para el código CSS fácil de mantener y evolucionar y ayudando a evitar problemas relacionados con la herencia de estilos.

La estructura de carpetas para los estilos es:

* **01_settings**: Contiene las variables globales, configuración, colores, etc. común para todo el proyecto. 
* **02_tools**: Mixins y funciones comunes para todo el proyecto.
* **03_generic**: Estilos para unificar la visualización en navegadores (por ejemplo normilize.css) e impresoras, declaración de fuentes, reglas globales para box-sizing, etc.
* **04_elements**: Estilos a etiquetas de HTML.
* **05_objects**: Patrones de layout estructurales repetitivos, sin ningún aspecto visual, por ejemplo, el [media object](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/).
* **06_components**: Piezas de la interfaz de usuario reconocibles, con estilos visuales propios. También llamados componentes.
* **07_themes**: Estilos para cambiar el aspecto de componentes y elementos en base a la clase del theme.
* **08_specifics**: Estilos específicos de partes de una página que aún no se ha encontrado el patrón para convertirlo en componente. 
* **09_utilities**: Clases totalmente especializadas que aportan estilos que sobreescriben cualquiera de los anteriores si fuera necesario. Cada clase contiene un único estilo, a diferencia de los componentes.

Recursos:
* [Manage large CSS projects with ITCSS](http://www.creativebloq.com/web-design/manage-large-css-projects-itcss-101517528)
* [Post de xfive](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/)

### Patrones de nombres

Para ayudar a identificar el objetivo de una clase concreta, seguiremos el siguiente patrón:

* `c-breadcrum`: Los clases de **componentes** comienzan por `c-`
* `u-margin-top`: Las clases de **utilidad** comienzan por `u-`
* `o-media`: Las clases de **objetos** comienzan por `o-`
* `t-light`: Las clases de **themes** comienzas por `t-`
* `s-some`: Las clases de estilos **específicos** comienzas por `s-`
* `is-active`: Las clases que especifiquen un estado o condición de un componente o elemento comienzan por `is-` o `has-`.
* `js-carousel`: No son clases que den ningún estilo, son nombres usados para referenciar elementos del DOM desde código javascript.

Recursos:
* [More transparent UI code with namespaces](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)

## Notación BEM

Nos da patrones y reglas para nombrar los estilos de nuestros componentes de interfaz. Nos proveen de estilos fáciles de saber cuándo y cómo deben ser usados, que evitan conflictos de nombres y nos permiten definir variantes de los componentes.

Recursos:
* [BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
* [BEMIT: Taking the BEM Naming convention a step further](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)

# Blogs de referencia
* [Harry Roberts (CSS wizardry)](https://csswizardry.com/)


# Recursos formativos

## Iniciación

* Introducción a HTML y CSS:
  * http://librosweb.es/libro/xhtml/ 
  * http://librosweb.es/libro/css/
  * http://librosweb.es/libro/css_avanzado/

* Entender el modelo de cajas, layout (display, position, float), especificad, herencia y cascada:
  * http://learnlayout.com/
  * http://adamschwartz.co/magic-of-css/
  * http://lifeonlars.com/coding/css-xhtml/ten-things-you-should-know-about-css/
  * http://learn.shayhowe.com/html-css/

## Avanzado
  * Blog de Harry Roberts: http://csswizardry.com/
  * Code snippets para aprender, analizar y jugar: http://codepen.io/
  * Conocer la compatibilidad de características en los diferentes navegadores web: http://caniuse.com/
  

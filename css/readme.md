# Buenas prácticas con CSS

## Atomic design

Nos ayuda a escribir código modular e ir creando, a partir de pequeñas piezas, otras más complejas.

Recursos:
* [Atomic Design por Brand Frost](http://bradfrost.com/blog/post/atomic-web-design/)

## Notación BEM

Nos da patrones y reglas para nombrar los estilos de nuestros componentes de interfaz. Estilos fáciles de saber cuándo y cómo deben ser usados, que evitan conflictos de nombres y nos permiten definir variantes de nuestros componentes. 

Un artículo que explica el motivo de los [namespace en los nombres de estilos](https://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/) y otro que explica [cómo ir un paso más allá](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/).

## ITCSS

Nos ayuda a construir una arquitectura del código CSS lo más fácilmente mantenible y evolucionable. 

La organización base en carpetas es:

* **01_settings**: Variables globales, configuración, colores, etc.
* **02_tools**: Mixins y funciones helpers
* **03_generic**: Estilos para unificar visualización en navegadores e impresoras y declaración de fuentes.
* **04_elements**: Estilos a etiquetas de html
* **05_objects**: Patrones de layouts sin aspecto visual
* **06_components**: Componentes de interfaz
* **07_themes**: Estilos para cambiar el aspecto de componentes y elementos en base a la clase del theme.
* **08_pages**: Estilos específicos de una página
* **09_utilities**: Estilos de ayuda

### Patrones de nombres

Para ayudar a identificar el objetivo de una clase concreta, seguiremos el siguiente patrón:

* `c-breadcrum`: Los clases de **componentes** comienzan por `c-`
* `u-margin-top`: Las clases de **utilidad** comienzan por `u-`
* `o-media`: Las clases de **objetos** comienzan por `o-`


Recursos:
* [Post de xfive](https://www.xfive.co/blog/itcss-scalable-maintainable-css-architecture/)
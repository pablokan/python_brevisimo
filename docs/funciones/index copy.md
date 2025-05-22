# Funciones

**Buenas prácticas!** 

Las funciones permiten modularizar un programa, dividiéndolo en porciones más comprensibles y simples de mantener. Son una herramienta imprescindible para la programación limpia!

Las funciones en Python se pueden considerar de dos tipos:  

1. **Subprogramas** o **procedimientos**: Son fragmentos de código que realizan una tarea sin necesidad de devolver ningún dato. Suelen ser de un solo uso y su finalidad es dividir el programa en componentes más pequeños y más fácilmente depurables y legibles. Ejemplos: función de carga, función de salida, hacer una línea separadora, etc.

2. **Funciones propiamente dichas**: Son fragmentos de código que normalmente reciben y devuelven datos y que además se pueden reutilizar. Aquí dividiremos entre funciones con **parametrización básica** y funciones con **parametrización avanzada**. 

De cualquier manera, en términos prácticos, vamos a dividir el tratamiento entre **funciones básicas** (procedimientos y funciones con parámetros simples) y **funciones con parametrización avanzada** (posicionales, clave-valor, tuplas, diccionarios).

** IMPORTANTE ** -->
Las funciones deben ser **independientes**: todo objeto usado dentro de ellas tiene que ser un **parámetro** o una **variable local** (aquellas que solamente existen al interior de la función). **NO** hay que usar **variables globales** (las del programa principal) dentro del bloque de la función. Esta independencia nos permitirá la reutilización de las funciones no solamente en el mismo programa sino también en otros.

### Vamos a verlas en detalle:

## Funciones [básicas](func_base.md) y [parametrización avanzada](func_av.md)

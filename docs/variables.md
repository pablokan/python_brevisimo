# Variables

Una variable es el nombre de un espacio de almacenamiento de un dato. Dicho dato es un valor que será de un tipo de dato específico.

**Para ir clarificando: **

Si decimos que la variable **nombre** contiene la string **"Ana"**, pues entonces dicha variable será de tipo **str** (cadena de caracteres o string).
```py
# Se asigna el valor a la variable con el signo igual.
nombre = "Ana"
```
Si luego decimos que la variable **edad** contiene el número **33**, el tipo de datos será **int**.
```py
edad = 33
```
Si finalmente decimos que tenemos una variable **altura**, cuyo valor es **1.65**, aquí el tipo de dato será real (**float**).
```py
altura = 1.65
```
Ahora podríamos juntar todo esto en una sola frase, mezclando strings literales (palabras o frases o cualquier conjunto de caracteres) con variables. Copien y peguen lo siguiente en un nuevo programa (recuerden: **Ctrl-N** para crear un nuevo programa, **Ctrl-S** para grabar y ponerle nombre -NO olviden que el nombre debe contener SOLAMENTE letras del alfabeto base, sin letras acentuadas ni eñe, más el caracter guión bajo y DEBE terminar con **.py**-)
```py
nombre = "Ana"
edad = 33
altura = 1.65
print(nombre, "tiene", edad, "años y mide", altura)
```
Al ejecutar, deberíamos ver como salida del programa lo siguiente:

**Ana tiene 33 años y mide 1.65**

Como sabe Python cuando poner **Ana** y cuando poner **tiene**?

Cuando encuentra una palabra que NO está entre comillas, entiende que es una variable y muestra entonces su valor contenido. En cambio, cuando encuentra dentro del **print()**, letras, palabras o frases o cualquier conjunto de caracteres entre comillas, muestra su contenido literal.

## Cómo se puede llamar una variable?

Debe comenzar con una letra (de preferencia minúscula -en Python, se distinguen las mayúsculas de las minúsculas-).

Luego puede haber otras letras, tanto minúsculas como mayúsculas y también números y guiones bajos.

Ejemplos de nombres de variables:

**nombre** (nombre de una persona, empresa, o lo que sea)  
**fecha_nacimiento** (Fecha de nacimiento en nomenclatura **snake case**)  
**fechaNacimiento** (Fecha de nacimiento en nomenclatura **camel case**)  
**sueldoBasico**  
**periodo2020_2022**

## Carga de valores desde el teclado
Las variables pueden recibir un valor por asignación directa como acabamos de ver:

**nombre = "Ana"**

o bien desde el teclado. 

Para ello, se utiliza la función **input()**, que nos permite colocar entre sus paréntesis un mensaje que le aparecerá al usuario para indicarle lo que se pretende que escriba.
```py
# El mensaje entre comillas sale por la consola como si fuera un print()
# y el cursor queda esperando que el usuario escriba y finalice con Enter.
# Luego de eso, lo ingresado queda asignado a la variable.
nombre = input("Ingrese su nombre: ")
print("Hola", nombre)
```









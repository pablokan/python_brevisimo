# Funciones básicas

```py
def raya():
    print("----------------------------")
```
Una función debe declararse con la palabra reservada **def**, luego un nombre (mismo criterio de nombrado que las [variables](../variables.md#como-se-puede-llamar-una-variable)), y luego el bloque de código que pertenece a la función son todas las líneas que estén indentadas (con sangría).

```py
def raya():
    print("----------------------------")

print("Ahora viene una raya:")
raya()
print("Y ahora otra raya más:")
raya()
```
Una función que no retorna valor (un procedimiento) se ejecuta poniendo su nombre y sus paréntesis. Puede ejecutarse más de una vez.

### Parámetros
Si se quiere customizar la función se debe hacerlo definiendo **parámetros**, que son variables que se colocan entre los paréntesis en la definición de la función. Y se reemplazan por **argumentos** enviados durante la ejecución. Veamos un ejemplo:

Supongamos que nos parece que nuestra función raya es muy limitada (tiene una cantidad fija de caracteres y además son solamente guiones). La vamos a hacer más flexible:

Primero, vamos a hacer una modificación para que luego se vea bien el efecto de los parámetros
```py
def raya():
    for x in range(20): 
        print("-", end="")

raya()
```
Hacemos un bucle de 20 vueltas, por tanto mostraremos 20 guiones (el **end=""** es para que no salte de línea)

```py
def raya(cantidad, caracter): # parámetros: cantidad, caracter
    for x in range(cantidad): 
        print(caracter, end="")
    print()

raya(20, "-") # argumentos: 20, "-"
raya(10, "+") # argumentos: 10, "+"
raya(30, "$") # argumentos: 30, "$"

# Salida:
""" Las 3 comillas son otra forma de comentario para multilíneas
--------------------
++++++++++
$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
"""
```
Como vemos, al enviar argumentos diferentes, la raya varía su largo y su caracter. Estos parámetros se denominan **posicionales** y cuando usamos la función, los valores que enviamos se llaman **argumentos**, son **obligatorios** y ocupan el lugar de los parámetros en la ejecución.

## Retorno
Ahora veremos el retorno de datos desde la función.

Hasta ahora, estamos usando la función como un subprograma, veamos otro ejemplo y luego lo convertimos en una función propiamente dicha.

```py
def saludo(nombre):
    print("Hola", nombre)

saludo("Ana")
```
Tenemos aquí una función tipo procedimiento, que tiene un parámetro **nombre** y cuando recibe el argumento **"Ana"** produce el saludo: **Hola Ana**. Vemos como la llamada a la función, cuando ponemos el nombre y se ejecuta, es similar al ejemplo anterior de la raya.

Ahora haremos la modificación de sustituir la función **print()** por la instrucción **return**.

```py
def saludo(nombre):
    return "Hola " + nombre # el signo + entre dos strings las concatena

print(saludo("Ana"))
```
Vemos que aquí, al agregar el retorno, el saludo vuelve en el nombre de la función, es por eso que podemos y tenemos que hacer el print() para poder obtener la salida deseada.

Otro ejemplo:
```py
def doble(numero):
    print(numero*2)

doble(3)
```
Si en cambio, queremos que el valor doble del argumento enviado sea retornado, debemos printear la función:
```py
def doble(numero):
    return numero*2

print(doble(3))
```

# Funciones básicas

```py
def raya():
    print("----------------------------")
```

Una función debe declararse con la palabra reservada **def**, luego un nombre (mismo criterio de nombrado que las [variables](../variables.md#como-se-puede-llamar-una-variable)), y luego el bloque de código que pertenece a la función (son todas las líneas que estén indentadas).

```py
# función como procedimiento
def raya():
    print("----------------------------")

print("Ahora viene una raya:")
raya()
print("Y ahora otra raya más:")
raya()
```

Una función que no retorna valor (un procedimiento) se ejecuta (se dice también que se "llama" a la función, en inglés, que se hace un "call") poniendo su nombre y sus paréntesis. Puede ejecutarse más de una vez.

---

```py
# función propiamente dicha
def bar():
    return 'valor que devuelve'
```

Una función que tiene **return** devuelve el o los valores que tiene a continuación, y se la llama para ser asignada (a una variable) o bien operada (como si ya fuera una variable) o directamente printeada:

```py
print (bar()) # muestra 'valor que devuelve'
valor_devuelto = bar() # asigna la string a la variable

```

## **Parámetros**

Si se quiere flexibilizar el comportamiento de la función y de esa manera darle mayor utilidad, se debe hacerlo definiendo **parámetros**, que son variables que se colocan entre los paréntesis en la definición de la función. Dichos parámetros serán reemplazan por **argumentos** enviados durante la ejecución. Veamos un ejemplo:

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

raya(20, "-") # argumentos: 20, "-" # reemplazan a los parámetros 
raya(10, "+") # argumentos: 10, "+" # 10 reemplaza a cantidad y + a caracter
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

Si en cambio, queremos que el valor doble del argumento enviado sea retornado, debemos printear la función (o bien asignarla o también operarla):

```py
def doble(numero):
    return numero*2

print(doble(3))
print(f'El doble del doble es {doble(4) * 2}')
dobleDe9 = doble(9)
print(dobleDe9)
```

---
Los parámetros posicionales obligatorios (los más básicos que estamos viendo hasta aquí), deben respetar **cantidad**, **orden** y **tipo de dato** a la hora de enviarle los argumentos a la función, independientemente de que le enviemos variables, literales o incluso expresiones.

```py
def operar(operacion, n1, n2): # 3 parámetros: string, número, número
    if operacion == 'suma':
        resultado = n1 + n2 # resultado es una variable local
    elif operacion == 'resta':
        resultado = n1 - n2 
    else:
        resultado = f'Operación desconocida "{operacion}"'
    return resultado

print(resultado) # error!!! esta variable solamente existe dentro de la función
print('Resultado de la suma de 4+5: ', end='')
print(operar("suma", 4, 5)) # mismo orden que los parámetros
a = 2
b = 3
print(f'{a=} y {b=}')
print('Resultado de la resta:', operar("resta", a, b))
salida = operar('mutiplicación', 10, 4) # asigno el retorno a una variable
print(salida)
print(f'a * 3 + 10 (a vale 2): {operar('suma', a*3, 10)}')
otra_salida = operar(7, 5, 'resta') # error!!! orden incorrecto
print(operar('suma', 1, 2, 3)) # error!!! cantidad incorrecta de argumentos
```

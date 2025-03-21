# If

Además del flujo de ejecución secuencial (que significa que se va ejecutando una línea de programa de arriba hacia abajo, una tras otra), en la programación estructurada tenemos flujo alternativo y flujo repetitivo.

En Python la alternativa se maneja con la instrucción **if** y sus instrucciones complementarios **elif** y **else**.

La alternativa significa que **no** necesariamente se ejecutan todas las líneas del programa. Puede ocurrir que se "salteen" líneas dependiendo de una **condición**.

```py
n = 1
if n > 2: # condición: expresión con un valor de verdad 
    print('la siguiente línea se ejecuta si la condición es verdadera')
    print("es mayor que 2") # en este caso, esto NO se ejecuta
else: # si no se cumple la condición del if
    print("no es mayor que 2")
print('fin') # esta línea se ejecuta siempre porque estoy "fuera" del if
```

Observemos también, que la o las líneas que dependen del **if** o del **else** están indentadas, tienen una sangría, no están en la misma columna sino corridas varios espacios hacia la derecha (la cantidad de espacios no importa pero siempre tiene que ser la misma en un programa).

### Operadores de Comparación y Lógicos
Para que una condición tenga valor de verdad usaremos operadores de comparación y lógicos:

**==** (igual), **!=** (distinto), **>**, **<**, **>=**, **<=** y operadores lógicos (**and**, **or**, **not**)

```py
edad = 77
if edad < 12: # el único if
    print("es un niño")
elif 13 <= edad <= 19: # esto es equivalente a edad >= 13 and edad <= 19
    print("es un adolescente")
elif 20 <= edad <= 70: # puede haber más de un elif
    print("es un adulto")
else: # el único else para toda opción no contemplada anteriormente
    print("es un adulto mayor")
```

Aprovechamos para introducir el tipo de dato lógico o booleano. Las variables booleanas solamente pueden contener dos valores True (verdadero) False (falso). Repasamos los tipos de datos con estas variables:

```py
nombre = 'Pablo' # string (cadena de caracteres) -> str
edad = 59 # integer (entero) -> int
altura = 1.73 # floating point (real) -> float
es_alto = False # boolean (lógico) -> bool
es_viejo = True # boolean (lógico) -> bool
```

Las variables booleanas tienen valor de verdad en si mismas, no es necesario compararlas:

```py
if es_viejo: # esto es lo mismo que poner: if es_viejo == True
    print(nombre, 'es viejo')

if edad >= 18 and not es_alto:
    print('Es mayor de edad y es bajo')
```

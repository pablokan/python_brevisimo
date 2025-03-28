# Bucle while
---
Para la sintaxis del **while**, hay que tener en cuenta estos requisitos:  

1. Luego de la palabra reservada **while**, debe haber una expresión que tenga un valor de verdad. El bucle se repetirá mientras dicha expresión sea verdadera.

2. Al final de la línea tienen que poner el signo de dos puntos (:)  

3. El bloque de código (una o más líneas que dependen del while) DEBE estar indentado

Con los ejemplos siguientes lo comenzaremos a entender:

## Recorrido que depende de la respuesta del usuario
---
Ejemplo:
``` py
respuesta = "si" # esto asegura que va a ingresar
while respuesta == "si": # mientras la variable respuesta siga valiendo "si"
    nombre = input("Ingrese su nombre: ")
    print("Hola", nombre)
    # La siguiente pregunta sirve para saber si quiere continuar o no
    respuesta = input("Quiere saludar a más personas? (si/no): ")
print('Adiós! (Salió del while porque dejó de contestar "si")')
```

Lo que está **adentro** del while (se dice así cuando una o varias líneas del programa están **indentadas**, es decir, con una especie de sangría: NO comienzan justo debajo del while, sino algunas columnas más a la derecha).

Entonces, lo que depende del while (lo que está adentro), se ejecutará MIENTRAS la condición sea verdadera (una cantidad indefinida de veces, porque depende del momento en el que el usuario decide volver falsa la expresión). 

---

## Recorrido que depende de una condición sin interacción
---
Ejemplo:
``` py
n = 0
while n < 5:
    print("dentro del while")
    n = n + 1  # contador
    print(n)
    if n == 3:
        print("llegó el 3!!!!")
print("afuera del while porque dejó de cumplirse la condición")
```
Aquí este **while** está funcionando como una imitación de un **for**, la diferencia es que el **for** incrementa la variable de recorrido automáticamente y en el **while** la tenemos que incrementar "a mano" con un contador.

## Contadores y Acumuladores

``` py
contador_envios = 0
acumulador_cajas = 0

respuesta = 's'
while respuesta == 's':
    contador_envios = contador_envios + 1
    print(f'Envío #{contador_envios}')
    cantidad_cajas = input('Cuántas cajas llegaron? ')
    cantidad_cajas = int(cantidad_cajas)
    acumulador_cajas = acumulador_cajas + cantidad_cajas
    respuesta = input('LLegaron más cajas? (s/n): ')

print(f'En {contador_envios} envíos fueron recibidas {acumulador_cajas} cajas')
```

---

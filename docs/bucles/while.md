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
respuesta = "si"
while respuesta == "si":
    nombre = input("Ingrese su nombre: ")
    print("Hola", nombre)
    respuesta = input("Quiere saludar a más personas? (si/no): ")
```

Lo que está **adentro** del while (se dice así cuando una o varias líneas del programa están **indentadas**, es decir, con una especie de sangría: NO comienzan justo debajo del while, sino algunas columnas más a la derecha).

Entonces, lo que depende del while (lo que está adentro), se ejecutará MIENTRAS la condición sea verdadera (una cantidad indefinida de veces, porque depende del momento en el que el usuario decide volver falsa la expresión). 

---

## Recorrido que depende de una condición sin interacción
---
Ejemplo:
``` py
n = 5
while n < 10:
    print("dentro del while")
    n = n + 1  # contador
    if i == 5:
        print("llegó el 5!!!!")
print(n)
```
---

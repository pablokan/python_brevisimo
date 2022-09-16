# Bucle for

---
## Variante de recorrido por índice
Ejemplo 1:
``` py
for i in range(3):
    print("hola")
```
**hola  
hola  
hola
**

Este ejemplo es un proceso repetitivo que se mueve en un rango 3. 
Qué significa eso? que lo que está **adentro** del for (se dice así cuando una o varias líneas del programa están **indentadas**, es decir, con una especie de sangría: NO comienzan justo debajo del for, sino algunas columnas más a la derecha).

Entonces, lo que depende del for (lo que está adentro), se ejecutará según lo que se defina allí, en este primer caso, la repetición del print("hola"). 

El **range(3)** está diciendo que dicha repetición se hará 3 veces.
La variable de control o de recorrido, en este ejemplo la variable i, tomará los valores 0, 1 y 2, porque el valor de **stop**, el número 3, indica cuando el bucle debe detenerse.

---

Ejemplo 2:
``` py
for numero in range(5):
    print(numero)
```
**0  
1  
2  
3  
4  
**

En este segundo caso, habrá 5 iteraciones, que a diferencia del **Ejemplo 1** no serán repeticiones estrictas, en cambio, el valor de la variable **numero** se irá incrementando en cada vuelta del **for**.

---
En ambos ejemplos, el **range()** recibe un solo valor (**stop**), y en estos casos, comienza desde **0 (cero)** y el bucle da tantas vueltas como especifica el dicho stop, es decir, llega hasta el **valor menos 1**.  
En nuestro **Ejemplo 2**, como el rango es **5**, el bucle se ejecuta **5 veces** y, al comenzar desde **0** el último valor no es 5, sino **4**.


## Variante de recorrido por elemento







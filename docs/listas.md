# Listas

Las listas (como otros iterables que tiene Python), son variables de almacenamiento múltiple, es decir, que sirven para guardar varios datos simultáneamente.

Se pueden recorrer fácilmente con el [for](bucles/for.md)
``` py
unaLista = ["dos", "uno", "tres"]
#Se llevan bien con la instrucción de bucle for

print("Recorrido por posición en la lista (con rango)")
# len es una función que devuelve la cantidad de elementos de la lista
for indice in range(len(unaLista)): 
    print(unaLista[indice])
print("-----------------------------------------------")

print("Recorrido por elemento")
for elemento in unaLista:
    print(elemento)
print("-----------------------------------------------")

print("Recorrido por elemento con enumeración")
# Equivalente a los dos anteriores juntos, 
# más la posibilidad de empezar a contar desde 1
# o cualquier otro valor entero
for i, e in enumerate(unaLista, start=1):
    print(i, e)
print("-----------------------------------------------")
```

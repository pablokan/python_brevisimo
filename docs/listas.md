# Listas

Las listas (como otros iterables que tiene Python), son variables de almacenamiento múltiple, es decir, que sirven para guardar varios datos simultáneamente.

Tienen una capacidad de almacenamiento dinámica (no se requiere ni se necesita un tamaño predefinido).
Además puede contener valores de cualquier tipo de dato simultáneamente:

```py
cambalache = [9, "jota", False, "🤖👽🐍", -8.2]

print(cambalache[1])  # muestra el segundo elemento (el primero está en posición cero)

print(cambalache)  # muestra toda la lista con los corchetes

print("Cantidad de elementos de la lista cambalache: ", len(cambalache))  # len: longitud

# Ahora declaro, asigno y reemplazo:
otraLista = []  # lista vacía - Sirve como declaración

otraLista[0] = 111  # IndexError: list assignment index out of range
# No funcionó porque la posición cero aún no existe

otraLista = ["q"] # asigno
print(otraLista)

otraLista[0] = 111  # reemplazo (ahora funciona porque la posición cero ya tenía valor)
print(otraLista)


# Y finalmente agrego, inserto, saco y borro 
otraListaMas = []
otraListaMas.append("primero") # agrego
print(otraListaMas)

otraListaMas.append("segundo") # agrego otro valor al fondo
print(otraListaMas)

otraListaMas.insert(1, "al medio") # inserto en la posición 1
print(otraListaMas)

otraListaMas[1] = "reemplazo al que estaba al medio"
print(otraListaMas)

otraListaMas.pop(1)  # elimina por posición, por defecto el último
print(otraListaMas)

otraListaMas.remove("primero")  # elimina por valor
print(otraListaMas)

otraListaMas = [100, 200, 300, 400, 500]
del otraListaMas[1:3] # borra por índice o por slice
print(otraListaMas)
```

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

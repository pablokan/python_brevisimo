# Listas

---

Las listas (como otros iterables que tiene Python), son variables de almacenamiento múltiple, es decir, que sirven para guardar varios datos simultáneamente.

Tienen una capacidad de almacenamiento dinámica (no se requiere ni se necesita un tamaño predefinido).
Además puede contener valores de cualquier tipo de dato simultáneamente:

```py
cambalache = [9, "jota", False, "🤖👽🐍", -8.2]

print(cambalache[1])  # muestra el segundo elemento (el primero está en posición cero)

print(cambalache)  # muestra toda la lista con los corchetes

# len es una función que devuelve la cantidad de elementos de la lista
print("Cantidad de elementos de la lista cambalache: ", len(cambalache))  
```

Ahora declaro, asigno y reemplazo:

```py
otra_lista = []  # lista vacía - Sirve como declaración

otra_lista[0] = 111  # IndexError: list assignment index out of range
# No funcionó porque la posición cero aún no existe

otra_lista = ["q"] # asigno
print(otra_lista)

otra_lista[0] = 111  # reemplazo (ahora funciona porque la posición cero ya tenía valor)
print(otra_lista)
```

Y finalmente agrego, inserto, saco y borro

```py
otra_lista_ mas = []
otra_lista_ mas.append("primero") # agrego
print(otra_lista_ mas)

otra_lista_ mas.append("segundo") # agrego otro valor al fondo
print(otra_lista_ mas)

otra_lista_ mas.insert(1, "al medio") # inserto en la posición 1
print(otra_lista_ mas)

otra_lista_ mas[1] = "reemplazo al que estaba al medio"
print(otra_lista_ mas)

otra_lista_ mas.pop(1)  # elimina por posición, por defecto el último
print(otra_lista_ mas)

otra_lista_ mas.remove("primero")  # elimina por valor
print(otra_lista_ mas)

otra_lista_ mas = [100, 200, 300, 400, 500]
del otra_lista_ mas[1:3] # borra por índice o por slice
print(otra_lista_ mas)
```

Se pueden recorrer fácilmente con el [for](bucles/for.md)

``` py
muebles = ["mesa", "silla", "banquito"]
#Se llevan bien con la instrucción de bucle for

print("Recorrido por posición en la lista (con rango)")
for indice in range(len(muebles)): 
    print(muebles[indice])
print("-----------------------------------------------")

print("Recorrido por elemento")
for mueble in muebles:
    print(mueble)
print("-----------------------------------------------")

print("Recorrido por elemento con enumeración")
# Equivalente a los dos anteriores juntos, 
# más la posibilidad de empezar a contar desde 1
# o cualquier otro valor entero
for indice, elemento in enumerate(muebles, start=1):
    print(indice, elemento)
print("-----------------------------------------------")
```

Carga de lista con iteración

``` py
print('Carga de elementos dentro de un for')
nombres = []
for i in range(5):
    nombre = input("Ingrese un nombre: ") # lo pisa en cada vuelta ...
    nombres.append(nombre) # ... pero lo guarda en la lista
print(nombres)
```

Listas pararelas

``` py
nombres = ["Juan", "Ana", "Luis"]  # misma posición, misma persona
edades = [32, 87, 12]  # entonces Juan tiene 32 años

for i in range(len(nombres)):
    # a mismo índice, datos relacionados
    print(nombres[i], 'tiene', edades[i], 'años')
```

Listas anidadas

``` py
personas = [["Juan", 32], ["Ana", 87], ["Luis", 12]]  # equivalente a paralelas
for persona in personas: # recorro por elemento
    print(persona[0], 'tiene', persona[1], 'años', end=' | ')
print()

lista_anidada = [
    ['cero-cero', 'cero-uno'],
    ['uno-cero', 'uno-uno'],
    ['dos-cero', 'dos-uno'],
    ['tres-cero', 'tres-uno']
    ]

# for anidados por índice
for x in range(len(lista_anidada)):
    for y in range(len(lista_anidada[x])):
        print(lista_anidada[x][y], end=' | ')
```

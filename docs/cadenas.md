# Cadenas

---

Las cadenas (strings, tipo de dato **str**) son variables o constantes (literales) muy potentes.

Primero lo más simple, recuerdan cuando en las primeras clases quisimos sumar dos números, por ejemplo 2 y 3, y el resultado en lugar de 5 fue 23?
Eso ocurrió porque, como sabemos, la función **input** toma siempre string y en lugar de sumar, lo que hicimos fue concatenar:

## Concatenar

```py
# concatenación
una_cadena = "primera cadena"
otra_cadena = "segunda cadena"
nueva_cadena = una_cadena + " - " + otra_cadena
print(nueva_cadena)
```

Las strings se pueden pensar como valores comunes (un solo dato) pero también pueden ser tratadas como listas.

Por lo tanto, al igual que las listas, se pueden recorrer fácilmente con el [for](bucles/for.md)

## Recorrer (como lista)

``` py
nombre = "Juan" # recorremos como si fuera esta lista: ['J', 'u', 'a', 'n']
for i in range(len(nombre)): # por índice
    print(nombre[i])

for letra in nombre: # lo mismo pero por elemento
    print(letra)
```

Pero... a diferencia de las listas, las strings son **inmutables**

``` py
lista = ['m', 'e', 's', 'a']
cadena = "mesa" 
lista[1] = 'i' # Funciona
cadena[1] = 'i' # NO funciona, no se puede modificar parcialmente
```

Como todo objeto en Python, las strings tienen decenas de métodos para operar sobre ellas.

Por ejemplo, el método **find**

## Find (buscar una subcadena)

```py
frase = "Las noches de otoño son frescas"
posicion = frase.find("otoño")  # busca subcadena y devuelve posición
print(posicion)
otra_posicion = frase.find("s no")  # no tiene que ser una palabra
print(otra_posicion)
no_existe = frase.find("no s")  # -1 si no existe
print(no_existe)
print(frase.find("es"))  # encuentra el "es" de "noches"
print(frase.find("es", 10))  # encuentra "es" en "frescas" (por qué?)
```

Otro método muy útil, **split**, que sirve para separar:

## Split (convertir a lista)

```py
Separar una cadena con split
fecha = "3/5/2022"
lista_fecha = fecha.split("/")
print(lista_fecha)  # ['3', '5', '2022']

nombres = "juan---ana---pedro---luisa"
print(nombres.split("---"))  # ['juan', 'ana', 'pedro', 'luisa']

cadena = "algo otro cosa techo"
print(cadena.split()) # por defecto separa por espacio en blanco
"""
```

## Slicing (obtener una subcadena)

```py
# Una operación muy utilizada (aplica también a listas)
frase = "Las noches de otoño son frescas"
print(frase[4:10])  # noches
comienzo = frase[:3]
print(comienzo)  # Las
final = frase[-7:]
final2 = frase[24:]
print(final, final2)  # frescas
print(frase[-1])
```

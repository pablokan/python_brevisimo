# Cadenas

---

Las cadenas (strings, tipo de dato **str**) son variables o constantes (literales) muy potentes.

Primero lo más simple, recuerdan cuando en la primera clase quisimos sumar dos números, por ejemplo 2 y 3, y el resultado en lugar de 5 fue 23?
Eso ocurrió porque, como sabemos, la función **input** toma siempre string y en lugar de sumar, lo que hicimos fue concatenar:

## Concatenar

```py
# concatenación
unaCadena = "primera cadena"
otraCadena = "segunda cadena"
nuevaCadena = unaCadena + " - " + otraCadena
print(nuevaCadena)
```

Las strings se pueden pensar como valores comunes (un solo dato) pero también pueden ser tratadas como listas.

Por lo tanto, al igual que las listas, se pueden recorrer fácilmente con el [for](bucles/for.md)

## Recorrer como lista

``` py
nombre = "Juan"
for i in range(len(nombre)):
    print(nombre[i])
```

Como todo objeto en Python, las strings tienen decenas de métodos para operar sobre ellas.

Por ejemplo, el método **find**

## Buscar una subcadena con **find**

```py
frase = "Las noches de otoño son frescas"
posicion = frase.find("otoño")  # busca subcadena y devuelve posición
print(posicion)
otraPosicion = frase.find("s no")  # no tiene que ser una palabra
print(otraPosicion)
noExiste = frase.find("no s")  # -1 cuando no existe
print(noExiste)
print(frase.find("es"))  # encuentra el "es" de "noches"
print(frase.find("es", 10))  # encuentra el "es" de "frescas" porque empieza a buscar desde mas adelante
```

Otro método muy útil, **split**, que sirve para separar:

## Separar una cadena con **split**

```py
fecha = "3/5/2022"
listaFecha = fecha.split("/")
print(listaFecha)  # ['3', '5', '2022']

nombres = "juan---ana---pedro---luisa"
print(nombres.split("---"))  # ['juan', 'ana', 'pedro', 'luisa']

cadena = "algo otro cosa techo"
print(cadena.split()) # por defecto separa por espacio en blanco
"""
```

Una operación muy utilizada (que aplica también a listas): slicing (rebanar, cortar una porción):

## Slicing (obtener una subcadena)

```py
frase = "Las noches de otoño son frescas"
print(frase[4:10])  # noches
comienzo = frase[:3]
print(comienzo)  # Las
final = frase[-7:]
final2 = frase[24:]
print(final, final2)  # frescas
print(frase[-1])
```

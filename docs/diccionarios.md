# Diccionarios

---

Un diccionario es una variable de almacenamiento múltiple como una [lista](listas.md), una estructura de datos que sirve para guardar varios datos simultáneamente. Pero, a diferencia de una lista, cada elemento es un par **clave: valor**. Por ejemplo, el siguiente diccionario tiene dos elementos, que al igual que en una lista, se separan con una coma.

```py
dicci = {'primero': 1, 'último': 'two'}
# El primer elemento del diccionario es ---> 'primero': 1
# y el segundo es ---> 'último': 'two'

# Subindicación:
# se realiza con la clave en lugar de una posición como hacemos en las listas
print(dicci['último'])  # muestra el valor del segundo elemento

print(dicci)  # muestra toda el diccionario con las llaves

# len, como en listas, devuelve la cantidad de elementos
print("Cantidad de elementos del diccionario dicci: ", len(dicci))  
```

Declarar y asignar:

```py
dicci2 = {}  # diccionario vacío - Sirve como declaración

# Agrego o reemplazo:
dicci2['algo'] = 111  # A diferencia de la lista, esto NO da error

print(dicci2)
```

Borrar y sacar:

```py
dicci3 = {'clave1': 'valor1', 'clave2': 'valor2'}

del(dicci3['clave1']) # elimina

valor = dicci3.pop('clave2')  # saca el elemento y lo asigna
print(dicci3)
print(valor)
```

Tipos de diccionarios. Si bien desde un punto de vista de su estructura todos los diccionarios son iguales, conceptualmente se pueden distinguir dos tipos:


**Homogéneos** (también llamados **colecciones**) que son aquellos cuyos elementos son similares

``` py
remeras = {'lisas': 10, 'rayadas': 5, 'con dibujitos': 3}
```

**Registro**, que son los que tienen elementos complementarios

``` py
persona = {'nombre': 'Ana', 'edad': 22, 'altura': 1.54}
```

Recorridos:

``` py
persona = {'nombre': 'Ana', 'edad': 22}

# Recorrido por claves solas
print('Muestro las claves')
for k in persona: # es lo mismo que poner ---> persona.keys()
    print(k)

print('Muestro los valores')
for v in persona.values(): # Recorrido por valor
    print(v)

print('Recorro y muestro por clave y valor')
for k, v in persona.items(): # Recorrido por item es clave y valor
    print(k, "->", v)

```

En general, las claves que usaremos serán habitualmente strings, pero los valores podrán ser tan complejos como nos haga falta!

``` py
familia = {
    "nombre": "Juan", 
    "nombres_hijos": ["Pedro", "Ana", "José"],
    "nombres_padres": {"Padre": "Juan", "Madre": "Maria"}
}

print(f"El nombre de la madre es {familia["nombres_padres"]["Madre"]}")

print('Nombres de los hijos:')
for hijo in familia["nombres_hijos"]:
    print(hijo)
```

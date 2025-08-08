# **Métodos Mágicos (dunders)**

Los **dunders** son métodos especiales que están disponibles de manera automática en cualquier clase de python.

Los más usuales son:

- __repr__: Para mostrar una representación del objeto útil para el Desarrollador
- __str__: Para una salida legible para el usuario
- __len__: Redefine el uso de la función len (por ejemplo para saber la cantidad de elementos que tiene un atributo lista)
- __add__: Sobrecarga de operador (redefine el comportamiento del signo **+** para operaciones entre objetos)
- __getitem__: Permite acceder a elementos usando la sintaxis de corchetes (mi_lista[0], mi_lista[1], etc.)
  
  Y varios más ...

``` py
class Color:
    def __init__(self, nombre) -> None:
        self.nombre = nombre

    def __add__(self, otro_color): # sobrecarga de operador +
        if self.nombre == 'azul' and otro_color.nombre == 'rojo':
            return Color('violeta')
        else:
            return Color('inexistente')

    def __repr__(self): # salida para programadores
        return f'Clase: {self.__class__.__name__}, Nombre: {self.nombre}'
    
    def __str__(self): # Para el usuario
        return f'Color {self.nombre}'

azul = Color('azul')
rojo = Color('rojo')
amarillo = Color('amarillo')

color_nuevo = azul + rojo
print(color_nuevo)
```

Y otro ejemplo:

``` py
class MiLista:
    def __init__(self):
        self.items = []
    
    def agregar(self, item):
        self.items.append(item)
    
    def __len__(self):
        """Define qué devuelve len(objeto)"""
        return len(self.items)
    
    def __getitem__(self, indice):
        """Permite acceder a elementos usando obj[indice]"""
        return self.items[indice]
    
    def __repr__(self):
        return f"MiLista({self.items})"

# Ejemplo de uso
mi_lista = MiLista()
mi_lista.agregar("manzana")
mi_lista.agregar("banana")
mi_lista.agregar("naranja")

print(f"Mi lista: {mi_lista}")
print(f"Longitud: {len(mi_lista)}")  # Usa __len__
print(f"Primer elemento: {mi_lista[0]}")  # Usa __getitem__
print(f"Segundo elemento: {mi_lista[1]}")  # Usa __getitem__
print(f"Último elemento: {mi_lista[-1]}")  # Usa __getitem__

# También funciona con slicing
print(f"Primeros dos: {mi_lista[0:2]}")  # Usa __getitem__ con slice
```

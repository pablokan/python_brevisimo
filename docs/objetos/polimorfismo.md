# **Polimorfismo**

El polimorfismo es la característica de la OOP que se refiere a los métodos de los objetos independientemente de las diferencias que tengan. Si los métodos se llaman igual, no importan las diferencias entre las clases, los puedo usar sin preocuparme de ellas.
Lo veremos claro en los ejemplos.

Primero que nada, vamos a dividir el uso polimorfismo del polimorfismo entre "duck typing" y "abstracción de clases".

El **duck typing** (viene de una broma nerd: "si camina como un pato y habla como un pato, lo trato como un pato"), implica que si dos objetos pertenecen a clases que no se relacionan entre si pero tienen métodos que se llaman igual, los puedo gestionar de la misma manera:

``` py
class Gato:
    especie = 'gato'

    def actividad(self):
        return 'Saltar'
    
class Auto:
    especie = 'auto'

    def actividad(self):
        return 'Gastar nafta'

g = Gato()
a = Auto()    
objetos_varios = [g, a]

for objeto in objetos_varios:
    print(f'El {objeto.especie} se dedica a: {objeto.actividad()}')
```
En este ejemplo vemos que, aunque un gato y un auto no se relacionan, al tener ambos el método **actividad**, puedo manejarlos en un mismo proceso y en cada caso, aún cuando compartan la denominación de elementos, cada uno mostrará cosas diferentes.

Este mecanismo facilita en gran forma la algoritmia necesaria para el funcionamiento de los programas.

---
Las **clases abstractas**, por otro lado, implementan el polimorfismo de manera diferente.
Aquí tendremos una clase Madre que no está pensada para ser instanciada sino solamente heredada, que puede definir métodos que obligatoriamente deban ser redefinidos, forzando a las clases hijas a especificarlo. En estos casos, a diferencia del duck typing, las clases están vinculadas por herencia y las hijas tendrán métodos del mismo nombre y, por sus diferencias, otro comportamiento.

``` py
from abc import ABC, abstractmethod

class Animal(ABC): # Clase abstracta (hereda de Abstract Base Class)

    @abstractmethod # Método abstracto
    def habla(self) -> str: # Debe ser implementado en las clases hijas (o subclases)
        pass

    def dormir(self): # Método concreto. Se hereda normalmente.
        return "ZZZ"

class Perro(Animal):
    def habla(self): # polimorfismo
        return "guau!"

    def __str__(self):
        return 'perro'
    
class Gato(Animal):
    def habla(self):
        return "miau!"

    def __str__(self):
        return 'gato'
    
animales = [Perro(), Gato()]

for animal in animales:
    print(f'El {animal} hace {animal.habla()}')
    print(f'y duerme asi: {animal.dormir()}')
```

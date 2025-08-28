# **Herencia**

La Herencia es uno de los principales aportes de la OOP. Nos permite definir jerarquías de clases yendo de la general a lo particular o al revés. De esta manera, evitamos repeticiones innecesarias de código y obtenemos estructuras más coherentes y ordenadas.

La Herencia se puede realizar por **especialización** o por **generalización**.

Cuando tengo una clase **Madre** como por ejemplo **Vehiculo**, puedo definir clases **Hijas** como **Bicicleta** y **Auto**, que son Vehiculos, con características más específicas (por ejemplo un Auto es un Vehiculo que tiene motor). Este proceso es la **especialización**, cuando se construyen clases herederas que dispondrán de todas las características (atributos) y todas las funciones (métodos) de su clase Madre pero además agregarán nuevos atributos y métodos específicos.

``` py
# Herencia por especialización
class Vehiculo: # clase Madre (desde aquí comienzo)
    def __init__(self, color, velocidad) -> None:
        self.color = color
        self.velocidad = velocidad

    def es_veloz(self):
        msg = 'es veloz' if self.velocidad > 100 else 'es lenta'
        return msg

class Bicicleta(Vehiculo): # clase Hija: Bicicleta hereda a Vehiculo
    def __init__(self, color, velocidad, tipo) -> None:
        super().__init__(color, velocidad)
        self.tipo = tipo

class VehiculoMotor(Vehiculo): # clase Hija: hereda a Vehiculo
    def __init__(self, color, velocidad, cilindrada) -> None:
        super().__init__(color, velocidad)
        self.cilindrada = cilindrada
    
class Auto(VehiculoMotor): # "Nieta" de Vehiculo
    def __init__(self, color, velocidad, cilindrada, puertas) -> None:
        super().__init__(color, velocidad, cilindrada)
        self.puertas = puertas

class Moto(VehiculoMotor):
    def __init__(self, color, velocidad, cilindrada, tipo) -> None:
        super().__init__(color, velocidad, cilindrada)
        self.tipo = tipo
    
bici = Bicicleta('rojo', 40, 'calle')
print(bici.color, bici.es_veloz())
motito = Moto('negra', 100, 110, 'enduro')
print(motito.color, motito.velocidad, motito.cilindrada, motito.tipo)
```

---
El proceso inverso es la **generalización**, que se realiza cuando tengo al menos 2 clases, por ejemplo **Alumno** y **Docente**, que observo que comparten algunos elementos (atributos y/o métodos) y entonces puedo construir una clase Madre que contenga todo lo que tienen en común (**nombre** y **edad**) dejando en las clases Hijas solamente lo que las distingue (**notas** en el caso de Alumno y **materia** en el caso de Docente).

``` py
# Herencia por generalización
class Persona: # esta clase Madre la construyo desde Alumno y Docente
    def __init__(self, nombre, edad) -> None:
        # estos atributos originalmente estaban repetidos en las clases Hijas
        self.nombre = nombre
        self.edad = edad

    def es_mayor(self):
        msg = 'es mayor' if self.edad >= 18 else 'es menor'
        return msg

class Alumno(Persona):
    def __init__(self, nombre, edad, notas) -> None:
        # de aquí quité nombre y edad
        super().__init__(nombre, edad) # ejecuta el constructor de Persona
        self.notas = notas

alu1 = Alumno('Pepe', 17, [4, 6, 7])
print(f'Las notas de {alu1.nombre} son {alu1.notas} y {alu1.es_mayor()}')

class Docente(Persona):
    def __init__(self, nombre, edad, materia) -> None:
        # de aquí quité nombre y edad
        super().__init__(nombre, edad)
        self.materia = materia

docente1 = Docente('Pedro', 44, 'Inglés')

```

---
La Herencia (o la posibilidad de implementarla) se puede verificar con facilidad utilizando el verbo SER en una frase que contenga a una clase Madre y una clase Hija.

Si yo puedo decir: "Un Docente **ES** una Persona", pues entonces hay Herencia posible entre **Persona**(clase Madre) y **Docente**(clase Hija).

Lo mismo se aplica a Bicicleta y Vehiculo: "Una Bicicleta **ES** un Vehiculo".

En concreto, independientemente del proceso de creación de la Herencia (sea por especialización o generalización), siempre resulta que una instancia (objeto) de la clase Hija se puede considerar también una instancia de la clase Madre. Un gatito será un objeto creado a partir de la clase Gato que hereda de Animal, y por lo tanto dicho gatito será naturalmente un Animal.

---

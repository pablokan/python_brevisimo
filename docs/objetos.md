# Objetos

La **Programación Orientada a Objetos** (en español: **POO**, en inglés: **OOP**) consiste en la declaración de Clases que permiten tener en una sola estructura, el objeto, tanto datos como acciones sobre esos datos.  

Las **clases** son plantillas, planos o, como me dijo un alumno hace algunos años en un examen, "una clase es una budinera, sirve para hacer budines pero no tengo ningún budín hasta que no hago uno".

## Clase:
![clase](img/budinera.webp) 

## Objeto:
![objeto](img/flan.webp)

Primer Ejemplo:

```py
class Persona:
    def __init__(self, n, e): # constructor: inicializa los atributos
        self.nombre = n # atributo: variable que representa una característica del objeto
        self.edad = e # otro atributo

    def saludo(self): # el self representa al objeto que se va a crear
        return  "Hola " + self.nombre + " tenés " + str(self.edad) + " años."

    def adulto(self): # las funciones dentro de los objetos se llaman métodos
        if self.edad >= 18:
            return True
        else:
            return False



pibe = Persona("José", 13)
profesora = Persona("Ana", 35)
bebito = Persona("Benjamín", 1)

print(profesora.saludo()) # los métodos siempre llevan paréntesis
print("Es adulto?", pibe.adulto()) # este método devuelve una variable booleana
print(bebito.nombre) # muestra el atributo directamente
```
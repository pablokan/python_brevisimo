# Objetos

La **Programación Orientada a Objetos** (en español: **POO**, en inglés: **OOP**) consiste en la declaración de Clases que permiten tener en una sola estructura, el **objeto** o **instancia**, tanto datos, como acciones sobre esos datos.  

Las **clases** son plantillas, planos o, como me dijo un alumno hace algunos años en un examen, "una clase es una budinera, sirve para hacer budines pero no tengo ningún budín hasta que no hago uno".

## Clase
![clase](img/budinera.webp) 

## Objeto
![objeto](img/flan.webp)

Ejemplo #1:
```py
class Gato:
    especie = "Felis silvestris catus" # atributo de clase: aplica a todos los objetos que se crean
    def __init__(self, n): # el self representa a cada objeto que se creará
        self.nombre = n # atributo de instancia u objeto

gatito = Gato("Kitty")
print("El gatito se llama", gatito.nombre) 
# el nombre del objeto reemplaza al self 
# que pusimos en la declaración de la clase, 
# luego se coloca un punto y finalmente el nombre del atributo.
```

Ejemplo #2:
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

    def esAdulto(self):
        if self.adulto():
            return "si, es adulto"
        else:
            return "no, aún no es adulto"

pibe = Persona("José", 13) # creación del objeto o instancia
profesora = Persona("Ana", 35) # otra instanciación
bebito = Persona("Benjamín", 1) # los argumentos se reciben en los parámetros del constructor

print(profesora.saludo()) # los métodos siempre llevan paréntesis
print("Es adulto?", pibe.esAdulto()) # este método devuelve una variable booleana
print("El bebé se llama", bebito.nombre) # muestra el atributo directamente
```
Observen que el objeto reemplaza a self en los atributos y en los métodos. Siempre va el nombre del objeto, un punto y finalmente el nombre del atributo o método.


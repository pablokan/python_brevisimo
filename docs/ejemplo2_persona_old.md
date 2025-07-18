## Ejemplo #2:

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

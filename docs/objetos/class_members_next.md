# **Miembros de Clase (atributos y métodos de clase)**

Los atributos y métodos de clase son aquellos que aplican a la totalidad de las instancias (objetos) que se crean.

Por ejemplo, si tenemos una clase **GatoDomestico**, cada instancia (cada objeto gato que se cree), podrá tener su atributo nombre específico, su edad, su comportamiento, etc.
Pero todos ellos serán de la **especie Felis Catus**, por lo tanto, **especie** será un atributo de clase, en lugar de ser un atributo de instancia.

A diferencia de los miembros de instancia, en lugar de usar solamente **self**, se utiliza **cls** para hacer referencia específica a la clase. Aunque con self también se puede acceder desde una instancia a un atributo de clase.

``` py
# atributos y métodos de clases
class Persona:
    especie = 'Homo Sapiens' # atributo de clase (aplica a todos los objetos)

    def __init__(self, nombre, edad) -> None:
        self.nombre = nombre # atributos de instancia 
        self.edad = edad

    def __str__(self):
        return f'Especie:{self.especie} Nombre:{self.nombre} Edad:{self.edad}'
    
    @classmethod
    def desde_datos(cls, persona_datos): #constructor alternativo
        nombre, edad = persona_datos.split('-')
        edad = int(edad)
        return cls(nombre, edad)
        
    @classmethod
    def set_especie(cls, nombre) -> None:
        cls.especie = nombre

alguien = Persona('Ana', 22)
print(alguien)
otra_persona = Persona('Juan', 35)
print(otra_persona)
dato1 = 'Luis-61'
otra_persona_mas = Persona.desde_datos(dato1)
print(otra_persona_mas)
Persona.set_especie('Homo Neanderthalensis')
print(alguien)
print(otra_persona)
```

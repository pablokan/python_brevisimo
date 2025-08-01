# **Encapsulamiento**

El **encapsulamiento** consiste en el acceso a los **atributos** solamente a través de **métodos**, NO de forma directa. Es decir que si yo tengo, por ejemplo, un atributo ***nombre***, tanto sea para asignarlo como para obtener su valor, tengo que definir métodos que hagan esa tarea. Por convención, se les llama **setters** (métodos que asignan) y **getters** (métodos que obtienen).
En Python, esto no es obligatorio (siempre puedo seguir accediendo a los atributos directamente), pero se considera una **buena práctica**.

---

En lugar de hacer esto:

``` py
class Persona:
    def __init__(self, edad) -> None:
        self.edad = edad

persona = Persona(35)
print(persona.edad) # esto se quiere evitar (aunque funciona)

```

Es más recomendable (en principio) hacer esto:

``` py
class Persona:
    def __init__(self, edad) -> None:
        self.set_edad(edad)

    def get_edad(self): # getter (get == obtener)
        return f'Edad: {self.edad}'
    
    def set_edad(self, nueva_edad): # setter (set == asignar)
        if nueva_edad > 0:
            self.edad = nueva_edad
        else:
            print('No puede tener edad negativa')
            self.edad = None

persona = Persona(11)
print(persona.get_edad())
otra_persona = Persona(-35)
print(otra_persona.get_edad())

```

Lo primero que se puede observar es que al convocar al setter en el constructor, permite validar el argumento de entrada (en este caso, impedir edad negativa).

---

Sin embargo, la forma más **pitónica** es usar **decoradores** (funciones especiales que modifican el comportamiento de los métodos):

``` py
class Persona:
    def __init__(self, edad) -> None:
        # La línea que sigue PARECE que asigna el parámetro al atributo...
        # ... pero en realidad, convoca al setter
        self.edad = edad

    @property # decorador
    def edad(self): # getter
        return f'La edad es {self._edad}'
    
    @edad.setter # decorador
    def edad(self, nueva_edad): # setter
        if nueva_edad < 0:
            print('No puede tener edad negativa!')
            self._edad = None
        else:
            self._edad = nueva_edad # este es el atributo VERDADERO

persona = Persona(10) # el valor va al setter que lo valida
# la siguiente línea PARECE mostrar el atributo...
# ... pero está convocando al getter
print(persona.edad) # el atributo real es _edad (con _ adelante)
otra_persona = Persona(-9)
print(otra_persona.edad)
```

Un ejemplo casi igual pero con carteles para ir mostrando el flujo de ejecución, además aquí se usa la instrucción ***raise*** que funciona como un ***return*** que es capturado por el ***except***:

``` py
class Persona:
    def __init__(self, edad):
        print('⦃constructor', end=' ')
        self.edad = edad
        print('constructor⦄', end=' ')

    @property # decorador 
    def edad(self): # getter (get == obtiene)
        print('⦃get', end=' ')
        return f'Edad: {self._edad}⦄' # este es el atributo VERDADERO

    @edad.setter 
    def edad(self, nueva_edad): # setter (set == asigna)
        print('⦃set', end=' ')
        if nueva_edad < 0:
            raise ValueError("La edad no puede ser negativa.")
        self._edad = nueva_edad # este es el atributo VERDADERO
        print(f'{self._edad=}', end=' ')
        print('set⦄', end=' ')


persona = Persona(10)
print(persona.edad)

try:
    otra_persona = Persona(-30)
except ValueError as error:
    print(f'Mensaje de error devuelto por el raise: {error}')

#p1.edad(50) # No funciona así el setter
persona.edad = 50 # ahora si!
print()
print(f'⦃ {persona.edad=} ⦄') # este es el GETTER
print(f'⦃ {persona._edad=} ⦄') # este es el atributo VERDADERO

```
!!! note "Nomenclatura de atributos"
    Por convención, los atributos se muestran como "privados" al colocar uno o dos guiones bajos al comienzo de sus nombres.

    Ejemplo: **_nombre** o **__nombre**

    De cualquier manera, siempre pueden ser accedidos directamente ya que Python no tiene atributos REALMENTE inaccesibles.
    La diferencia entre ambos existe en la forma de acceso directo, pero es una decisión de nomenclatura y no cambia demasiado. Se los llama de varios modos (privacidad débil y fuerte, por ejemplo) pero elijan libremente cual usar.

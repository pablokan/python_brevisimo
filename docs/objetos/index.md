# Orientación a Objetos

La **Programación Orientada a Objetos** (en español: **POO**, en inglés: **OOP**) es un paradigma (forma de organización del código) de programación que surgió con el objetivo de mejorar la modelización de la realidad. Se trató de eliminar algunos supuestos defectos del paradigma de la **Programación Estructurada**.

## Objetivos

- Mayor consistencia: al poner datos y operaciones sobre sobre los mismos dentro de la misma estructura, se reduce el riesgo de desajustes.
- Mejor reutilización: a partir de la **Herencia**
- Simplificación: **Abstracción** (importa QUÉ hace y no CÓMO)
- Seguridad y validación: Acceso más controlado a los datos (**Encapsulamiento**)
- Sencillez: el **Polimorfismo** nos da interfases comunes para objetos diversos.
- Menor acoplamiento: Mejorar la relación entre componentes (**Composición**)

## Terminología

- Clase: Las **clases** son moldes, plantillas, planos o, como me dijo un alumno hace algunos años en un examen, "una clase es una budinera, sirve para hacer budines pero no tengo ningún budín hasta que no hago uno".
- Instancia: el **objeto** propiamente dicho (un budín!)
- Miembros de la clase
    - Atributo: Características o propiedades de un objeto.
    - Método: Acciones o comportamientos de un objeto.

## Clase

![clase](../img/budinera.webp) 

## Objeto

![objeto](../img/flan.webp)

## Nomenclatura

En Python, la nomenclatura de clases sigue la convención de usar PascalCase, donde la primera letra de cada palabra en el nombre de la clase se escribe en mayúscula. Además, es recomendable que los nombres de clase sean sustantivos singulares.
Ejemplos: Usuario, Producto, Coche, GatoDomestico.

```py
class Alumno:
    def __init__(self, nombre, apellido): # método constructor
        self.nombre = nombre # self.nombre es un atributo ...
        self.apellido = apellido # ... y self.apellido otro atributo
        inicial = nombre[0].lower() # variable local
        # y self.mail aunque no viene de parámetros, también es un atributo:
        self.mail = f'{inicial}.{apellido.lower()}@itecriocuarto.org.ar'

    def nombre_completo(self): # método
        return f'{self.nombre} {self.apellido}'
    
    def promedio(self, *args): # otro método
        return sum(args) / len(args)

alumno1 = Alumno('Juan', 'Torres') # instanciación (creación del objeto)
print(f'El alumno {alumno1.nombre_completo()} tiene este mail: {alumno1.mail}')
print(f'Y su promedio es {alumno1.promedio(4,5,7)}')
```

Observen que el objeto reemplaza a self en los atributos y en los métodos. Siempre va el nombre del objeto, un punto y finalmente el nombre del atributo o método (este siempre lleva paréntesis).

## Listas de objetos

Las estructuras de datos, como las listas, no solamente pueden almacenar valores de los tipos de datos comunes que ya conocíamos, sino también instancias de clases (objetos).

```py
class Alumno:
    def __init__(self, nombre, apellido): # método constructor
        self.nombre = nombre
        self.apellido = apellido
        inicial = nombre[0].lower()
        self.mail = f'{inicial}.{apellido.lower()}@itecriocuarto.org.ar'

    def nombre_completo(self):
        return f'{self.nombre} {self.apellido}'
    
    def promedio(self, *args):
        return sum(args) / len(args)

alumnos: list[Alumno] = [] # VER Tipado explícito
for i in range(2):
    nombre_carga = input('Nombre: ')
    apellido_carga = input('Apellido: ')
    alumno_carga = Alumno(nombre_carga, apellido_carga) # instanciamos
    alumnos.append(alumno_carga) # cargamos el objeto en la lista

for alumno_almacenado in alumnos: # recorremos la lista de objetos 'Alumno'
# la variable de recorrido es un objeto y dispone de los atributos y métodos:
    print(alumno_almacenado.mail) 
    print(alumno_almacenado.nombre_completo()) 
```

## Tipado explícito

Ya sabemos que Python no fuerza la declaración de tipos de datos, sin embargo en la actualidad se considera una buena práctica, y si bien no se relaciona necesariamente con la OOP, lo traigo aquí porque, además del aporte a la legibilidad, sirve de mucha ayuda para el autocompletado y la visibilidad de los errores cuando usamos editores como Visual Studio Code, sus derivados y la mayoría de los más utilizados.

``` py
nombre: str = 'Ana' # se puede declarar junto con la asignación

edad: int # o bien declarar ...
edad = 22 # ... y luego asignar

egresado: bool = False

# en las listas y tuplas se pone entre corchetes el tipo de los valores
nombres: list[str] = ['Ana', 'Luis']

# en un diccionario, habitualmente 'str' para la clave y otro tipo de dato
# para el valor o bien 'object' si queremos que pueda ser cualquiera:
persona: dict[str, object] = {'nombre': 'Ana', 'edad': 22, 'notas': [4, 7]}

# las funciones pueden tener tipo de retorno o None cuando no devuelven nada
def main() -> None:
    print('Yo soy main')

def saludo(nombre: str) -> str: # los parámetros también (esto es muy útil !!!)
    return f'Hola {nombre}!'

print(saludo('Juan'))

# y se puede anidar estructuras más complejas como aquí:
personas: list[dict[str, object]] = [
    {'nombre': 'Juan', 'edad': 35},
    {'nombre': 'Ana', 'edad': 23}
]   

```

# Orientación a Objetos

La **Programación Orientada a Objetos** (en español: **POO**, en inglés: **OOP**) es un paradigma (forma de organización del código) de programación que surgió con el objetivo de mejorar la modelización de la realidad. Se trató de eliminar algunos supuestos defectos del paradigma de la **Programación Estructurada**.

## Objetivos

- Mayor consistencia: al poner datos y operaciones sobre sobre los mismos dentro de la misma estructura, se reduce el riesgo de desajustes.
- Mejor reutilización: a partir de la **Herencia**
- Simplificación: **Abstracción** (importa QUÉ hace y no CÓMO)
- Seguridad: Acceso más controlado a los datos (**Encapsulamiento**)
- Sencillez: el **Polimorfismo** nos da interfases comunes para objetos diversos.

## Terminología

- Clase: Las **clases** son moldes, plantillas, planos o, como me dijo un alumno hace algunos años en un examen, "una clase es una budinera, sirve para hacer budines pero no tengo ningún budín hasta que no hago uno".
- Instancia: el objeto propiamente dicho (un budín!)
- Atributo: Características o propiedades de un objeto.
- Método: Acciones o comportamientos de un objeto.

## Clase

![clase](img/budinera.webp) 

## Objeto

![objeto](img/flan.webp)

## Nomenclatura

En Python, la nomenclatura de clases sigue la convención de usar PascalCase, donde la primera letra de cada palabra en el nombre de la clase se escribe en mayúscula. Además, es recomendable que los nombres de clase sean sustantivos singulares.
Ejemplos: Usuario, Producto, Coche, GatoDomestico.

Ejemplo #1:

```py
class Alumno:
    def __init__(self, nombre, apellido): # método constructor
        self.nombre = nombre # self.nombre es el atributo
        self.apellido = apellido
        self.mail = f'{nombre[0].lower()}.{apellido.lower()}@itecriocuarto.org.ar'

    def nombre_completo(self):
        return f'{self.nombre} {self.apellido}'
    
    def promedio(self, *args):
        return sum(args) / len(args)

alumno1 = Alumno('Juan', 'Torres') # instanciación (creación del objeto)
print(f'El alumno {alumno1.nombre_completo()} tiene este mail: {alumno1.mail}')
print(f'Y su promedio es {alumno1.promedio(4,5,7)}')

```

Observen que el objeto reemplaza a self en los atributos y en los métodos. Siempre va el nombre del objeto, un punto y finalmente el nombre del atributo o método (este siempre lleva paréntesis).

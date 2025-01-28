# Tutorial de Python: De Básico a OOP
*Un repaso completo para programadores principiantes*

## Tabla de Contenidos
1. [Configuración del Entorno](#configuración-del-entorno)
2. [Conceptos Básicos](#conceptos-básicos)
3. [Estructuras de Control](#estructuras-de-control)
4. [Funciones](#funciones)
5. [Estructuras de Datos](#estructuras-de-datos)
6. [Programación Orientada a Objetos](#programación-orientada-a-objetos)
7. [Manejo de Archivos](#manejo-de-archivos)
8. [Gestión de Paquetes y Módulos](#gestión-de-paquetes-y-módulos)
9. [Proyecto Final](#proyecto-final)

## Configuración del Entorno

### Instalación de Python
1. Descarga Python desde python.org
2. Instala asegurándote de marcar "Add Python to PATH"

### Configuración de uv (Gestor de Entornos Virtuales)
```bash
# Instalar uv
pip install uv

# Crear un nuevo entorno virtual
uv venv

# Activar el entorno virtual
# En Windows:
.venv\Scripts\activate
# En Unix/MacOS:
source .venv/bin/activate
```

## Conceptos Básicos

### Variables y Tipos de Datos
```python
# Tipos básicos
nombre = "Ana"  # str
edad = 25      # int
altura = 1.75  # float
es_estudiante = True  # bool

# Print con formato
print(f"Me llamo {nombre} y tengo {edad} años")
```

### Operadores
```python
# Aritméticos
suma = 5 + 3
resta = 10 - 4
multiplicacion = 6 * 2
division = 15 / 3
division_entera = 15 // 2
modulo = 15 % 2
potencia = 2 ** 3

# Comparación
igual = 5 == 5
diferente = 5 != 3
mayor = 5 > 3
menor = 3 < 5
```

## Estructuras de Control

### Condicionales
```python
edad = 18

if edad >= 18:
    print("Eres mayor de edad")
elif edad >= 13:
    print("Eres adolescente")
else:
    print("Eres menor de edad")
```

### Bucles
```python
# While
contador = 0
while contador < 5:
    print(contador)
    contador += 1

# For
for i in range(5):
    print(i)

# For con lista
frutas = ["manzana", "pera", "uva"]
for fruta in frutas:
    print(fruta)
```

## Funciones

### Definición y Uso
```python
def saludar(nombre, edad=None):
    if edad:
        return f"Hola {nombre}, tienes {edad} años"
    return f"Hola {nombre}"

# Llamadas a función
print(saludar("Juan"))
print(saludar("Ana", 25))

# Función con argumentos variables
def suma(*args):
    return sum(args)

print(suma(1, 2, 3, 4))  # 10
```

## Estructuras de Datos

### Listas
```python
# Creación y manipulación
numeros = [1, 2, 3, 4, 5]
numeros.append(6)
numeros.pop()
primer_elemento = numeros[0]
ultimo_elemento = numeros[-1]

# List comprehension
cuadrados = [x**2 for x in range(5)]
```

### Diccionarios
```python
# Creación y acceso
persona = {
    "nombre": "Juan",
    "edad": 25,
    "ciudad": "Madrid"
}

print(persona["nombre"])
persona["profesion"] = "Programador"

# Iteración
for clave, valor in persona.items():
    print(f"{clave}: {valor}")
```

## Programación Orientada a Objetos

### Clases y Objetos
```python
class Persona:
    def __init__(self, nombre, edad):
        self.nombre = nombre
        self.edad = edad
    
    def saludar(self):
        return f"Hola, soy {self.nombre}"
    
    @property
    def es_mayor_edad(self):
        return self.edad >= 18

# Uso de la clase
juan = Persona("Juan", 25)
print(juan.saludar())
print(juan.es_mayor_edad)
```

### Herencia
```python
class Estudiante(Persona):
    def __init__(self, nombre, edad, carrera):
        super().__init__(nombre, edad)
        self.carrera = carrera
    
    def estudiar(self):
        return f"Estoy estudiando {self.carrera}"

# Uso de la herencia
ana = Estudiante("Ana", 20, "Informática")
print(ana.saludar())
print(ana.estudiar())
```

## Manejo de Archivos

### Lectura y Escritura
```python
# Escribir archivo
with open("ejemplo.txt", "w") as f:
    f.write("Hola mundo\n")
    f.write("Segunda línea")

# Leer archivo
with open("ejemplo.txt", "r") as f:
    contenido = f.read()
    print(contenido)

# Leer línea por línea
with open("ejemplo.txt", "r") as f:
    for linea in f:
        print(linea.strip())
```

## Gestión de Paquetes y Módulos

### Estructura de Proyecto
```
mi_proyecto/
│
├── src/
│   ├── __init__.py
│   ├── main.py
│   └── utils/
│       ├── __init__.py
│       └── helpers.py
│
├── tests/
│   ├── __init__.py
│   └── test_main.py
│
├── requirements.txt
└── README.md
```

### Creación de Módulos
```python
# helpers.py
def validar_edad(edad):
    return edad >= 0 and edad <= 120

def formatear_nombre(nombre):
    return nombre.strip().title()

# main.py
from utils.helpers import validar_edad, formatear_nombre

def procesar_usuario(nombre, edad):
    if validar_edad(edad):
        nombre_formateado = formatear_nombre(nombre)
        return f"Usuario: {nombre_formateado}, Edad: {edad}"
    return "Edad inválida"
```

### Gestión de Dependencias
```bash
# Crear requirements.txt
uv pip freeze > requirements.txt

# Instalar dependencias
uv pip install -r requirements.txt
```

## Proyecto Final

### Gestor de Tareas Simple
```python
# task_manager.py
class Task:
    def __init__(self, title, description=""):
        self.title = title
        self.description = description
        self.completed = False

class TaskManager:
    def __init__(self):
        self.tasks = []
    
    def add_task(self, title, description=""):
        task = Task(title, description)
        self.tasks.append(task)
        return len(self.tasks) - 1  # retorna el índice
    
    def complete_task(self, index):
        if 0 <= index < len(self.tasks):
            self.tasks[index].completed = True
            return True
        return False
    
    def list_tasks(self):
        for i, task in enumerate(self.tasks):
            status = "✓" if task.completed else " "
            print(f"[{status}] {i}: {task.title}")

# main.py
def main():
    manager = TaskManager()
    
    while True:
        print("\n1. Agregar tarea")
        print("2. Completar tarea")
        print("3. Listar tareas")
        print("4. Salir")
        
        opcion = input("\nSeleccione una opción: ")
        
        if opcion == "1":
            titulo = input("Título de la tarea: ")
            desc = input("Descripción (opcional): ")
            manager.add_task(titulo, desc)
        elif opcion == "2":
            index = int(input("Índice de la tarea: "))
            manager.complete_task(index)
        elif opcion == "3":
            manager.list_tasks()
        elif opcion == "4":
            break

if __name__ == "__main__":
    main()
```

Este tutorial cubre los conceptos fundamentales de Python y proporciona una base sólida para comenzar a programar. Para profundizar en cualquier tema, se recomienda consultar la documentación oficial de Python y practicar con ejercicios adicionales.

# **Composición**

La Composición, junto a la Herencia, son las dos maneras principales de vincular Clases. Como ya hemos visto, decimos que una Clase hereda de otra, cuando podemos usar el verbo SER para confirmar dicha relación, ejemplo, Gato hereda de Animal, porque un gato **es** un animal.

En el caso de la Composición, decimos que una Clase compone o es componente de otra, cuando podemos usar el verbo TENER, ejemplo, una empresa **tiene** empleados, por tanto, la clase Empleado compone a Empresa. 

Esta forma de Composición se denomina **Agregación**, porque es una forma 'débil' ya que una Empresa **puede tener** empleados aunque no es obligatorio (hay empresas unipersonales: un dueño, ningún empleado).

``` py
# Agregación (Composición Débil)
class Empleado: # clase contenida (secundaria)
    def __init__(self, nombre):
        self.nombre = nombre

class Empresa: # clase contenedora (principal)
    def __init__(self):
        #self.empleado = 'José' # NO es composición
        self.empleado = Empleado('José') # Composición

empresa = Empresa()
print(empresa.empleado.nombre)
```

---
Por otro lado, tenemos la Composición propiamente dicha, o 'fuerte', que es cuando las instancias de la Clase Componente son **requeridas obligatoriamente**, por ejemplo, un auto tiene puertas y motor (y no es opcional!): 

``` py
# Composición (Fuerte: el auto DEBE tener puertas)
class Puerta: # clase componente o contenida
    def __init__(self, uv, uh):
        self.uv = uv
        self.uh = uh

    def abrir_puerta(self):
        print(f'Abierta la puerta {self.uv} {self.uh}')

    def cerrar_puerta(self):
        print(f'Cerrada la puerta {self.uv} {self.uh}')

class Auto: # clase compuesta o contenedora
    def __init__(self, tipo_auto, nombre):
        print(nombre)
        self.di = Puerta("delantera", "izquierda") # Comp (agregar una puerta al auto)
        self.dd = Puerta("delantera", "derecha")
        if tipo_auto == "sedán":
            self.ti = Puerta("trasera", "izquierda")
            self.td = Puerta("trasera", "derecha")

cupecita = Auto('cupé', 'Cupecita')
cupecita.di.abrir_puerta()
cupecita.di.cerrar_puerta()
duna = Auto("sedán", "Duna")
duna.td.abrir_puerta()
```

---
Naturalmente, las dos formas de vinculación de Clases se pueden implementar de manera combinada, teniendo en una misma aplicación, tanto **Herencia** como **Composición**:

``` py
class Persona:
    def __init__(self, nombre) -> None:
        self.nombre = nombre

class Musico(Persona):
    def __init__(self, nombre, instrumento) -> None:
        super().__init__(nombre)
        self.instrumento = instrumento

    def __str__(self):
        return f'{self.nombre} toca {self.instrumento}'
    
class Banda:
    def __init__(self, nombre, miembros) -> None:
        self.nombre = nombre
        self.miembros = [] # lista de objetos Musico
        for datos in miembros:
            nombre_musico, instrumento = datos
            musico = Musico(nombre_musico, instrumento) # composición
            self.miembros.append(musico)

    def __str__(self) -> str:
        salida = f'\nBanda {self.nombre}\n'
        salida += ' - '.join([str(m) for m in self.miembros])
        return salida

integrantes = [
        ('John', 'la guitarra'), 
        ('Paul', 'el bajo'), 
        ('George', 'la guitarra'), 
        ('Ringo', 'la batería')
    ]
integrantes.append(('Quinto Beatle', 'pandereta'))

beatles = Banda('Los Beatles', integrantes)
print(beatles)

duo = [
    ('Simon', "arpa"),
    ('Garfunkel', 'bongó')
]
sg = Banda('Simon & Garfunkel', duo)
print(sg)
```

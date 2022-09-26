# PySide6

Aún no hemos trabajado ambientes virtuales (virtual environments), por ahora vamos a instalar la librería GUI en el Python global.

---
Instalación:
```py
pip install pyside6
```
---
Escribimos nuestra primera ventana:
```py
# minima.py
from PySide6.QtWidgets import QApplication, QWidget

app = QApplication() # crea una instancia de la clase Aplicación 

window = QWidget() # crea una ventana como widget 
# (todos los objetos que veremos son widgets, los botones por ejemplo)

window.show() # muestra la ventana

app.exec() # inicia el bucle de eventos
```
---
Ahora vamos a reemplazar la instanciación de un widget para crear una ventana propiamente dicha (que podrá tener menúes, barra de estado, barra de herramientas, etc. -lo veremos más adelante-)
```py
from PySide6.QtWidgets import QApplication, QMainWindow # reemplacé QWidget por QMainWindow

app = QApplication() # crea una instancia de la clase Aplicación 

window = QMainWindow() # crea una ventana propiamente dicha

window.show() # muestra la ventana

app.exec() # inicia el bucle de eventos
```
---
Para poder tener más control y más flexibilidad en la ventana, creamos una nueva clase hija de **QMainWindow** y le vamos agregando otros widgets y luego disposición y diseño.
El primer ejemplo con la clase nuestra **MainWindow** como es habitual en clases hijas, hace una llamada al constructor de **QMainWindow** y luego define un botón y lo coloca como widget central de la ventana. 
```py
from PySide6.QtWidgets import QApplication, QMainWindow, QPushButton

class MainWindow(QMainWindow):
    def __init__(self):
        super().__init__()

        boton = QPushButton('Hola Mundo')
        self.setCentralWidget(boton)

if __name__ == '__main__':
    app = QApplication()
    window = MainWindow()
    window.show()
    app.exec()
```
---
Hasta acá, hemos podido definir una ventana y colocarle un solo widget. Para superar esa limitación vamos a incorporar el concepto de **layout**, que es el esquema de distribución de los widgets en la ventana.
```py
from PySide6.QtWidgets import QApplication, QWidget, QMainWindow, QVBoxLayout, QLabel, QLineEdit

class MainWindow(QMainWindow):
    def __init__(self):
        super().__init__()

        layout = QVBoxLayout() # esquema vertical
        self.texto = QLabel('Texto') # instancio texto estático
        layout.addWidget(self.texto) # agrego el texto al esquema
        self.entrada = QLineEdit() # instancio un caja de texto
        layout.addWidget(self.entrada) # agrego la caja de texto al esquema

        # estas 3 líneas de ahora en más son automáticas
        centralWidget = QWidget() # creo un widget que servirá de base del esquema
        centralWidget.setLayout(layout) # le paso el esquema 
        self.setCentralWidget(centralWidget) # lo centro

if __name__ == '__main__':
    app = QApplication()
    window = MainWindow()
    window.show()
    app.exec()
```
---
Signals & Slots: Así se denominan en PySide6 a los eventos y a las acciones que dichos eventos disparan. En términos de Python, habrá unas funciones que disparan y otras que accionan. Lo veremos fácilmente con ejemplos:
```py
from PySide6.QtWidgets import (
    QApplication, QMainWindow, 
    QLabel, QVBoxLayout, 
    QWidget, QLineEdit, QPushButton)

class MainWindow(QMainWindow):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("Saludo!") # ya que está le pongo título a la ventana
        layout = QVBoxLayout() # instancio el vertical box
        self.texto = QLabel('Ingrese su nombre:') # instancio un texto
        layout.addWidget(self.texto) # agrego el texto al vertical box
        self.entrada = QLineEdit() # instancio una caja de texto
        layout.addWidget(self.entrada) # agrego la caja de texto al vertical box
        boton = QPushButton('Saludar') # instancio un botón
        boton.setDefault(True) # para que funcione con Enter
        layout.addWidget(boton) # agrego el botón al vertical box
        boton.clicked.connect(self.saludar) # SIGNAL: conecto el click con la función saludar
        centralWidget = QWidget()
        centralWidget.setLayout(layout)
        self.setCentralWidget(centralWidget)

    def saludar(self): # SLOT: se dispara cuando se produce el evento de click del botón
        # .text() es el getter que devuelve el str contenido en el objeto texto
        self.texto.setText(f'Hola {self.entrada.text()}') 

if __name__ == '__main__':
    app = QApplication()
    window = MainWindow()
    window.show()
    app.exec()
```


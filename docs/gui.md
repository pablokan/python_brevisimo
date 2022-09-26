# GUI

**GUI** significa **Graphical User Interface** (en español **interfaz gráfica de usuario**).
Hace referencia a los ambientes gráficos de los sistemas operativos modernos, como Windows, MacOS y Linux principalmente.

Entonces, una aplicación GUI, también llamada **aplicación de escritorio** (**desktop app**), sería un programa que, a diferencia de los **programas de consola** (**CLI**: command line interface) que corren en la terminal en modo texto, tendrán una interfase similar a los programas que usamos habitualmente en el escritorio de los SO recién nombrados.

En concreto, trabajaremos con ventanas, botones, cajas de texto, caja de chequeo, botones de radio, etc.

Además del aspecto diferente en relación con las aplicaciones CLI, la diferencia principal es el flujo de ejecución.

En un programa CLI estándar, la ejecución comienza y termina (Obviamente, podemos controlar ese comportamiento con un menú de opciones que solamente nos permita terminar la ejecución cuando elegimos la opción de Finalizar).

En cambio, una aplicación GUI normalmente se ejecuta en modo bucle infinito, quedando a la espera de la interacción con el usuario. Es decir, se ejecuta y queda atenta al click de un botón, al ingreso de una tecla, al movimiento del mouse o de una opción de menú. Ese evento, dispara una acción (normalmente una función), que realiza una tarea concreta. 

Cada biblioteca maneja y denomina a esto de diferentes maneras. Pero lo central es siempre lo mismo: **algo se dispara y produce una acción**.

En Python, existen varias librerías y frameworks, las más conocidas son:

- Tkinter (que viene con el Python, pero se considera algo pobre)
- PyQt (la que veremos ahora en su variante PySide)
- wxPython (importante, la trabajé varios años en esta materia)
- PySimpleGUI (muy fácil de usar, la trabajé dos años)
  
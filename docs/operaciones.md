# Operaciones matemáticas

Las variables y las constantes o los valores literales se pueden operar matemáticamente. 
Los operadores son los siguientes: 

<span style="font-size: 150%;">```+```</span> (suma)
<span style="font-size: 150%;">```-```</span>(resta)
<span style="font-size: 150%;">```*```</span>(multiplicación)
<span style="font-size: 150%;">```**```</span>(potenciación)
<span style="font-size: 150%;">```/```</span>(división)
<span style="font-size: 150%;">```//```</span>(división entera)
<span style="font-size: 150%;">```%```</span>(módulo -resto de la división-)


```py
print(3 + 5) # muestra 8
suma = 3 + 5 # asigna el resultado a la variable suma
print(suma)
print(3 - 5) # muestra -2
print(3 * 5) # muestra 15
print(3 / 5) # muestra 0.6
print(3 // 5) # muestra 0 porque es división entera 
print(11 % 2) # muestra 1 que es el resto de la división entera
print(3 ** 5) # muestra 243, 3 elevado a la quinta potencia

# operaciones con variables (se pueden operar de manera combinada variables y literales)
a = 3
b = 5
print(a + b) # sigue dando 8
suma = a + 1 # suma vale 4
print(suma)
print(11 - b) # muestra 6
"""
```

El resultado de la operación **depende** del tipo de dato.


Es importante tener en cuenta que SIEMPRE, la función **input()**, toma el dato ingresado como **str**. Es decir que si ingreso un número, tengo que convertirlo a **int** o bien a **float** para poder operar con ese dato. De no hacerse dicha conversión, cualquier operación sobre ese número será en realidad una operación de strings.

```py
edad = input("Ingrese su edad: ")
print("El doble de tu edad es", edad * 2) # ups !
# claro! input toma string, NO multiplicó
# olvidé convertir a entero, ahora va:
edad = int(edad)
# pruebo de nuevo:
print("El doble de tu edad es", edad * 2)
```

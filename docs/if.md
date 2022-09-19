# If

Además del flujo secuencial, en la programación estructurada tenemos flujo alternativo y flujo repetitivo.
La alternativa clásica en Python se maneja con la instrucción **if** y sus instrucciones complementarios **elif** y **else**.
Ejemplo:

```py
n = 7
if n > 2: # condición: expresión con un valor de verdad 
    print("es mayor") 
else: # si no se cumple la condición del if
    print("no es mayor")
```

```py
edad = 77
if edad < 12: # el único if
    print("es un niño")
elif 13<= edad <= 19: # puede haber más de un elif
    print("es un adolescente")
elif 20 <= edad <= 70: # otro elif
    print("es un adulto")
else: # el único else para toda opción no contemplada anteriormente
    print("es un adulto mayor")
```

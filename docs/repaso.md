#Repaso rápido 
## (para copiar y pegar en el editor y probar que sale)

```py
# Primer programa 
print(“Hola mundo”)
```

Variables y sus Tipos de datos:
# Esto es un comentario porque empieza con numeral
# Variables
nombre = “José” # string
edad = 34 # int
altura = 1.87 # float

print(“Hola”, nombre, “,tenés”, edad, “años y medís”, altura)

La salida por pantalla sería: Hola José, tenés 34 años y medís 1.87


Tomar datos:

nombre = input(“Ingrese su nombre: “)
edad = int(input(“Ingrese su edad: “))  # input toma siempre string, por lo tanto si quiero tomar entero debo aplicar la función int 

```
Alternativa:

if <condición>, ejemplo: 
if nombre == “Juan”, if edad > 27, if altura <= 1.80

if edad >= 18:
	print(“es mayor de edad”)
else: # sino
	print(“es menor de edad”)

Observar que el bloque que depende del if está indentado (tabulado), 4 espacios a la derecha.



Repetitivas:

Dos instrucciones:

for, para cuando tendremos una cantidad fija de repeticiones
while, para cantidad indefinida con condición

for vr in range(vi, vf): # para una variable de recorrido que va desde valor inicial a valor final -1
	print(“hola”)
	print(vr) # si vi=5 y vf=10 entonces la salida sería: 5 - 6 - 7 - 8 - 9
	print(“chau”)

cuentaRegresiva = 10
while cuentaRegresiva > 0: # condición con valor de verdad, como el if
	print(“hola”)
	cuentaRegresiva = cuentaRegresiva - 1
	print(cuentaRegresiva)


Contadores y Acumuladores
En los procesos repetitivos, es habitual usar contadores y acumuladores.
Los contadores son variables que se incrementan de a una unidad, ejemplo: n = n + 1
y los acumuladores son totalizadores del tipo: totalSueldos = totalSueldos + sueldo





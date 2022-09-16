# Listas
``` py
iterable = ["dos", "uno", "tres"]

# Recorrido por posición
for indice in range(len(iterable)):
    print(iterable[indice])
print("-----------------------------")

# Recorrido por elemento
for elemento in iterable:
    print(elemento)
print("-----------------------------")

# Recorrido por elemento con enumeración
for i, e in enumerate(iterable, start=1):
    print(i, e)
print("-----------------------------")
```

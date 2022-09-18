# orden recomendado: 
# 1) Posicionales individuales. Parámetro posicional <-> Argumento posicional obligatorio
# 2) *args. Tupla de tamaño indeterminado de posicionales. No tiene argumentos obligatorios. Positional-only
# 3) Pares clave-valor o con valor por defecto individuales. Parámetro con valor por defecto <-> Argumento opcional
# 4) **kwargs. Diccionario de tamaño indeterminado de pares clave-valor. No tiene argumentos obligatorios. Keyword-only

# x) variantes individuales exclusivas (positional-only y keyword-only). Dependen de los seudo-parámetros / y *


def foo1(a, b, *args, n1="ene uno", **kwargs):
    print('foo1')
    print(a, b, args, n1, kwargs)
foo1(1, 2, 3, 4, 5, xX="equisequis", n1="<nuevo ene uno>", nN="algo")
foo1("a", "b") # los únicos argumentos obligatorios son los que corresponde a parámetros posicionales

# funciona pero no es recomendable porque 
def foo2(a, b, n1="ene uno", *args, **kwargs):
    print('foo2')
    print(a, b, args, n1, kwargs)
foo2(1, 2, 3, 4, 5, k='k')

# variante posicionales exclusivos (positional-only arguments)
def foo3(a, b, /, c): 
    print('foo3')
    # la / obliga a NO usar el nombre del parámetro 
    #de los que quedan a la izquierda
    print(a, b, c)
foo3(1, 2, c=3) # solamente funciona si NO se pone a= y b=

# variante clave-valor exclusivos (keyword-only arguments)
def foo4(a=1, b=2, *, c=3, d=4): 
    print('foo4')
    # el * obliga a usar el nombre del parámetro
    # de los que quedan a la derecha
    print(a, b, c, d)
foo4(11, 22, c=33, d=44) # solamente funciona si se ponen c= y d=




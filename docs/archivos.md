# Manejo de Archivos en Python - Documentación Oficial

## Función open()
La función built-in `open()` retorna un objeto file, y es la forma estándar de abrir archivos en Python.

### Sintaxis Básica
```python
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```

### Modos de Apertura
- `'r'`: Solo lectura (default)
- `'w'`: Solo escritura (trunca el archivo)
- `'x'`: Creación exclusiva
- `'a'`: Append (agregar al final)
- `'b'`: Modo binario
- `'t'`: Modo texto (default)
- `'+'`: Lectura y escritura

## Administrador de Contexto (with)
El statement `with` se introdujo en Python 2.5 (PEP 343) como una forma más limpia de manejar excepciones y limpieza de recursos.

### Características
- Implementa el protocolo de administración de contexto (__enter__ y __exit__)
- Garantiza que el archivo se cierre apropiadamente
- Maneja automáticamente las excepciones

## Métodos Principales de Objetos File

### Lectura
- `read(size=-1)`: Lee el archivo completo o 'size' bytes
- `readline()`: Lee una línea
- `readlines()`: Lee todas las líneas en una lista
- `seek(offset, whence=0)`: Mueve el cursor del archivo

### Escritura
- `write(str)`: Escribe una cadena al archivo
- `writelines(lines)`: Escribe una lista de líneas
- `flush()`: Fuerza la escritura del buffer

### Control
- `close()`: Cierra el archivo
- `closed`: Propiedad que indica si el archivo está cerrado
- `mode`: Modo de apertura del archivo
- `name`: Nombre del archivo

## Mejores Prácticas

1. **Uso de with**
   ```python
   with open('archivo.txt') as f:
       data = f.read()
   ```

2. **Manejo de Encoding**
   ```python
   with open('archivo.txt', encoding='utf-8') as f:
       texto = f.read()
   ```

3. **Procesamiento por Líneas**
   ```python
   with open('archivo.txt') as f:
       for linea in f:
           proceso(linea)
   ```

## Notas Importantes

1. Los archivos se cierran automáticamente cuando:
   - El bloque `with` termina
   - El objeto file es recolectado por el garbage collector
   
2. Es una buena práctica especificar siempre el encoding al abrir archivos de texto

3. Para archivos grandes, es preferible leer por líneas en lugar de cargar todo el archivo en memoria

4. El modo binario ('b') es necesario para archivos no textuales

## Consideraciones de Rendimiento

1. `readlines()` carga todo el archivo en memoria
2. La iteración directa sobre el archivo es más eficiente
3. `writelines()` no agrega saltos de línea automáticamente
4. El buffering puede afectar el rendimiento

## Excepciones Comunes

- `FileNotFoundError`: Archivo no encontrado
- `PermissionError`: Permisos insuficientes
- `IsADirectoryError`: Se intentó abrir un directorio
- `UnicodeDecodeError`: Error de decodificación

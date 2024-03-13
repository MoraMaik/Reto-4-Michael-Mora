# Reto-4-Michael-Mora 

*Universidad Nacional De Colombia*

**Asignatura:** Programacion de Computadores

**Docente:** Felipe Gonzalez Roldan

**Correo:** mmorame@unal.edu.co

--------
## 1. Dado un número entero, determinar si ese número corresponde al código ASCII de una vocal minúscula.

```python
# Función para determinar si un número es el código ASCII de una vocal minúscula
def es_vocal_minuscula(codigo):
    # Convertir el código entero a su correspondiente carácter ASCII
    caracter = chr(codigo)
    
    # Definir una cadena con todas las vocales minúsculas
    vocales_minusculas = 'aeiou'
    
    # Verificar si el carácter obtenido está en la cadena de vocales minúsculas
    if caracter in vocales_minusculas:
        return True
    else:
        return False

# Solicitar al usuario que ingrese un número entero
while True:
    codigo_usuario = input("Ingresa un número entero: ")
    if codigo_usuario.strip():  # Verificar si la cadena no está vacía
        try:
            codigo_usuario = int(codigo_usuario)
            break  # Salir del bucle si la conversión fue exitosa
        except ValueError:
            print("Por favor, ingresa un número entero válido.")
    else:
        print("Por favor, ingresa un número.")

# Utilizar la función para determinar si corresponde a una vocal minúscula
if es_vocal_minuscula(codigo_usuario):
    print("El número corresponde al código ASCII de una vocal minúscula.")
else:
    print("El número NO corresponde al código ASCII de una vocal minúscula.")
```
[![ascii.jpg](https://i.postimg.cc/k5T8q9X5/ascii.jpg)](https://postimg.cc/PL8NQgDG)

------------

## 2. Dada una cadena de longitud 1, determine si el código ASCII de primera letra de la cadena es par o no.
```python
# Función para determinar si el código ASCII de un carácter es par
def es_codigo_ascii_par(caracter):
    # Obtener el código ASCII del carácter
    codigo_ascii = ord(caracter)
    
    # Verificar si el código ASCII es par
    if codigo_ascii % 2 == 0:
        return True
    else:
        return False

# Solicitar al usuario que ingrese una cadena de longitud 1
cadena_usuario = input("Ingresa una cadena de longitud 1: ")

# Asegurar que la cadena tenga una longitud de 1
if len(cadena_usuario) == 1:
    # Utilizar la función para determinar si el código ASCII es par
    if es_codigo_ascii_par(cadena_usuario):
        print("El código ASCII de la letra es par.")
    else:
        print("El código ASCII de la letra NO es par.")
else:
    print("Por favor, ingresa una cadena de exactamente 1 carácter de longitud.")
```
[![ascii-par-o-no.jpg](https://i.postimg.cc/JnvLkTQL/ascii-par-o-no.jpg)](https://postimg.cc/gXVQ9H5S)

------------

## 3. Dado un carácter, construya un programa en Python para determinar si el carácter es un dígito o no.
```python
# Solicitar al usuario que ingrese un carácter
caracter = input("Ingresa un carácter: ")

# Asegurar que el usuario haya ingresado exactamente un carácter
if len(caracter) == 1:
    # Usar el método .isdigit() para determinar si el carácter es un dígito
    if caracter.isdigit():
        print("El carácter ingresado es un dígito.")
    else:
        print("El carácter ingresado NO es un dígito.")
else:
    print("Por favor, ingresa exactamente un carácter.")
```
[![digito-o-no.jpg](https://i.postimg.cc/pL2gpbtj/digito-o-no.jpg)](https://postimg.cc/F7BPB6zF)

Este programa funciona de la siguiente manera:

+ Primero, solicita al usuario que ingrese un carácter.
+ Luego, verifica si la longitud de la entrada es exactamente 1, para asegurarse de que se trata de un único carácter.
+ Si es así, utiliza el método .isdigit() para verificar si el carácter es un dígito.
+ Finalmente, imprime un mensaje indicando si el carácter es o no un dígito.

Es importante recordar que este programa solo verifica un único carácter. Si el usuario ingresa más de un carácter, el programa le pedirá que ingrese exactamente un carácter.

------------

## 4. Dado un número real x, construya un programa que permita determinar si el número es positivo, negativo o cero. Para cada caso de debe imprimir el texto que se especifica a continuación:

* Positivo: "El número x es positivo"
* Negativo: "El número x es negativo"
* Cero (0): "El número x es el neutro para la suma"
```python
# Solicitar al usuario que ingrese un número real
x = float(input("Ingresa un número real x: "))

# Determinar si el número es positivo, negativo o cero
if x > 0:
    print(f"El número {x} es positivo")
elif x < 0:
    print(f"El número {x} es negativo")
else:
    print(f"El número {x} es el neutro para la suma")
```
  [![0.jpg](https://i.postimg.cc/C1y7nkf2/0.jpg)](https://postimg.cc/XZ8dTZLK)

------------
## 5. Dado el centro y el radio de un círculo, determinar si un punto de R2 pertenece o no al interior del círculo.

```python
import math

# Función para calcular la distancia entre dos puntos
def calcular_distancia(x1, y1, x2, y2):
    return math.sqrt((x2 - x1)**2 + (y2 - y1)**2)

# Solicitar al usuario las coordenadas del centro del círculo y el radio
centro_x = float(input("Ingresa la coordenada x del centro del círculo: "))
centro_y = float(input("Ingresa la coordenada y del centro del círculo: "))
radio = float(input("Ingresa el radio del círculo: "))

# Solicitar al usuario las coordenadas del punto a verificar
punto_x = float(input("Ingresa la coordenada x del punto: "))
punto_y = float(input("Ingresa la coordenada y del punto: "))

# Calcular la distancia entre el centro del círculo y el punto
distancia = calcular_distancia(centro_x, centro_y, punto_x, punto_y)

# Determinar si el punto está dentro del círculo
if distancia <= radio:
    print("El punto está dentro del círculo.")
else:
    print("El punto NO está dentro del círculo.")
```
[![circulo-r2.jpg](https://i.postimg.cc/W1ghbZTz/circulo-r2.jpg)](https://postimg.cc/QFNXfHBZ)

Este programa realiza lo siguiente:

+ Define una función calcular_distancia que calcula la distancia euclidiana entre dos puntos.
+ Solicita al usuario que ingrese las coordenadas *x* y *y* del centro del círculo, así como el radio del círculo.
+ Solicita al usuario que ingrese las coordenadas *x* y *y* del punto a verificar.
+  Calcula la distancia entre el punto y el centro del círculo usando la función **calcular_distancia**.
+ Compara esta distancia con el radio del círculo para determinar si el punto se encuentra dentro del círculo.
+ Imprime un mensaje indicando si el punto está dentro del círculo o no.

------------

## 6.Dadas tres longitudes positivas, determinar si con esas longitudes se puede construir un triángulo.
En termino de longitudes *a*, *b* y *c* esto significa:

1) *a*+*b* > *c*
2) *a*+*c* > *b*
3) *b*+*c* > *a*

```python

# Solicitar al usuario que ingrese las tres longitudes
a = float(input("Ingresa la longitud del primer lado: "))
b = float(input("Ingresa la longitud del segundo lado: "))
c = float(input("Ingresa la longitud del tercer lado: "))

# Verificar la desigualdad triangular
if a + b > c and a + c > b and b + c > a:
    print("Con las longitudes dadas, SÍ se puede construir un triángulo.")
else:
    print("Con las longitudes dadas, NO se puede construir un triángulo.")

```

[![triangulo.jpg](https://i.postimg.cc/kGyPpnmn/triangulo.jpg)](https://postimg.cc/n9MWsfr5)

------------
**Fin del reto. Gracias.**

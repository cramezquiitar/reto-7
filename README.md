# reto-7
la solucion en el notebook esta en untilted2.ipynb

### Ejercicios
1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.
2.  Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.
3.  Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial
5. Calcular el valor de 2 elevado a la potencia n usando ciclos *for*.
6. Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for. **Disclaimer:** Trate de no utilizar el operador de potencia (**).
7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.
8. Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Taylor. **Nota:** use *math* para traer la función exponencial y mostrar la diferencia entre el valor real y la aproximación.
$$e^x \approx exp(x,n) \approx \sum_{i=0}^{n}\frac{x^i}{i!}$$
9. Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. **Nota:** use *math* para traer la función seno y mostrar la diferencia entre el valor real y la aproximación.
$$sin(x) \approx sin(x,n) \approx \sum_{i=0}^{n} (-1)^i \frac{x^{2i+1}}{(2i+1)!}$$

## Solución

### Ejercicio 1
```python
# hacer un listado con los números del 1 al 100, cada uno con su respectivo cuadrado
for n in range(1, 101):  # Creamos el bucle con el for en el rango de 1 hasta 101 sin incluir este ultimo 
    print("El cuadrado de " + str(n) + " es " + str(n**2))  # Imprimimos el numero con su respectivo cuadrado
```

### Ejercicio 2
```python
# Imprimir los números impares desde 1 hasta 999
for n in range(1, 1000):  # Recorremos del 1 al 999
    if n % 2 != 0:  # Verificamos si el número es impar
        print(n)  # Imprimimos los impares

# Imprimir los números pares desde 2 hasta 1000
for n in range(2, 1001):  # Recorremos del 2 al 1000
    if n % 2 == 0:  # Verificamos si el número es par
        print(n)  # Imprimimos los pares
```

### Ejercicio 3
```python
# Imprimir números pares descendentes desde n hasta 2

n = int(input("Ingrese un número entero mayor o igual a 2: "))  # Solicita un número

if n < 2:
    print("El número debe ser mayor o igual a 2.")  # Mensaje de error
else:
    if n % 2 != 0:  # Si es impar, bajamos al par más cercano
        n -= 1

    for i in range(n, 1, -2):  # Recorremos en pasos de -2
        print(i)  # Imprimir el número par
```

### Ejercicio 4
```python
# Imprimir los números del 1 hasta un número natural n dado, cada uno con su respectivo factorial

n = int(input("Ingrese un número natural: "))  # Pedimos un número natural

for i in range(1, n + 1):  # Creamos el rango desde 1 hasta n (incluyéndolo)
    
    factorial = 1  # Inicializamos el factorial en 1 para cada número i

    for j in range(1, i + 1):  # Bucle interno para calcular el factorial de i
        factorial *= j  # Multiplicamos j en cada iteración para obtener el factorial

    print(str(i) + "! = " + str(facto))  # Imprimimos el número con su factorial
```

### Ejercicio 5
```python
# Calcular el valor de 2 elevado a la potencia n usando ciclos for

n = int(input("Ingrese un número entero que no sea negativo: "))  # Pedimos un número entero no negativo

resultado = 1  # Iniciamos el resultado en 1 (ya que cualquier número elevado a 0 es 1)

for i in range(n):  # Multiplicamos 2 por sí mismo n veces
    resultado *= 2

print("2 elevado a la", n, "es:", resultado)  # Imprimimos el resultado
```

### Ejercicio 6
```python
# Leer un número natural n y un número real x, y calcular x^n usando ciclos for (sin usar el operador **)

n = int(input("Ingrese un número natural mayor o igual a 0: "))  # Pedimos que ingresen un número natural

x = float(input("Ingrese un número real x: "))  # Pedimos que ingresen un número real

resultado = 1.0  # Inicializamos el resultado en 1.0 como número flotante

# Multiplicamos x por sí mismo n veces
for i in range(n):
    resultado *= x

print(x, "elevado a la", n, "es:", resultado)  # Imprimimos el resultado final
```

### Ejercicio 7
```python
# Diseñe un programa que muestre las tablas de multiplicar del 1 al 9

for i in range(1, 10):  # Recorremos los números del 1 al 9 para generar cada tabla
    print("Tabla del " + str(i) + ":")  # Imprimimos el encabezado de cada tabla
    
    for h in range(1, 11):  # Recorremos del 1 al 10 para cada multiplicación de la tabla
        resultado = i * h  # Calculamos el resultado
        print(str(i) + " x " + str(h) + " = " + str(resultado))  # Mostramos la multiplicación
    
    print("------------")  # Línea divisoria entre tablas
```

### Ejercicio 8
```python
import math

def aproximar_exp(x: float, n: int) -> float:
    # Calcula una aproximación de e^x usando la serie de Taylor con n términos
    resultado = 0  # Iniciamos la suma acumulada en 0

    for i in range(n + 1):  # Recorremos desde i = 0 hasta n
        resultado += (x ** i) / math.factorial(i)  # Sumamos cada término de la serie

    return resultado  # Retornamos la suma total

# Solicitar valores
x = float(input("Ingrese el valor de x: "))  # Valor de entrada x
n = int(input("Ingrese el número de términos n: "))  # Cantidad de términos de la serie

# Cálculos
aproximacion = aproximar_exp(x, n)  # Aproximación de e^x
valor_real = math.exp(x)  # Valor real de e^x con math.exp
diferencia = abs(valor_real - aproximacion)  # Error absoluto

# respuestas
print("Aproximación:", aproximacion)
print("Valor real:", valor_real)
print("Diferencia:", diferencia)
```

### Ejercicio 9
```python
import math

def aproximar_seno(x: float, n: int) -> float:
    # Calcula una aproximación de sin(x) usando la serie de Maclaurin
    resultado = 0  # Inicializamos el resultado en 0

    for i in range(n + 1):  # Recorremos desde 0 hasta n
        signo = (-1) ** i  # Alternamos el signo: +, -, +, ...
        numerador = x ** (2 * i + 1)  # Potencia impar de x
        denominador = math.factorial(2 * i + 1)  # Factorial correspondiente
        resultado += signo * (numerador / denominador)  # Sumamos el término

    return resultado  # Retornamos la suma total

# Solicitamos los valores
x = float(input("Ingrese el valor de x (en radianes): "))
n = int(input("Ingrese el número de términos n: "))

# Cálculos
aproximacion = aproximar_seno(x, n)
valor_real = math.sin(x)
diferencia = abs(valor_real - aproximacion)

# Mostrar respuestas
print("Aproximación:", aproximacion)
print("Valor real:", valor_real)
print("Diferencia:", diferencia)
```

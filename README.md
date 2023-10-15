# Ya_no_quiero_ser_adulta
Cosas de adultos #9
## Punto 1
De los retos anteriores selecione 3 funciones y escribalas en forma de lambdas.
* Para este punto ultilicé el punto 1 del reto 6, en el que tocaba calcular el area y volumen de una figura, la ecuación para calcular eso, lo puse en un lambda.
```python
import math
if __name__ == "__main__":
  r1=float(input("Ingrese el radio de la esfera: "))
  r2=float(input("Ingrese el radio del cono: "))
  h=float(input("INgrese la altura del cono: "))
  g= (lambda r2, h : ((r2**2) + (h**2))**0.5)(r2,r1)
  area_superficial =(lambda r1,r2,g : (4 * math.pi * (r1**2)) + (math.pi * r2 + g))(r1,r2,g)
  volumen=(lambda r1, r2, h: (4/3* math.pi*(r1**3) ) + (1/3 * math.pi * (r2**2)*h))(r1,r2,h)
  print(f"El area suoerficial de la figura es: {area_superficial} ")
  print(f"El volumen de la figura es: {volumen}")
```
* En el punto 4 del mismo reto, el objetivo era culcular las vueltas o la deuda teniendo en cuenta el dinero que se tenpia y los productos que se debían comprar. Al igual que en e reto anterior, la formula para calcular esto, lo puse dentro de un lambda.
```python
  print("Ingresa la cantidad de cada porducto que te dijo tu mamá que compraras: ")
  P = int(input("Panes: "))
  M = int(input("Bolsasa de leche: "))
  H = int(input("Huevos: "))
  B = int(input("Ingresa la cantidad de dinreo que te dió tu mamá: "))
  vueltas_O_deuda=(lambda B,P,M,H: B-((P*300)+(M*3300)+(H*350)))(B,P,M,H)
  if vueltas_O_deuda >= 0:
    print(f"Te deben dar {vueltas_O_deuda} de vueltas ")
  else:
    vueltas_O_deuda*=-1
    print(f"Le debes a la tienda {vueltas_O_deuda}")
```
* Por último en el punto 5 de el mmismo reto, lo que se quería era calcular el valor total de un prestamo conociendo el tiempo y el interés que tiene. Ese calculo lo metí tod en un lambda.
```pyhton
  C = float(input("Ingrese el valor del prestamo: "))
  I = float(input("Ingrese el valor del interés: "))
  N = float(input("Ingrese el  tiempo: "))
  VALOR_PRESTAMO =(lambda a,b,c: a * ((1+b)**c))(C,I,N)
  print(f"Este es el valor total del prestamo {VALOR_PRESTAMO}")
```
## Punto 2
De los retos anteriores selecione 3 funciones y escribalas con argumentos no definidos (*args)
* Para el punto 3 del reto 8 la idea es imprimir la lista de números pares de manera descendente hasta determinado npumero, en vez de definir ese número en el argumento de la función, puse un `*args`.
```python
#8-3
def imprimir_pares_descendentes(*args):
    if n < 2:
        print("El número debe ser mayor o igual a 2.")
    else:
        for b in range(n, 1, -1):
            if b % 2 == 0:
                print(b)

n = int(input("Ingrese un número natural (n ≥ 2): "))
print("Números pares descendentes hasta 2:")
imprimir_pares_descendentes(n)
```
* El punto 1 del reto 8, tenía como objetivo imrpimir una lista de los números naturales hasta el 100 con su respectivo cuadrado, en este lo que hice fue de alguna manera cambiar el órden del código, en los argumentos utilicé args, y en vez de usar el range en la función, lo utilicé como la variable a la que se le iba a hacer la definición.
```python
#8-1
def cuadrado(*args):
  cuadrado=a**2
  print(f"{a} - {cuadrado}")

for a in range(1,101):
  cuadrado(a)
```
* En el punto 4 del reto 8 hice practicamente lo mismo que en el punto 3, fue poner un args en vez del argumento.
```python
#8-4
def calcular_factorial(*args):
  for i in args:
    factorial = 1
    for i in range(1, n + 1):
      factorial *= i
  return factorial
  
n=int(input("Ingrese un número: "))
factorial= calcular_factorial(n,a)
print(factorial)
```
## Punto 3
Escriba una función recursiva para calcular la operación de la potencia.
En la función definí dos argumentos, x que seria el número base y n que serí la potencia. Como caso base puse 1, porque culaquier número elevado a 1 va a ser el mismo número. En la condición hice que se multiplicara po si misma, pero con *n-1*. Y por último mande que la función se ejecutara.
```python
def potencia_recursiva(n : int, x:float )-> int:
  if n == 1:
    # caso base
    return x
  else:
    # condicion
    return x*potencia_recursiva(n-1,x)

if __name__ == "__main__":
  n = int(input("Ingrese numero: "))
  x= float(input("Ingrese un número: "))
  potencia = potencia_recursiva(n,x)
  print(f"El resultado de {x}^{n} = {potencia}")
```
## Punto 4
Utilice la siguiente plantilla de code para contar el tiempo.
- Prueba con fibonachi iterativo:
```python
import time

start_time = time.time()
def fibo(n : int )-> int:
  i : int = 1
  # caso base
  n1 : int = 0
  n2 : int = 1
  while(i <= n):
    # Condicion
    sumFibo = n1 + n2
    print(sumFibo)
    # Actualizacion
    n1 = n2
    n2 = sumFibo
    i += 1
  return sumFibo

if __name__ == "__main__":
  num = 10
  serieFibo = fibo(num)
  print("La serie de Fibonacci hasta " + str(num) + " es " + str(serieFibo))
end_time = time.time()

timer = end_time - start_time
print(timer)
```
- Prueba fibonachi recursivo:
```python
import time

start_time = time.time()
def fiboRecursivo(n : int )-> int:
  if n <=1:
    # caso base
    return 1
  else:
    # condicion
    return fiboRecursivo(n-1)+fiboRecursivo(n-2)  

if __name__ == "__main__":
  num = 10
  serieFibo = fiboRecursivo(num)
  print("La serie de Fibonacci hasta " + str(num) + " es " + str(serieFibo))
end_time = time.time()

timer = end_time - start_time
print(timer)
```
* Hay que decir que la diferencia de tiempo es de más o menos 0,0072 segundos que no es muy significativo, pero aún asi demuestra que para este caso la recursividad es más rápida que la iteración.
* Para calcular el número de iteraciones que se deben hacer tomé  1 cómo el tiempo significativo y con  una función while mientras que se va iterando con `n+1`, si el tiempo es mayor o  igual que 1 para e imprime la n.
```python
import time
def fiboRecursivo(n : int )-> int:
  if n <=1:
    # caso base
    return 1
  else:
    # condicion
    return fiboRecursivo(n-1)+fiboRecursivo(n-2)
def tiempo(n):
  start_time = time.time()
  fiboRecursivo(n)
  end_time = time.time()

  timer = end_time - start_time
  return timer

n=1
tiempo:float= tiempo(n)
print(tiempo)
while tiempo <= 1:
  n+=1
  print(n)
```
# Punto 5
![image](https://github.com/mvarelau/Ya_no_quiero_ser_adulta/assets/141885396/21199e14-e404-4972-98db-1a30476dd4fd)
La verdad si está bien útil crear una cuenta en esta pagina, o red social o twiter de gente bien pila. Es muy facil resolver cualquier duda que se tenga en cuanto a un código, o en general en cuanto a lenguages de programación y tecnología.
# Punto 6 
![image](https://github.com/mvarelau/Ya_no_quiero_ser_adulta/assets/141885396/d40c9059-f642-4ce5-9403-c0a293e0ecc8)
https://www.linkedin.com/in/maria-alejandra-varela-u%C3%B1ate-29381b296/
Me siento genial jajajaja, tuve que buscar una foto de mi grado porque me puse a mirar las fotos de los demás perfiles y esa es la más cercana que tengo a algo profecional. Uno realmente no se da cuenta de la importancia de la experiencia laboral hasta que empieza a buscar trabajo, asi que si es muy bueno estar metida en ese mundo desde ya, asi no sea para conseguir trabajo, pero si para aprender más de ese mundo.



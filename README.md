# Reto_5

### Solucion ejercicios 

#### 1. Dado la figura de la imagen, desarrolle:

![image](https://github.com/user-attachments/assets/c27cd13c-7673-4ab1-b41e-6fa2440316b3)

#### - Una función matemática para calcular el volumen y el área superficial.
#### - Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r1, r2 y h.
#### - Revise como utilizar el valor de pi usando import math y math.pi

```
import math

def calcular_volumen(r1: float, r2: float, h: float) -> float:
    volumen_esfera = (4/3) * math.pi * r1**3
    volumen_cono = (1/3) * math.pi * h * (r1**2 + r1*r2 + r2**2)
    return volumen_esfera + volumen_cono

def calcular_area_superficial(r1: float, r2: float, h: float) -> float:
    area_esfera = 2 * math.pi * r1**2  
    l = math.sqrt((r2 - r1)**2 + h**2)  
    area_lateral_cono = math.pi * (r1 + r2) * l
    area_base_cono = math.pi * r2**2
    return area_esfera + area_lateral_cono + area_base_cono

if __name__ == "__main__":
    r1 = float(input("Ingrese el radio r1 de la esfera y base del tronco de cono: "))
    r2 = float(input("Ingrese el radio r2 de la parte superior del tronco de cono: "))
    h = float(input("Ingrese la altura h del tronco de cono: "))

    volumen_total = calcular_volumen(r1, r2, h)
    area_total = calcular_area_superficial(r1, r2, h)

    print(f"\nVolumen total de la figura: {volumen_total:.2f} unidades cúbicas")
    print(f"Área superficial total de la figura: {area_total:.2f} unidades cuadradas")
```

#### 2. Dado la figura de la imagen, desarrolle:

![image](https://github.com/user-attachments/assets/6b216233-eb3a-4dc6-8f79-360c40a8c398)

#### -Una función matemática para calcular el área y el perimetro.
#### -Cree dos funciones en python para calcular los valores antes establecidos, al ingresar por teclado r, a y b.
#### -Revise como utilizar el valor de pi usando import math y math.pi

```
import math

def calcular_area(a: float, b: float, r: float) -> float:
    area_rectangulo = a * b
    area_circulo = math.pi * r**2
    return area_rectangulo + area_circulo

def calcular_perimetro(a: float, b: float, r: float) -> float:
    perimetro_vertical = 2 * a
    perimetro_inferior = b
    perimetro_circulo = 2 * math.pi * r
    return perimetro_vertical + perimetro_inferior + perimetro_circulo

if __name__ == "__main__":
    r = float(input("Ingrese el radio r de los extremos semicirculares: "))
    a = float(input("Ingrese la altura a del rectángulo: "))
    b = float(input("Ingrese el ancho b del rectángulo: "))

    area_total = calcular_area(a, b, r)
    perimetro_total = calcular_perimetro(a, b, r)

    print(f"\nÁrea total de la figura: {area_total:.2f} unidades cuadradas")
    print(f"Perímetro total de la figura: {perimetro_total:.2f} unidades")
```

#### 3. Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.

```
def calcular_carne_aves(n: int, m: int, k: int) -> int:
    return n * 6 + m * 7 + k * 1

if __name__ == "__main__":
    n = int(input("Ingrese la cantidad de gallinas: "))
    m = int(input("Ingrese la cantidad de gallos: "))
    k = int(input("Ingrese la cantidad de pollitos: "))

    total_kilos = calcular_carne_aves(n, m, k)
    print(f"\nLa cantidad total de carne es: {total_kilos} kilos")
```

#### 4 Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.

```
def calcular_prestamo_compuesto(c: float, i: float, n: int) -> float:
    return c * (1 + i)**n

if __name__ == "__main__":
    c = float(input("Ingrese el monto del préstamo (capital): "))
    i = float(input("Ingrese la tasa de interés mensual (en porcentaje): "))
    n = int(input("Ingrese la cantidad de meses: "))

    # Convertimos el porcentaje a decimal
    tasa_decimal = i / 100

    valor_final = calcular_prestamo_compuesto(c, tasa_decimal, n)
    print(f"\nEl valor total a pagar después de {n} meses es: {valor_final:.2f} ")
```

#### 5 Escriba un programa que pida 5 números reales y calcule las siguientes operaciones usando una función para cada una:

#### -El promedio
#### -El promedio multiplicativo (multilplica todos y luego calcula la raíz de la cantidad de operandos)
#### -La potencia del mayor número elevado al menor número
#### -La raíz cúbica del menor número

```
import math

def promedio(numeros: list) -> float:
    return sum(numeros) / len(numeros)

def promedio_multiplicativo(numeros: list) -> float:
    producto = 1
    for num in numeros:
        producto *= num
    return producto ** (1 / len(numeros))

def potencia_mayor_al_menor(numeros: list) -> float:
    mayor = max(numeros)
    menor = min(numeros)
    return mayor ** menor

def raiz_cubica_menor(numeros: list) -> float:
    menor = min(numeros)
    return menor ** (1/3)

if __name__ == "__main__":
    numeros = []
    for i in range(5):
        num = float(input(f"Ingrese el número {i+1}: "))
        numeros.append(num)

    prom = promedio(numeros)
    prom_mult = promedio_multiplicativo(numeros)
    pot_mayor_menor = potencia_mayor_al_menor(numeros)
    raiz_cubica = raiz_cubica_menor(numeros)

    print(f"\nPromedio: {prom:.2f}")
    print(f"Promedio multiplicativo: {prom_mult:.2f}")
    print(f"Potencia del mayor elevado al menor: {pot_mayor_menor:.2f}")
    print(f"Raíz cúbica del menor número: {raiz_cubica:.2f}")
```

#### 6 Consultar qué es y cómo funciona pip en python.

##### pip es el gestor de paquetes oficial de Python. Sirve para instalar, actualizar y desinstalar paquetes o librerías que no vienen integradas en la instalación estándar de Python.
##### Para usar pip, se conecta a PyPI (Python Package Index), que es un repositorio online donde se almacenan miles de paquetes. pip descarga el paquete que le indiques e instala todos sus archivos en tu sistema.

#### 7 Hacer un listado de módulos populares para python que se puedan instalar com pip.

```
| Módulo           | ¿Para qué sirve?                                           | Cómo instalarlo                             |
| ---------------- | ---------------------------------------------------------- | ------------------------------------------- |
| `numpy`          | Cálculo numérico y matrices (matemáticas)                  | `pip install numpy`                         |
| `pandas`         | Análisis y manipulación de datos en tablas                 | `pip install pandas`                        |
| `matplotlib`     | Graficar datos (barras, líneas, tortas, etc.)              | `pip install matplotlib`                    |
| `seaborn`        | Visualización estadística (basado en `matplotlib`)         | `pip install seaborn`                       |
| `scikit-learn`   | Machine Learning (clasificación, regresión, clustering...) | `pip install scikit-learn`                  |
| `requests`       | Hacer solicitudes HTTP (APIs, web scraping básico)         | `pip install requests`                      |
| `flask`          | Crear aplicaciones web simples                             | `pip install flask`                         |
| `django`         | Framework web robusto para apps grandes                    | `pip install django`                        |
| `beautifulsoup4` | Extraer datos de páginas web (web scraping)                | `pip install beautifulsoup4`                |
| `openpyxl`       | Leer y escribir archivos de Excel (.xlsx)                  | `pip install openpyxl`                      |
| `PyPDF2`         | Leer archivos PDF                                          | `pip install PyPDF2`                        |
| `pygame`         | Crear videojuegos en 2D con Python                         | `pip install pygame`                        |
| `tkinter`        | Interfaz gráfica de usuario (GUI) – ya viene con Python    | *(no se instala con pip, ya está incluido)* |
| `pyautogui`      | Automatización del mouse y teclado                         | `pip install pyautogui`                     |
```


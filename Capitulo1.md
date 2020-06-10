# **Sistemas Numericos y codigos**

## 1.1 Sistema Binario, octal y hexadecimal 

### ¿Que es un sistema numerico?

Un sistema numerico es un **conjunto de caracteres y reglas**, las cuales son utilizadas para **representar cantidades o datos numericos**.

### ¿Que es la base de un sistema numerico?
Es la **cantidad de digitos** que tiene el sistema por ejemplo:
- **Sistema Binario**: Tiene **dos** digitos (0, 1)
- **Sistema Octal**: Tiene **ocho** digitos (0, 1, 2, 3, 4, 5, 6, 7)
- **Sistema Decimal**: Tiene **diez** digitos (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
- **Sistema Hexadecimal**: Tiene **dieciseis** digitos compuestos por 9 numeros y 6 letras del alfabeto (0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F)

> **Nota**: En el sistema Hexadecimal las letras tienen la siguiente equivalencia. A => 10, B => 11, C => 12, D => 13, E => 14, F => 15

### ¿Como se representan los numeros en los sistemas numericos?

Basicamente los numeros tienen **dos representaciones** las cuales son: Notacion Posicional y Notacion Polinomial

![](/images/m1.png)
- **Notacion Posicional**: En esta forma de representar las cantidades cada digito posee un valor dependiendo de su posicion relativa es decir lo que conocemos como unidad, decena, centena, etc. Ejemplo:
    - 555 = En este numero el 5 toma diferentes valores (500, 50, 5) esto se debe a sus posiciones

- **Notacion Polinomial**: En la notacion polinomial lo que tenemos es una sumatoria de los digitos multiplicados por la base elevada a la posicion.
    - (110.01) => 1*(2)^2 + 1*(2)^1 + 0*(2)^0 + 0*(2)^-1 + 1*(2)^-2

## 1.2 Conversion de los sistemas 
Los metodos acontinuacion toman como referencia a la base 10 o base decimal ya que es el sistema numerico que usamos habitualmente. Existen dos metodos de conversion los cuales son:
- **Metodo de Sustitucion**: Este metodo se lo utiliza para convertir de **cualquier** base a base **decimal** similar a la **Notacion Polinomial**. 

``` markdown
Ejemplos
    - (342.2)(8) = 3*(8)^2 + 4*(8)^1 + 2*(8)^0 + 2*(8)^-1 == (226.25)(10)
    - (101001.111)(2) = 1*(2)^5 + 0*(2)^4 + 1*(2)^3 + 0*(2)^2 + 0*(2)^1 + 1*(2)^0 + 1*(2)^-1 + 1*(2)^-2 + 1*(2)^-3 == (41.875)(10) 
```

- **Metodo por Multiplicaciones y Divisiones Sucesivas**: Este metodo se lo usa para llevar de base **decimal** a **cualquier** base. El metodo consiste en dos partes, transformar la parte entera y transformar la parte decimal.
    - Parte Entera: 
        1. En el dividendo colocamos la parte entera del numero en base decimal.
        2. En el divisor colocamos la base del sistema al que queremos llevar.
        3. Realizamos la division.
        4. El cociente lo volvemos a dividir por la base del sistema que queremos llevar asi hasta llegar a 0
        5. El residuo es nuestro nuevo numero en la base deseada
    - Parte Fraccionaria:
        1. Multiplicamos la parte fraccionaria por la base a la que queremos convertir.
        2. Al resultado le hacemos un split(.) repetimos desde el paso 1 con la parte fraccionaria asi hasta llegar a 0.
> **Ejemplo Parte Entera**
![](/images/M2.png)

> **Ejemplo Parte Fraccionaria**
![](/images/m3.png)

### Casos Especiales 
cuando A y B son potencias de la misma Base 
- (N)(A) => (N)(B)    ;     B = A^n ; **A < B**
    1. Formamos grupos de n elementos en (N)(A) en caso de no ser posible rellenamos con "0"
    2. Cada grupo lo reemplazamos por el correspondiente valor en la otra base (Uso de Tabla)

- (N)(A) => (N)(B) ; A = B^n ; **A > B**
    1. Reemplazamos cada digito en (N)(A) por su correspondiente n digitos en base B. ¿Que pasa si n es menor o mayor al valor correspondiente? creo que nunca va a pasar  

> **Nota 1:** Los casos mencionados anteriormente funcionan bien para transformar desde sistema binario a (octal y hexadecimal) y viceversa. 

> **Nota 2:** Si queremos transformar de octal a hexadecimal o viceversa debemos primero transformar al sistema binario y de ahi pasarlo al sistema deseado siempre.

## 1.3 Sumas y Restas de Numeros en Diferentes Bases 

- **Suma** Se realiza de la manera tradicional cuando llegas al ultimo numero del sistema numerico **"llevas uno"** el mismo que es agregado a la siguiente seccion.

> **Nota:** El ultimo numero de cada sistema es: el 9 en el sitema decimal, el 1 en el sistema binario, el 7 en el sistema octal, y la F en el sistema Hexadecimal. Luego de llegar a cualquiera de esos numeros regresamos al inicio que en todos los casos es el mismo el 0 y **"llevamos uno"**

- **Resta** Se realiza algo diferente del metodo tradicional 
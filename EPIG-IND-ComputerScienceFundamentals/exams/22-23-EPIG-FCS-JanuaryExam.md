# Exam Computer Science Fundamentals 17th January 2023

1. Sean x, y, z tres variables booleanas del lenguaje Python. A) Escríbase
   una condición en ese lenguaje que sea verdadera (True) exactamente cuando
   dos cualesquiera de ellas sean iguales y diferentes de la tercera. B) Niéguese la
   expresión obtenida y simplifíquese hasta que desaparezcan las negaciones, las
   que afecten a operadores relacionales sustitúyanse cambiado el operador al
   complementario. Simplifíquese la expresión al máximo
   ```text







   ```

2. Exprésense, mediante una cadena de igualdades (comentando el
   cometido de cada una) todaslas transformaciones que realiza un ordenador que
   represente los números enteros negativos con un byte para calcular la
   operación 5 - 8
   ```text
    5 – 8 (se transforman a la representación en binario adecuada) = ...






   ```

3. Dado el siguiente trozo de código, rellena la tabla con el valor de las variables al finalizar cada iteración.
   Rellena los huecos que consideres necesarios en función del número de iteraciones que realiza el bucle

    ```python
    a = 7; b = a
    c = 4
    cond= False
    while not(cond):
       b- = 2
       c+ = 1
       cond = (a%(b+c) == 0)
    ```
    
    |          | inicio | it1 | it2 | it3 | it4 | it5 |
       |:--------:|:------:|:---:|:---:|:---:|:---:|:---:|
    |  **a**   |   7    |     |     |     |     |     |
    |  **b**   |   7    |     |     |     |     |     |
    |  **c**   |   4    |     |     |     |     |     |
    | **cond** | False  |     |     |     |     |     |

4. Se tienen las siguientes variables: a= [['A', 'B'], ['C', 'D']], b= '3', c= 1,
   d= [b, 'abc', float(b)]. Para cada expresión de la tabla siguiente, indica si es
   correcta o no. Si lo fuera indica el resultado y su tipo, y si es incorrecta indica
   brevemente por qué:

   | Expresión      | ¿Correcta? | Tipo y resultado / Modificación / Causa del error | 
             |----------------|------------|---------------------------------------------------|
   | `a[::-1]`      |            |                                                   |
   | `a*b`          |            |                                                   |
   | `a[0][c]`      |            |                                                   |
   | `b**c` |            |                                                   |
   | `int(b)*len(d[1])`    |            |                                                   |

5. Defínanse las siguientes funciones:
    1. `media_aritmetica()`: calcula la media aritmética de los números que
       hay en una lista que recibe como argumento. Devuelve la media calculada.
       **NOTA:** No se pueden utilizar las funciones sum() y len()en el cálculo de la
       media.
    2. `valor_minimo()`: los argumentos son una lista y un número n. La
       función modifica todos los elementos de la lista que sean menores que n,
       haciendo que sean iguales a n. Devuelve el total de modificaciones realizadas.

    3. `cadena_simetrica()`: el argumento de entrada es una cadena.
       Devuelve otra cadena el doble de larga, y con simetría especular. Por ejemplo,
       si “12345” es la cadena que recibe, devuelve “1234554321”
    4. `total_lineas()`: el argumento es el nombre de un fichero. Devuelve
       la cantidad de líneas que tiene el fichero

        ```python
        #Solve the exercise here
        
  
  
  
  
  
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
  
  
          ```


6. Usando las funciones del ejercicio 5, escribir un programa que lea
   números reales de un fichero (con un número por línea), cuyo nombre se
   demandará por teclado, los introduzca en una lista y calcule su media. Luego
   pedirá, por teclado, un número mínimo que hará de corte, calculará cuántos de
   la lista no alcanzan ese mínimo y mostrará la lista modificada con ese valor
   mínimo sustituyendo a los valores originales menores que él. El programa
   debería dar una respuesta como la siguiente:
      ```console
        Dame el nombre del fichero con los datos: Numeros 
        Dame el valor mínimo de la lista: 10 
        La lista [3.0, 4.0, 72.0, 9.0, 45.3, 34.0] tiene una media de: 
        27.883333333333336 
        Y, por debajo de 10.0 tenía 3 datos 
        La lista queda: [10.0, 10.0, 72.0, 10.0, 45.3, 34.0]
   ```

    ```python
    #Solve the exercise here
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    ```

NOTA previa: en las preguntas siguientes, tipo V/F, dos errores invalidan un acierto.

7. Conteste V o F según corresponda:

    - [ ] Los HDDs tienen partes mecánicas en movimiento que les permiten acceder
      a los datos en menos tiempo que los SSDs.
    - [ ] La CPU está compuesta por la unidad aritmeticológica, la unidad de control
      y una serie de registros de almacenamiento.
    - [ ] La principal diferencia entre un servidor y un ordenador personal es que el
      primero dispone de menos recursos computacionales (disco, memoria, CPU,
      etc.).
    - [ ] El software de aplicación es el que utilizan los operadores para controlar un
      proceso industrial específico, basándose en mediciones de diferentes
      variables de proceso.

8. Conteste V o F según corresponda:

    - [ ] Los sistemas empotrados son sistemas informáticos de propósito general
      que están integrados en un sistema de ingeniería más general, como el
      computador de a bordo de un automóvi.
    - [ ] El bootloader se encarga de localizar los diferentes sistemas operativos
      disponibles en un ordenador y cargar el núcleo del sistema seleccionado por
      el usuario, en el caso de disponer de varios.
    - [ ] El anti-spyware combate activamente las infecciones informáticas por virus
      de forma similar a un antivirus.
    - [ ]  Desde la perspectiva del hardware, el sistema operativo es responsable de
      proporcionar una interfaz entre el usuario y la computadora.

9. En una empresa dedicada al reacondicionamiento de dispositivos
   electrónicos es necesario mantener una base de datos con las operaciones que
   hay que realizar a los mismos, quien las va a realizar y que materiales se
   necesitan. Un ejemplo de operación sería cambiar la pantalla y entre otras cosas,
   para esta operación uno de los materiales es la pantalla en sí misma, por ejemplo.
   La información que se almacena en la base de datos es la siguiente:

    - Clientes: razón social y teléfono
    - Dispositivos: modelo, número de serie, cliente
    - Encargados: nombre, apellidos
    - Operaciones: denominación, horas, encargado
    - Material: denominación

      Un cliente puede enviar varios dispositivos, cada dispositivo es enviado por un
      solo cliente.

      Un dispositivo puede requerir varias operaciones y una misma operación puede
      ser requerida por varios dispositivos.

      Una operación puede requerir cierto material para su realización y el mismo
      material puede ser necesario para varias operaciones.

      Un encargado puede ocuparse de varias operaciones, estas solo son realizadas
      por un encargado.

      Se pide el diseño de la base de datos de acuerdo con los contenidos teóricos
      impartidos, incluyendo el tipo de cada relación (1:n, n:n) y clave (PK/FK).

      **NOTA: Es posible que sean necesarias tablas adicionales o añadir campos a las tablas para relacionarlas.**

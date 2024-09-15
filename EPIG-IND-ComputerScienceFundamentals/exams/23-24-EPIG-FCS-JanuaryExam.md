# Exam Computer Science Fundamentals 9th January 2024

1. Sean x e y dos variables enteras (int) del lenguaje Python. 1.1) Obténgase una condición en ese lenguaje que sea
   verdadera (True) si y solo si las dos variables, x e y, son opuestas en signo y no nulas. 1.2) Niéguese la condición
   obtenida y aplíquense las Leyes de De Morgan, y las que fuesen necesarias, hasta obtener una expresión sin negaciones
   que habrán quedado absorbidas en última instancia por el paso a los operadores relacionales complementarios
   ```text
   
   
   
   
   
   
   
   ```

2. Desarróllense las transformaciones y cálculos que realizaría un ordenador que representase los números enteros con un
   byte para realizar la resta: 12 – 17 y, finalmente, proporcionar su resultado en base decimal
   ```text
   
   
   
   
   
   
   
   ```

3. Dado el siguiente trozo de código, rellena la tabla con el valor de las variables al finalizar cada iteración.
   Rellena los huecos que consideres necesarios en función del número de iteraciones que realiza el bucle

   ```python
   c = "3."
   a = 10
   b = 0
   d=len(c)
   while d < 5:
     c += str (a // 7)
     b = a % 7
     a = int(str(b) + '0')
     d = len(c)
   ```
   
   |       | inicio | it1 | it2 | it3 | it4 | it5 |
   |-------|--------|-----|-----|-----|-----|-----|
   | **a** | 10     |     |     |     |     |     |
   | **b** | 0      |     |     |     |     |     |
   | **c** | "3."   |     |     |     |     |     |
   | **d** | 2      |     |     |     |     |     |

4. Se tienen las siguientes variables: a=4, b= '3', c= [‘A’,3,2.5, a], d= 3.0. Para cada expresión de la tabla
   siguiente, indica si es correcta o por si el contrario, daría un error en su ejecución. Indique en caso de error la
   causa de este:
   
   | Expresión    | ¿Correcta? | Tipo y resultado / Causa del error |
   |--------------|------------|------------------------------------|
   | `c[-2:]`     |            |                                    |
   | `d/b`        |            |                                    |
   | `d>=len(c)`  |            |                                    |
   | `float(b)+d` |            |                                    |
   | `b*c.pop()`  |            |                                    |

5. El año 2023 ha sido el más caluroso desde que se tienen registros en muchas zonas del planeta. El ayuntamiento de
   Gijón tiene un sensor en el Monte Deva que lleva midiendo la temperatura de la ciudad desde 1975, no obstante, se
   sabe que en ocasiones el sensor da medidas erróneas. Se nos pide un programa que se capaz de “limpiar” esos datos
   para poder usarlos. Para ello se piden las siguientes funciones:

    1. `prepare_data()` recibe una lista de temperaturas (["15ºC”,”12.3ºC”,”6ºC”, …]) y retorna otra lista de flotantes
       con el valor numérico de la temperatura (`[15.0,12.3,6.0…]`).
    2. `detect_outlayers()` que reciba una lista de flotantes y un valor límite y retorne las posiciones de la lista que
       están por encima de ese valor
    3. `calculate_avg()` recibe una lista de flotantes y las posiciones en las que existen valores erróneos, debe de
       retornar la media de los valores correctos
    4. `sanitize_data()` recibe una lista de temperaturas (`[”12.3ºC”,”9ºC”…]`) y un valor límite, debe de utilizar las
       funciones implementadas en los apartados A-C para sustituir aquellos valores que sobrepasen el valor límite dado
       por el promedio de las temperaturas.

   ```python
   #Solve the exercise here










































   
   ```

6. Usando las funciones del ejercicio anterior, escribir un programa que lea temperaturas de un fichero (una temperatura
   por línea), sustituya aquellas que superen un límite (introducido por teclado) por su promedio, las formatee
   adecuadamente y las vuelva a guardar en otro fichero (salida.txt). El programa debería dar una respuesta como la
   siguiente:

   entrada.txt:

   ```txt
   12.0ºC
   231ºC
   15.0ºC
   55ºC
   ```

   salida.txt:
   
   ```txt
   12.0ºC
   13.5ºC
   15.0ºC
   13.5ºC
   ```

   Salida por consola:

   ```shell
   > Dame el límite (threshold): 
   46.0
   > Se han limpiado los datos!
   ```

   ```python
   #Solve the exercise here





































   
   ```

NOTA previa: en las preguntas siguientes, tipo V/F, dos errores invalidan un acierto.

7. Conteste V o F según corresponda:

   - [ ] Los HDDs tienen partes mecánicas en movimiento y presentan unas velocidades de lectura-escritura mucho menores que
     los SSDs.
   - [ ] La CPU se comunica con los diferentes periféricos/memoria a través de ondas electromagnéticas (Wi-Fi).

   - [ ] La evolución de los dispositivos de almacenamiento externo, CD, DVD y Blue-ray fue debida a la introducción
     sucesiva en la grabación de láseres con rayo cada vez más fino, para el primero rojo y para el último azul

   - [ ] El software de aplicación es el que utilizan los operadores para controlar un proceso industrial específico,
     basándose en mediciones de diferentes variables de proceso.

8. Conteste V o F según corresponda:

   - [ ] Los sistemas operativos en tiempo real se utilizan principalmente en aplicaciones donde la interacción con el
     usuario es más crítica que el procesamiento de datos.
   - [ ] La gestión de memoria en los sistemas operativos modernos permite que varios programas se ejecuten
     simultáneamente, aunque la memoria física sea menor que la requerida para todos los programas.
   - [ ] Los sistemas operativos modernos no requieren controladores de dispositivos específicos para interactuar con el
     hardware
   - [ ] La seguridad de los sistemas operativos depende exclusivamente de software de terceros, como antivirus y
     cortafuegos

9. Una empresa dedicada a la gestión de tráfico ferroviario requiere una base de datos con los diferentes trayectos que
   realizan los trenes, qué maquinistas los realizan y qué pasajeros viajan en esos trayectos. La información que se
   almacena en la base de datos es la siguiente:

   - Trenes: modelo, año de fabricación y ancho
   - Trayectos: hora de salida, hora d llegada, estación de origen y estación de destino.
   - Maquinistas: nombre, apellidos, licencia y DNI
   - Pasajeros: nombre, apellidos y DNI
   - Billetes: precio y clase

   Un pasajero puede tener varios billetes, cada billete pertenece a un único pasajero.
   
   Un tren realiza múltiples trayectos, que a su vez son realizados por un único tren.
   
   Un billete puede incluir varios trayectos, a su vez los trayectos pueden realizarse con varios billetes.

   Un maquinista puede realizar varios trayectos, a su vez los trayectos pueden ser realizados por varios maquinistas.
 
   **Se pide el diseño de la base de datos de acuerdo con los contenidos teóricos impartidos, incluyendo el tipo de cada
   relación (1:n, n:n) y clave (PK/FK).**
   
   **NOTA: Es posible que sean necesarias tablas adicionales o añadir campos a las tablas para relacionarlas**



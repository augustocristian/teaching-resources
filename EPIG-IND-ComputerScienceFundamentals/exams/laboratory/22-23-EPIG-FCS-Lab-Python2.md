# Laboratory Exam Python (All) Computer Science Fundamentals 15th December 2022

1. Se nos ha encargado crear un programa que calcule la calificación de la
   asignatura de Fundamentos de Informática y genere en ficheros separados cada grupo.
   Se debe de crear una función que tome por parámetro la ruta de un fichero CSV con las
   calificaciones de las partes de teoría y práctica, así como otros datos de los alumnos
   (UO, Correo, Nombre, Sexo, Grupo de PL, calificación PL, Calificación Teoría). El
   programa debe de:
    1. Calcular la nota de la asignatura (50% prácticas, 50% teoría, si no se llega a la nota mínima de 4 en alguna de
       las partes, figurará un 4.0), añadirla al final
    2. Determinar que partes tiene el alumno suspensas (formato libre), añadirla a continuación de la nota.
    3. Guardar en distintos ficheros CSV los alumnos, atendiendo a su grupo de laboratorio (nombrar los ficheros
       resultsgroup X.csv siendo X la letra del grupo al que pertenecen). En estos ficheros deben de tener el contenido
       del fichero original, además de la nota y partes suspensas.

   Contenido del CSV:

   ```csv
   UO289025;UO289025@uniovi.es;Kelsey Hernandez;male;group A;3.9;7
   UO263862;UO263862@uniovi.es;Susan Sutton;female;group A;4;2
   UO252897;UO252897@uniovi.es;Robert Strickland;male;group E;5.9;6
   UO286370;UO286370@uniovi.es;Jacob Wu;male;group A;7.7;7.8;
   ```
   Ejemplo de uno de los ficheros de salida (resultsgroupA.csv):

   ```csv
   UO289025;UO289025@uniovi.es;Kelsey Hernandez;male;group A;3.9;7;4;pl
   UO263862;UO263862@uniovi.es;Susan Sutton;female;group A;4; 2;3;all
   UO286370;UO286370@uniovi.es;Jacob Wu;male;group A;7.7;7.8;7.75;
   ```

2. Se nos ha encargado implementar el juego de buscar parejas, para ello se nos
   pide crear una serie de funciones:
    1. Función `imprimematriz()`, recibe como parámetro una matriz y la muestra por pantalla estructurada (véase los
       ejemplos)
    2. Función `imprimejugada()`, recibe como parámetros dos matrices, una con un tablero vacío (lleno de
       caracteres “?”) y otra con la solución (codificada con caracteres, véase parte derecha del ejemplo) y la posición
       de dos elementos de la matriz (AX, AY, Bx, BY). La función debe de mostrar el contenido del tablero vacío,
       excepto las dos posiciones que se especifican, en las cuales mostrará el contenido de la matriz solución.
    3. Función `continuajuego()` recibe como parámetro una matriz y retornará Verdadero si en alguna de sus posiciones
       hay un “?” y Falso en caso contrario.
    4. Función `jugada()` vuelve a recibir como parámetro las matrices tablero vacío y solución, así como la posición de
       dos elementos de la matriz. La función debe de imprimir la jugada y en el supuesto de que las posiciones
       especificadas contengan el mismo carácter en la matriz solución, modificar el tablero vacío con sus valores y
       retornarlo, en cualquier caso.
    5. Implementar la función `juegocartas()`, esta función debe tomar por teclado dos posiciones a mostrar en la matriz
       siguiendo el formato “NM”, comprobar si son iguales y modificar el tablero en caso afirmativo y repetir esto
       hasta que el usuario haya ganado (haya encontrado todas las parejas).
   
   **Tablero inicial:**
   ```console
   [["?", "?", "?", "?"],
   ["?", "?", "?", "?"],
   ["?", "?", "?", "?"],
   ["?", "?", "?", "?"]]
   ```
   **Solución:**
   ```console
   SOLUCIÓN:
   [["A", "D", "B", "D"],
   ["E", "A", "F", "G"],
   ["G", "H", "B", "I"],
   ["F", "I", "E", "H"]]
   ```
   **Salida por pantalla:**
   ```console
   Dame la primera posición
   1-1
   Dame la segunda posición
   1-2
   ? ? ? ?
   ? A F ?
   ? ? ? ?
   ? ? ? ?
   Dame la primera posición
   0-0
   Dame la segunda posición
   1-1
   A ? ? ?
   ? A ? ?
   ? ? ? ?
   ? ? ? ?
   Dame la primera posición
   1-3
   Dame la segunda posición
   3-1
   A ? ? ?
   ? A ? G
   ? ? ? ?
   ? I ? ?
   
   ```
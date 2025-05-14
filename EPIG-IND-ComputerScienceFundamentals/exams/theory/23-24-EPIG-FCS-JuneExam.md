# Exam Computer Science Fundamentals 20th June 2024

1. Sean x, y, dos variables enteras (int) del lenguaje Python.
    1. Obténgase una condición en ese lenguaje que sea verdadera (True) si y solo si se verifica que x no es divisible
       por 7 e y toma el valor ASCII correspondiente al carácter A.
    2. Si fuese posible, simplifíquese la condición obtenida hasta obtener una expresión sin negaciones que, en última
       instancia, habrían quedado absorbidas por la adopción de los operadores relacionales complementarios.

       ```text
 
 
 
 
 
 
 
       ```

2. Proporciónese, con argumentación, el mayor entero con signo que se puede representar en un sistema que reserva 8 bits
   para cada uno.

   ```text







   ```

3. Dado el siguiente trozo de código, rellena la tabla con el valor de las variables al finalizar cada iteración del
   bucle while. Rellena los huecos que consideres necesarios en función del número de iteraciones que realiza el bucle

    ```python
    a = 4
    b = 0
    for i in range(1, 4):
      while a%i==0 and a>0:
        f=a//i
        a-=1
        b+=a+f
   ```

   |       | inicio | it1 | it2 | it3 | it4 | it5 |
   |-------|--------|-----|-----|-----|-----|-----|
   | **a** |        |     |     |     |     |     |
   | **b** |        |     |     |     |     |     |
   | **f** |        |     |     |     |     |     |

4. Se tienen las siguientes variables: a = 'amor', b = [1, ’es’, 3.5], c = 7. Para cada expresión de la tabla siguiente,
   indica si es correcta o por si el contrario, daría un error en su ejecución. Indíquese el tipo y resultado o la
   modificación de la lista o en caso de error la causa de este:

   | Expresión          | ¿Correcta? | Tipo y resultado / Modificación / Causa del error |
                               |--------------------|------------|---------------------------------------------------|
   | `a[::-1]`          |            |                                                   |
   | `a.append(str(b))` |            |                                                   |
   | `a * b[2]`         |            |                                                   |
   | `c**(1/2)`         |            |                                                   |
   | `int(c/b[2])`      |            |                                                   |


5. Llagares Norniella y Hermanos nos ha encargado la implementación de un software para automatizar las tolvas que
   mezclan los diferentes tipos de manzana para la elaboración de sidra. Se nos solicita lo siguiente:
    1. Crear una función processApplePalet() que reciba un valor flotante representando una cantidad de manzanas en
       gramos y
       una cadena indicando la unidad de medida deseada. La función debe retornar la cantidad de manzanas en libras ("
       lb"),
       kilogramos ("kg"), toneladas ("tn") o toneladas imperiales ("UKtn"), según la unidad proporcionada.
    2. Crear una función filterVerdialona() que reciba como parámetros dos listas: la primera contiene el peso
       individual de
       cada manzana (flotante) en gramos y la segunda su grado de acidez o pH (flotante). La función debe retornar una
       lista
       con las posiciones de las manzanas del tipo "Verdialona" que son aquellas cuyo pH < 4 y su peso está entre 150g y
       210g. Además, debe mostrar en pantalla la siguiente información para cada manzana: posición en la lista, grupo de
       acidez (ácida, neutral o alcalina) y su peso.
    3. Usando convenientemente las funciones anteriores, implementar un código que, con las siguientes dos listas
       constantes, [210,167,400,155,160] y [3,2,2,3,6], una con los pesos en gramos y otra con los grados de acidez
       correspondientes al mismo conjunto de manzanas y en el mismo orden, sume por un lado el peso de las manzanas de
       tipo
       “Verdialona”, y por otro lado las del resto de tipos (otras). Debe de mostrar ambos totales con dos decimales, en
       la
       unidad que también habrá demandado al usuario cerciorándose de que haya sido correcta. Las unidades consideradas
       serán: lb (libras), kg (kilogramos), tn  (toneladas métricas) y UKtn (toneladas inglesas).

   **Nota**:  1tn = 1000kg, 1lb = 0.45kg, 1 UKtn = 1.016 tn. Clasificación del pH: pH < 4 → ácida, 4 ≤ pH < 9 → neutral,
   pH > 9 → alcalina.

   Por ejemplo, elegida lb como unidad, la salida esperada será semejante a:
    ```console
    > Hay un total de 11.02 lbs, de Verdialona.
    > Hay un total de 15.07 lbs, de otras clases.
    ```

    ```python
    #Solve the exercise here
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    ```

6. La Escuela Politécnica desea realizar un estudio para comparar la media de las calificaciones de los alumnos en el
   primer año de ingeniería con sus calificaciones en la EBAU, diferenciadas por centros educativos. Para ello, se
   requiere implementar:
    1. La función averageDifferenceCenter() que recibe como parámetros una lista de cadenas, cada una con datos de un
       alumno  (ver el ejemplo A), y una cadena con el nombre del centro. Retornará la diferencia promedio entre la
       calificación de la EBAU y la media de calificaciones en ingeniería para el centro dado (en valor absoluto).
    2. Implementar un código que trabaje con los datos proporcionados por dos listas de cadenas constantes en el propio
       código: una similar a la del apartado “a)” y otra con los nombres de los centros que interviene en aquella.
       Apoyándose en la función anterior, debe mostrar en pantalla el nombre del centro con la mayor diferencia promedio
       y esa diferencia, y el centro con la menor diferencia promedio y esa diferencia (ver ejemplo B).
    3. Modificar el código anterior para que solicite al usuario el nombre de un archivo y almacene en él los centros
       obtenidos en dicho código y los respectivos promedios de sus diferencias (ver el formato del ejemplo C).
       **Nota:** puede emplearse la función abs (diferencia) para obtener valores absolutos.

Ejemplos:

A)    Contenido de la lista con los datos de los alumnos:

```csv
“Pérez Suarez, Pablo; IES López Acuña; EBAU:6.6; EPI: 5.5”
"Rodríguez Fernández, Luis; IES Antonio Machado; EBAU:8.1; EPI: 7.0”
"Alonso Hidalgo, Sara; IES Antonio Machado; EBAU:10; EPI: 4.0”
"Pérez Hidalgo, Rufino; IES Nº1; EBAU:5; EPI: 9.0”
...
```

B) Salida esperada:

```txt
El peor centro es IES Antonio Machado con una desviación de 2.12 y el mejor es el IES López Acuña con una desviación de 0.53
```

Fichero de salida:

```txt
IES Antonio Machado;2.12
IES López Acuña;0.53
...
```

```python
#Solve the exercise here






































```

NOTA previa: en las preguntas siguientes, tipo V/F, dos errores invalidan un acierto.

7. Conteste V o F según corresponda:

    - [ ] El código máquina debe ser convertido a ensamblador antes de ser ejecutado por la CPU
    - [ ] La dirección IP se emplea para poder recordar el dominio de un computador.
      diferentes tipos de conectores como USB o SATA
    - [ ] Python es un lenguaje de programación de alto nivel.
    - [ ] En la arquitectura Von Neumann la CPU ejecuta las instrucciones, los buses transportan datos, y la
      memoria principal almacena datos e instrucciones.

8. Conteste V o F según corresponda:

    - [ ] Windows 11 es un sistema operativo multiusuario y monotarea.
    - [ ] Ejecutar aplicaciones y acceder a aplicaciones son dos tareas de un sistema operativo moderno.
      simultáneamente, aunque la memoria física sea menor que la requerida para todos los programas.
    - [ ] La interfaz de texto de un sistema operativo hace referencia a programas como Word, la interfaz gráfica a
      programas Paint.
    - [ ] Los virus informáticos solo afectan a Windows, sistemas como Linux no tienen problemas de malware.

9. La Universidad quiere crear una base de datos para almacenar la información referente de sus auditorías energéticas.
   En la base de datos se almacenará la información de los espacios, edificios, lecturas de los contadores, profesores y
   PAS (personal de administración y servicios) del campus. De estas entidades se va a almacenar
    - Espacio: número inventario y tamaño.
    - Edificio: dirección, año de construcción, tamaño, número de suministro, potencia contratada.
    - Lectura de contador:  fecha, hora y potencia suministrada
    - Profesor: nombre, apellidos, correo y departamento.
    - Miembro del PAS: nombre, apellidos, puesto y correo

   Además, sabemos que:

   Un edificio puede tener varios espacios, los espacios pertenecen a un único edificio.

   Un espacio puede tener varias lecturas de contador, cada lectura corresponde a un único momento (fecha y hora) y
   espacio.

   Un profesor puede tener asignados varios espacios, a la misma vez un espacio puede ser compartido por varios
   profesores.

   El PAS rota entre diferentes espacios de la Universidad, un espacio puede ser usado por varios miembros del PAS.

   Se pide el diseño de la base de datos de acuerdo con los contenidos teóricos impartidos, incluyendo el tipo de cada
   relación (1:n, n:n) y clave (PK/FK).

   **NOTA: Es posible que sean necesarias tablas adicionales o añadir campos a las tablas para relacionarlas.**

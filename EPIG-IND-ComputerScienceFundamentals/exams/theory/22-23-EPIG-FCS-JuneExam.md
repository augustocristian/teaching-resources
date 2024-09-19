# Exam Computer Science Fundamentals 19th June 2023

1. Dos números enteros positivos son congruentes módulo m si al
   dividirlos por m proporcionan el mismo resto. Por ejemplo, 4 y 7 son congruentes
   módulo 3, ambos divididos entre 3 dan de resto 1. Sean x, y, dos variables
   enteras, tipo int, del lenguaje Python. A) Escríbase una condición en ese lenguaje
   que sea verdadera (True) exactamente cuando los valores de ambas variables
   sean mayores o iguales que cero y ambos valores congruentes módulo 5. B)
   Proporciónense un valor para x y otro para y que proporcionen el valor de
   verdadero (True) a tal condición
   ```text







   ```

2. En un ordenador que utiliza un byte para representar internamente
   los números enteros en complemento a dos, proporciónese la representación
   interna binaria del número -64
   ```text







   ```

3. Dado el siguiente trozo de código, rellena la tabla con el valor de las
   variables al finalizar cada iteración. Rellena los huecos que consideres necesarios
   en función del número de iteraciones que realiza el bucle.

    ```python
    lista = ['a', 'b', 'c']
    i = 0
    p = lista[0]
    s = ' '
    while i<len(lista):
      if i % 2 == 0:
        p = chr(ord(lista[i])+2)
        s = chr(ord(lista[i])+1)
      else:
        p = chr(ord(lista[i])+1)
        s = chr(ord(lista[i])+2)
      i+=1
   ```

   |       | inicio | it1 | it2 | it3 | it4 | it5 |
   |-------|--------|-----|-----|-----|-----|-----|
   | **s** |        |     |     |     |     |     |
   | **p** |        |     |     |     |     |     |
   | **i** |        |     |     |     |     |     |

4. Se tienen las siguientes variables: a = 1, b = 2, c = 3, d = 4,
   e= [3.5,2,5.5]. Para cada expresión de la tabla siguiente y los valores de las
   variables asignadas indica si se produce algún un error (sintáctico, en tiempo de
   ejecución, etc.). Si no se produce error alguno indica el resultado y su tipo y si se
   produce un error indica brevemente por qué:

   | Expresión        | ¿Correcta? | Tipo y resultado / Modificación / Causa del error | 
   |------------------|------------|---------------------------------------------------|
   | `c/(c-(a+b))`    |            |                                                   |
   | `e[a]*'d'+'z'*a` |            |                                                   |
   | `b*b**-a`        |            |                                                   |
   | `len(e)/b*'z'`   |            |                                                   |
   | `e[d-b**b]`      |            |                                                   |

5. El Ayuntamiento de Madrid ha implementado restricciones a la
   movilidad de los vehículos en función de sus matrículas. Las matrículas constan
   de cuatro dígitos seguidos de tres letras (para simplificar no se contemplan las
   restricciones de letras impuestas en el Código de Circulación) y pueden ser de
   color azul (para VTCs y taxis) o blancas (para el resto de los vehículos).

   Ejemplos:
   ```txt
    VTC 1322 KXX, azul
    Vehículo particular 1712 KZY, blanco
    Vehículo particular 1812 KPA, blanco
   ```
   Para validar la matrícula, se realiza una verificación para determinar si el vehículo
   es un VTC o un taxi. En caso afirmativo, se le permite circular sin restricciones. Sin
   embargo, si se trata de un vehículo particular, se aplican restricciones específicas.
   En los días pares del mes, los vehículos particulares podrán circular si la última
   letra de su matrícula se encuentra entre la 'A' y la 'M', ambas incluidas. Por otro
   lado, en los días impares, se permitirá la circulación del resto de vehículos
   particulares con matrículas acabadas entre la ‘N’ y la ‘Z’, ambas incluidas.

   Siguiendo con el ejemplo anterior, el día de hoy:
   ```txt
    1322 KXX, azul--> Circulación permitida
    1712 KZY, blanco --> Circulación permitida
    1812 KPA, blanco --> Circulación denegada
   ```
   Se pide:
    1. Crear una función llamada validar_matricula(matricula,
       dia) que tome como parámetros una cadena que representa la matrícula de
       un vehículo y un valor numérico que representa el día. Esta función debe
       devolver True si la última letra de la matrícula se encuentra entre 'A' y 'M',
       ambas incluidas, en los días pares, o si se encuentra entre 'N' y 'Z', ambas
       incluidas, en los días impares. En cualquier otro caso, la función debe devolver
       False
    2. Escribe una función llamada circulacion_permitida(dia, matricula, color) que tome como parámetros el día del mes,
       la
       matrícula del vehículo y su color (representado por 'b' o 'a'). Esta función debe utilizar la función previamente
       definida validar_matricula para determinar si el vehículo cumple las condiciones de circulación permitida. En el
       caso
       afirmativo devolverá True y False en el caso contrario.
    3. Implementa un programa que introduciéndole mediante el teclado los datos necesarios correctamente escritos
       imprima
       una leyenda informando de si al vehículo que corresponda le está permitida la circulación o no, ese día.

       ```python
         #Solve the exercise here
       
 
 
 
 
 
       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
       
 
 
       ```


6. Defínanse las siguientes funciones:
    1. `validar_indice()`, cuyos argumentos son un número entero (índice) y una lista. La función devuelve True si el
       índice es válido para la lista,
       y False en caso contrario..
    2. `intercambiar(a, b, lista)`, donde a y b supuestamente son índices de la lista que recibe. Si los índices son
       válidos intercambia los
       elementos de la lista indexados por a y b y devuelve True. Si alguno de los dos índices no es válido, devuelve
       False..
    3. El programa que utilizará las funciones construidas presentará un menú al usuario ofreciéndole cargar una lista
       de enteros positivos y dos índices: A)Desde el teclado (valor < 0 para concluir la carga) o B) Desde un fichero.
       En ambos casos la lista se asignará a la variable lis y los índices a las variables i1 e i2. En el segundo caso
       leerá los índices y la lista del fichero denominado lista.txt. Los dos primeros números leídos se corresponderán
       con los índices y los demás con los elementos de la lista. (Como ejemplo del fichero lista.txt imagínese un
       fichero con los siguientes números, uno en cada línea: 3 1 5 2 9 1 7. Tal fichero representará la
       lista [5, 2, 9, 1, 7] y los índices 3 y 1). Una vez leída la lista y los índices desde cualquiera de los medios,
       teclado o fichero, se intercambiarán los elementos de la lista que estén en las posiciones proporcionadas por los
       índices introducidos, si estos fuesen válidos, mostrando en pantalla la lista resultante o un mensaje avisando de
       que no se pudieron intercambiar por ser índices inválidos.

    ```python
    #Solve the exercise here
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    ```

NOTA previa: en las preguntas siguientes, tipo V/F, dos errores invalidan un acierto.

7. Conteste V o F según corresponda:

    - [ ] El estándar de firmware UEFI es una extensión del estándar de firmware BIOS.
    - [ ] El objetivo principal del Firewall es controlar, de forma activa, las conexiones
      de un dispositivo de una red para mejorar la seguridad perimetral.
    - [ ] Los sistemas operativos actuales permiten multitarea; esto es, permiten
      gestionar diferentes recursos hardware al mismo tiempo.
    - [ ] La gestión de los procesos en la CPU depende exclusivamente de la CPU, por
      eso el Sistema Operativo no opera con procesos.

8. Conteste V o F según corresponda:

    - [ ] La memoria principal (RAM) es aleatoria porque accede de forma estocástica
      a las direcciones de memoria.
    - [ ] El switch permite conectar dispositivos de la misma red, generalmente
      cercanos, mientras que el router permite conectar dispositivos de diferentes
      redes, generalmente más lejanos.
    - [ ] La ventaja de un lenguaje compilado es que, como usa intérprete, puede
      funcionar en distintas arquitecturas.
    - [ ]  La memoria Flash es volátil, porque la información permanece cuando no hay
      alimentación.

9. Un servicio de streaming almacena las canciones en archivos digitales
   en distintos tipos de formatos (mp3, aac, flac, etc.) y calidad (bitrate). El tipo de
   formato y la calidad definen un formato, por ejemplo “mp3 128 bits/s”. Como es
   obvio, además del título de la canción y otros datos también se almacenan en la
   base de datos el autor o autores y el álbum (disco) o álbumes de los que forma
   parte cada canción, en resumen:

    - Autores: nombre
    - Canciones: título y duración
    - Formatos: tipo y bitrate
    - Álbumes: título

   Además, sabemos que:

   Un autor puede escribir varias canciones y una canción estar escrita por varios
   autores.

   Una canción puede aparecer en varios álbumes y en un álbum hay varias
   canciones.

   Una canción puede estar almacenada en varios formatos y el mismo formato
   puede utilizarse en varias canciones.

   Se pide el diseño de la base de datos de acuerdo a los contenidos teóricos
   impartidos, incluyendo el tipo de cada relación (1:n, n:n) y clave (PK/FK)
   **NOTA: Es posible que sean necesarias tablas adicionales o añadir campos a las tablas para relacionarlas.**

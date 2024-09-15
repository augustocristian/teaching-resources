# Exam Computer Science Fundamentals 21th May 2024

1. Sean x, y, z, u cuatro variables enteras (int) del lenguaje Python.1.1) Obténgase una condición en ese lenguaje que
   sea verdadera (True) si y solo si no se verifica que las cuatro variables tomen valores iguales o decrecientes en el
   orden que se proporcionaron. 1.2) Si fuese posible, simplifíquese la condición obtenida hasta obtener una expresión
   sin negaciones que, en última instancia, habrían quedado absorbidas por la adopción de los operadores relacionales
   complementarios.

   ```text







   ```

2. Desarróllense las transformaciones y cálculos que realizaría un ordenador que representase los números enteros con un
   byte para obtener el valor de la variable x en la ecuación: 00000011 - x = 11111010. Finalmente, proporciónese el
   resultado de x en base decimal.

   ```text







   ```

3. Dado el siguiente trozo de código, rellena la tabla con el valor de las variables al finalizar cada iteración.
   Rellena los huecos que consideres necesarios en función del número de iteraciones que realiza el bucle.

   ```python
    e = 2
    da = db = 0
    farey = []
    for i in range(e):
      for j in range(e): 
        da = i + 1
        db = j + 1
        farey.append(da/db)
   ```

   |           | inicio | it1 | it2 | it3 | it4 | it5 |
       |-----------|--------|-----|-----|-----|-----|-----|
   | **da**    |        |     |     |     |     |     |
   | **db**    |        |     |     |     |     |     |
   | **farey** |        |     |     |     |     |     |

4. Se tienen las siguientes variables: a = ['pe', 1, 'il'], b= '3,2', c=5. Para cada expresión de la tabla siguiente,
   indica si es correcta o por si el contrario, daría un error en su ejecución. Indíquese el tipo y resultado o la
   modificación de la lista o en caso de error la causa de este:

   | Expresión         | ¿Correcta? | Tipo y resultado / Modificación / Causa del error |
       |-------------------|------------|---------------------------------------------------|
   | `a[0][1]+a[2][1]` |            |                                                   |
   | `b + c`           |            |                                                   |
   | `float(b) + c`    |            |                                                   |
   | `a[:-1]`          |            |                                                   |
   | `a.append(b)`     |            |                                                   |

5. Recientemente, el Ayuntamiento de Bolonia cerró las "Due Torri" y sus alrededores debido al riesgo de derrumbe. Con
   objeto de realizar el mantenimiento preventivo y evitar más incidentes, el Gobierno Italiano nos ha encargado un
   software para evaluar el riesgo de sus edificios históricos. Se requiere una función buildingRisk() que tome como
   parámetros la altura, el año de construcción, el material y la inclinación, y retorne un índice de riesgo. La fórmula
   para calcular el índice de riesgo es: norm alizar(inclinación) * coef * altura, donde el coeficiente (coef) depende
   de:
    - Si el material es *"iron"* y la antigüedad es menor que 100 años, o *"stone"* y la antigüedad es menor que 400
      años, el coeficiente es 0.85.
    - Si el material es *"iron"* y la antigüedad mayor o igual que 100 y menor que 200 años, o *"stone"* y la antigüedad
      mayor o igual que 400 y menor que 700 años, el coeficiente es 1.25
    - Si la antigüedad es mayor o igual que 200 años para *"iron"* o mayor o igual que 700 años para *"stone"*, el
      coeficiente es 1.85.
    - Independientemente del material, si la antigüedad supera los 1200 años, el coeficiente pasa a ser 2.0.

   **Nota:** No se demanda implementar la función normalizar(), solo utilizarla. Esta función recibe tres enteros
   como parámetro: la inclinación detectada en grados (negativa o positiva), el mínimo (0), el máximo (45), y
   devuelve el valor normalizado.

   ```python
   #Solve the exercise here











































   ```

6. El Gobierno Italiano tiene monitorizadas todas las torres, cuya inclinación se reporta periódicamente mediante un
   texto de la forma “idtorre;inclinación” (identificador de la torre e inclinación). Por otra parte, se tiene
   almacenado en una lista una serie reportes de diferentes torres con la siguiente información: el identificador de la
   torre, la altura, el material y el año de construcción. En concreto, cada elemento de la lista es un texto con la
   estructura “idtorre;altura;material,año”.
   Se pide implementar las siguientes funciones:
    1. posTowerData() que dados como parámetros un identificador de la torre y una lista con los datos de varias,
       retorne la posición de la lista en la que se encuentran los datos de la torre.
    2. calculateTowerRisk() que dado como parámetro un reporte de una torre (torre e inclinación), así como la lista con
       los datos de distintas torres, calcule y retorne convenientemente el riesgo empleando las funciones anteriores.
    3. towerAlarm() que dados como parámetros la ruta de un fichero con reportes de varias torres (uno por línea), una
       lista con los datos de las torres y un umbral, lea y muestre por pantalla los identificadores de aquellas torres
       con un índice de riesgo mayor que el umbral dado.

   Lista con los datos de las torres:

   ```python
   lista =  [“tower1;123;stone;1922”,“tower2;500;iron;1680”,“tower3;800;stone;1325”,“tower4;2000;iron;1750”… ]
   ```

   Reporte de torre:

   ```txt
   tower1;2º
   ```

   Fichero de reportes:

   ```csv
   tower1;2º
   tower2;1.4º
   tower2:1.41º
   ```

   ```python
   #Solve the exercise here






































   ```

NOTA previa: en las preguntas siguientes, tipo V/F, dos errores invalidan un acierto.

7. Conteste V o F según corresponda:

    - [ ] Los sistemas operativos actuales no requieren drivers, el dispositivo es gestionado automáticamente por el
      S.O. en el momento en el que se conecta.
    - [ ] Los discos duros, así como las unidades lectoras de CD, DVD y Blue-Ray se pueden conectar al ordenador
      mediante
      diferentes tipos de conectores como USB o SATA

    - [ ] Ubuntu, Windows 11, Android 15 o MacOS son ejemplos de sistemas operativos multitarea y multiusuario modernos

    - [ ] La memoria está formada por una secuencia de celdas de almacenamiento numeradas (posiciones de memoria) donde
      cada una es un byte o unidad de información.

8. Conteste V o F según corresponda:

    - [ ] El nombre completo de un archivo es la concatenación de su nombre y extensión.
    - [ ] La interfaz de texto de un SO requiere un menor consumo de recursos, un mayor conocimiento técnico del S.O. y
      es poco intuitiva.
      simultáneamente, aunque la memoria física sea menor que la requerida para todos los programas.
    - [ ] Todos los ordenadores dentro de una misma red local comparten los bits más significativos de la dirección de
      red. Estos bits vienen determinados por la máscara
    - [ ] El Administrador de Tareas/Monitor de Actividad permite monitorizar las tareas en ejecución, pero no
      finalizarlas

9. La universidad quiere crear una serie de canales de YouTube para dar difusión a su actividad docente-investigadora.
   Para ello requiere de una base de datos en la que almacenará la información de los vídeos , canales, suscriptores,
   comentarios y creadores de contenido. De estas entidades se va a almacenar:

    - Canal: nombre, fecha de creación y tópico.
    - Suscriptor: nick, correo electrónico, edad y URL con la foto de perfil
    - Creadores de contenido: nick, nombre, apellidos, correo electrónico y centro de adscripción.
    - Video: nombre, descripción y resolución, fecha y hora de publicación.
    - Comentario: contenido, fecha y hora.

   Además, sabemos que:
   Un canal puede tener varios suscriptores, a su vez estos pueden estar suscritos a varios canales.

   Un canal tiene uno o varios videos creados por los creadores de contenido de la Universidad. Un creador de contenido
   puede crear varios videos e incluso colaborar en un mismo video con otro creador.

   Los videos tienen uno o varios comentarios, realizados por los suscriptores que a su vez pueden realizar más de un
   comentario en los diferentes videos.

   **Se pide el diseño de la base de datos de acuerdo con los contenidos teóricos impartidos, incluyendo el tipo de
   cada relación (1:n, n:n) y clave (PK/FK).**

   **NOTA: Es posible que sean necesarias tablas adicionales o añadir campos a las tablas para relacionarlas.**

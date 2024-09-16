# Exam Computer Science Fundamentals 26th May 2023

1. Sean x, y dos variables enteras del lenguaje Python; es decir, tipo int.
   A) Escríbase una condición en ese lenguaje que sea verdadera (True)
   exactamente si al menos una de las dos es mayor que cero y al menos una de las
   dos es menor que cero. B) Defínase el concepto de proposición contradictoria en
   Lógica y proporciónense un par de valores para x e y respectivamente que
   confirmen que la condición pedida no se corresponde con una proposición
   contradictoria.

   ```text







   ```

2. En un ordenador que utiliza un byte para representar internamente los números enteros con signo, la representación de
   un cierto número es:11111111. Reviértase el proceso de obtención de esa representación hasta
   alcanzar la expresión habitual en base de decimal del citado número.

   ```text







   ```

3. Dado el siguiente trozo de código, rellena la tabla con el valor de las
   variables al finalizar cada iteración. Rellena los huecos que consideres necesarios
   en función del número de iteraciones que realiza el bucle.

   ```python
   lista = [3,2,5,-3,4,2]
   i = 0
   p = 1
   s = 0
   while lista[i] >= 0:
      if lista[i] % 2 == 0:
         s = s + lista[i]
      else:
         p = p * lista[i]
      i = i + 1
   ```

   |       | inicio | it1 | it2 | it3 | it4 | it5 |
      |-------|--------|-----|-----|-----|-----|-----|
   | **s** | 0      |     |     |     |     |     |
   | **p** | 1      |     |     |     |     |     |
   | **i** | 0      |     |     |     |     |     |

4. Se tienen las siguientes variables: a = 1, b = 2, c = 3, d = 4,
   e = [3.5,2,5.5]. Para cada expresión de la tabla siguiente, indica si es
   correcta o no o si se produce un error en tiempo de ejecución. Si es correcta
   indica el resultado y su tipo, y si es incorrecta o se produce un error, indica
   brevemente por qué:

   | Expresión          | ¿Correcta? | Tipo y resultado / Modificación / Causa del error |
      |--------------------|------------|---------------------------------------------------|
   | `-a**b+c*d`        |            |                                                   |
   | `c*'d'+b*'a'`      |            |                                                   |
   | `(a//b)**-c+d`     |            |                                                   |
   | `d/b*'c'+'a'`      |            |                                                   |
   | `e[1]*e[2]+len(e)` |            |                                                   |

5. Defínanse las siguientes funciones::
    - `factorial(n)`: el argumento será un entero, cero o positivo, y
      devolverá el factorial del valor del argumento: n!; es decir, si n es cero
      devolverá 1 y si no devolverá el resultado de: 1 ⋅ 2 ⋅ 3 ⋅ 4 ⋅...⋅n
    - `combinatorio(n,m)`: los argumentos son dos enteros, cero o
      positivos, tales que n>=m. Devolverá el valor de la expresión
      $$
      \frac{n!}{(n-m)!*m!}
      $$

      Utilizando las funciones anteriores, constrúyase un programa que reciba
      como entrada desde el teclado un entero positivo o cero, deberá de comprobar
      que es así y si es necesario repetir la petición del valor, y calcule e imprima el
      valor de la siguiente expresión para el valor n introducido:
      $$
      \sum_{k=0}^{n} (-1)^k \binom{n}{k}
      $$

   ```python
   #Solve the exercise here











































   ```

6. En algunos países, el IBAN de una cuenta corriente consta de dos
   letras mayúsculas del alfabeto inglés, que identifican a cada país, seguido de un
   número de dígitos que varía de unos a otros.

   Ejemplos:

   | País    | IBAN                     | 
      |---------|--------------------------|
   | Bélgica | BE88320034713441         | 
   | España  | ES9000246912501234567891 |   
   | Estonia | EE382200221020145685     | 
   Durante el proceso de validación del IBAN, las letras se convierten en números
   de la siguiente manera: La A se sustituye por 10, la B por 11, y así
   sucesivamente hasta la Z que se sustituye por 35.

   Siguiendo con el ejemplo anterior

   | País    | Sustitución | 
      |---------|-------------|
   | Bélgica | BE --> 1114 | 
   | España  | ES --> 1428 |   
   | Estonia | EE --> 1414 | 

   Se pide:
    1. Hacer una función `convertirLetrasIBAN(IBAN)` que reciba
       como parámetro una cadena que contiene un IBAN, y devuelva otra cadena
       con los 4 dígitos correspondientes al código de país, obtenidos según la regla
       anterior.
    2. Para validar el IBAN se debe de colocar, al final del mismo, la cadena
       de 4 dígitos obtenida en el apartado anterior, junto con los 2 primeros dígitos
       del IBAN. Si el número así obtenido se divide entre 97 y el resto es 1, el IBAN
       es válido.

       `Ejemplo: BE88320034713441 ---> 320034713441111488 ---> el resto de dividir entre
       97 da 1, luego el IBAN es válido.`

       Hacer otra función `validarIBAN(IBAN)` que reciba como parámetro una
       cadena con el IBAN y, haciendo uso de la anterior, devuelva True o False
       según proceda

       ```python
       #Solve the exercise here
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
       ```

NOTA previa: en las preguntas siguientes, tipo V/F, dos errores invalidan un acierto.

7. Conteste V o F según corresponda:

    - [ ] Los controladores de dispositivo son programas que supervisan los
      periféricos.
    - [ ] La arquitectura Von Neumann tiene cuatro buses: Control, Datos,
      Direcciones y Seguridad.

    - [ ] Los discos de estado sólido no disponen de partes móviles.

    - [ ] Los discos ópticos como los CDs o DVDs tienen los datos colocados en forma
      de espiral

8. Conteste V o F según corresponda:

    - [ ] Los sistemas operativos no se encargan de gestionar la memoria del
      computador.

    - [ ] Los sistemas operativos en tiempo real deben responder dentro de un
      intervalo de tiempo determinado.

    - [ ] Una WAN es una red de área local que no tiene conexiones con otras
      redes.

    - [ ] El servicio de nombres de dominio, DNS, se encarga de traducir direcciones
      IP a nombres de dominios.

9. En una empresa dedicada a la ges�ón de cines es necesario mantener
   una base de datos con la información de sus cines, sus salas y las películas que se
   visualizan en ellas. La información que se almacena en la base de datos es la
   siguiente:

    - Ciudad: Nombre, provincia.
    - Cine: Nombre, ubicación.
    - Sala: Número y capacidad.
    - Película: Título, categoría
    - Sesión: Fecha y hora
    - Cliente: Nombre, DNI

Una ciudad puede tener varios cines y un cine se localiza en una sola ciudad.

Un cine puede tener varias salas y una sala solo puede estar un cine.

Una película puede ser visualizada en varias sesiones y en una sesión solo se podrá visualizar una película.

En una sala se pueden realizar varias sesiones y una sesión solo se podrá realizar en una sala.

Un cliente puede asis�r a varias sesiones y en una sesión pueden asistir varios clientes.

Se pide el diseño de la base de datos de acuerdo a los contenidos teóricos impartidos, incluyendo el tipo de cada
relación (1:n, n:n) y clave (PK/FK)

**NOTA: Es posible que sean necesarias tablas adicionales o añadir campos a las tablas para relacionarlas.**

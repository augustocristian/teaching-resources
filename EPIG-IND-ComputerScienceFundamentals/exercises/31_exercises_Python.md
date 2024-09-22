# Python exercises VOL I

## Contenido

- [Ejercicios condicionales](#ejercicios-de-condicionales)
- [Ejercicios con bucles](#ejercicios-de-bucles)
- [Ejercicios con funciones](#ejercicios-con-funciones)
- [Ejercicios con ficheros](#ejercicios-con-ficheros)

## Ejercicios de variables

1. Dadas las variables a= 3 b = “pepe” c=1 d= 2 para cada expresión de la tabla siguiente, indicar si la expresión es
   correcta o no. Si lo fuera, indicar el resultado y su tipo. Si es incorrecta indicar brevemente por qué

   | Expresión  | ¿Es correcta? | Tipo y resultado | 
   |------------|---------------|------------------|
   | `a/d`      |               |                  |
   | `a*b/d`    |               |                  |
   | `a**(c/2)` |               |                  |
   | `c%d==c`   |               |                  |
   | `b*a**d`   |               |                  |

    <details>
      <summary>SEE SOLUTION</summary>

   | Expresión  | ¿Es correcta? | Tipo y resultado                                           |
   |------------|---------------|------------------------------------------------------------|
   | `a/d`      | Sí            | 1.5 `float`                                                |
   | `a*b/d`    | No            | Incorrecta, b es una cadena la cual no soporta la división |
   | `a**(c/2)` | Sí            | 3^(√2)   `float`                                           |
   | `c%d==c`   | Sí            | True  `bool`                                               |
   | `b*a**d`   | Sí            | 'pepepepepepepepepepepepepepepepepepe' `str`               |

   </details>
2. ¿Qué saldrá por pantalla al ejecutar el siguiente código?

   ```python 
   j = 0
   h = 5
   resultado = h**j
   j = j + 1
   resultado = resultado + h**j
   j = j + 1
   resultado = resultado + h**j
   print(resultado)
    ```
   Salida: `El resultado es : _ _`
    <details>
      <summary>SEE SOLUTION</summary>

   ` El resultado es 31 (1+5+25)`
   </details>

3.  Dado el siguiente código:
    ```python 
      lista = [3, 7, 8, 12,8]
      i = 0
      a = 0
      b = 10
      while len(lista) != 0:
        i += 1
        if i % 2 == 0:
          a += lista.pop()
        else:
          b -= lista.pop(0)
      ```
   Rellena la siguiente tabla:
   
   | Variable  | 1 | 2 | 3 | 4 | 5 | 6 |
   |:---------:|:-:|:-:|:-:|:-:|:-:|:-:|
   |   **i**   |   |   |   |   |   |   |
   |   **a**   |   |   |   |   |   |   |
   |   **b**   |   |   |   |   |   |   |
   | **lista** |   |   |   |   |   |   |
 <details>
   <summary>SEE SOLUTION</summary>
   
   | Variable  |     1      |     2     |   3    |   4   | 5  | 6 |
   |:---------:|:----------:|:---------:|:------:|:-----:|:--:|:-:|
   |   **i**   |     1      |     2     |   3    |   4   | 5  |   |
   |   **a**   |     0      |     8     |   8    |  20   | 20 |   |
   |   **b**   |     7      |     7     |   0    |   0   | -8 |   |
   | **lista** | [7,8,12,8] | [7,8,12]  | [8,12] |  [8]  | [] |   |
</details>

## Ejercicios de condicionales

1. Escribir las siguientes condiciones empleando la sintaxis de Python:
    1. El resto de dividir `X` entre `Y` es mayor que `Y` elevado al cuadrado.  `Y` se encuentra en el intervalo [1,4)
    2. Y más 5 es distinto de `Z` así como `Z` más 4 es menor que `Y`. `X` e `Y` se encuentran en el intervalo (2,5)
       ```python 
       Escribe la solución aquí:
    
    
    
    
         ```
   <details>
      <summary>SEE SOLUTION</summary>

      ```python 
               i) ((X%Y)>(Y**2) ) &((Y>=1)&(Y<4))
               ii) ((Y+5)!=Z) & (Z+4<Y) & (Z>2)&(Z<5) & (Y>2)&(Y<5)
      ```

 </details>

## Ejercicios de bucles

1. Imprimir por pantalla un cuadrado de asteriscos.
   ```console 
    **************
    **************
    **************
    **************
    ```
    <details>
      <summary>SEE SOLUTION</summary>

   ```python 
    # WHILE SOLUTION
    iter: int = 0
    while (iter <= 4):
        print("***********")
    iter = iter + 1
    # FOR SOLUTION
    for iter in range(0, 5, 1):
        print("***********")
    ```

</details>

2. Imprimir por pantalla un cuadrado vacío de asteriscos.
   ```console 
    **************
    *            *
    *            *
    **************
    ```
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   # WHILE SOLUTION 
    iter: int = 0
    while (iter <= 4):
        if (iter == 0) | (iter == 4):
            print("***********")
        else:
            print("*         *")
        iter = iter + 1
    # FOR
    for iter in range(0, 5, 1):
        if (iter == 0) | (iter == 4):
            print("***********")
        else:
            print("*         *")
    ```

</details>

3. Imprimir por pantalla un cuadrado vacío de asteriscos.
   ```console 
    **************
    *            *
    *            *
    **************
    ```
    <details>
      <summary>SEE SOLUTION</summary>

   ```python 
    # WHILE SOLUTION
    iter: int = 0
    while (iter <= 4):
        if (iter == 0) | (iter == 4):
            print("***********")
        else:
            print("*         *")
        iter = iter + 1
    # FOR SOLUTION
    for iter in range(0, 5, 1):
        if (iter == 0) | (iter == 4):
            print("***********")
        else:
            print("*         *")
    ```

</details>

4. Calcular el sumatorio de un número.
   ```math 
    \sum_{}^{}n
    ```
    <details>
      <summary>SEE SOLUTION</summary>

   ```python 
    sumatorio: int = 0
    num: int = int(input("Dame un número"))
    # WHILE SOLUTION
    iter = 0
    while (iter < num):
        iter = iter + 1
        sumatorio = sumatorio + iter
    
    # FOR SOLUTION
    for iter in range(0, num + 1, 1):
        sumatorio = sumatorio + iter
        print("El sumatorio es ", sumatorio)
    ```

</details>

5. Pedir a un usuario un número n y mostrar todos los impares que hay en el rango `[0, n]`.

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
    # WHILE SOLUTION 
    num : int = int(input("dame un número"))
    iter : int = 0
    while (iter < num):
        if (iter % 2 != 0):
            print(iter)
        iter = iter + 1
    # FOR SOLUTION
    for iter in range(0, num + 1, 1):
        if (iter % 2 != 0):
            print(iter)
    ```

</details>

6. Pedir a un usuario una palabra y mostrar por pantalla cada una de sus letras.

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
    word = input("Dame una palabra")
    # WHILE SOLUTION
    iter = 0
    while (iter < len(word)):
        print(word[iter])
        iter = iter + 1
    # FOR SOLUTION
    for iter in range(0, len(word), 1):
        print(word[iter])

    ```

</details>

7. Pedir a un usuario una palabra y mostrar la cantidad de vocales que tiene esta.

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
    word : str = input("dame una palabra")
    # WHILE
    iter = 0
    nvocales: int = 0
    while iter < len(word):
    if (word[iter] == "a") | (word[iter] == "e") | (word[iter] == "i") | (word[iter] == "o") | (word[iter] == "u"):
        nvocales = nvocales + 1
        iter = iter + 1
    print("La cantidad de vocales es ", nvocales)
    
    # FOR
    nvocales : int = 0
    for iter in range(0, len(word), 1):
        if ((word[iter] == "a") | (word[iter] == "e") | (word[iter] == "i") | (word[iter] == "o") | (word[iter] == "u")):
            nvocales = nvocales + 1
    print("La cantidad de vocales es ", nvocales)

    ```

</details>

8. Dada una palabra en minúsculas, devuelve al usuario la misma palabra toda en mayúsculas (chr-ord) (A  a =32).

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
    wordmayus = ""
    iter = 0
    while (iter < len(word)):
        wordmayus = wordmayus + chr(ord(word[iter]) - 32)
        iter = iter + 1
    print(wordmayus)
    
    wordmayus = ""
    for iter in range(0, len(word), 1):
        wordmayus = wordmayus + chr(ord(word[iter]) - 32)
    print(wordmayus)
    ```

</details>

9. Pedir cuantos números se van a introducir, ir introduciendo por teclado esos números y mostrando un mensaje cada vez
   que el número introducido sea menor que el anterior.

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
    cantidad : int = int(input("¿Cuantos vas a introducir?"))
    anterior : int = 0
    iter : int = 0
    # Con while
    while (iter < cantidad):
        num : int = int(input("Dame Nº"))
        if (num < anterior):
            print("Es menor!")
        anterior = num
        iter = iter + 1
    # Con For
    for iter in range(0, cantidad, 1):
        num : int = int(input("Dame Nº"))
        if (num < anterior):
            print("Es menor!")
        anterior = num
    ```

</details>

10. Pedir de forma iterativa un número al usuario hasta que este introduzca un múltiplo de 7
    <details>
      <summary>SEE SOLUTION</summary>

       ```python
            esmultiplo : bool = False
            while (esmultiplo == False):
                num = int(input("Dame un número"))
                if (num % 7 == 0):
                    esmultiplo = True
       ```

</details>

11. Pedir de forma iterativa números hasta que el usuario introduzca un 0. En ese momento se deberá imprimir que números
    son pares y cuales impares
    <details>
      <summary>SEE SOLUTION</summary>

       ```python
        pares = "Los pares son : \n "
        impares = "Los impares son : \n "
        num = 1
        while (num != 0):
            num = int(input("Dame un número"))
            if (num % 2 == 0):
                pares = pares + " " + str(num)
            else:
                impares = impares + " " + str(num)
        print(pares + "\n" + impares)
       ```

</details>

12. Imprimir por pantalla una matriz n*m con las posiciones de sus elementos tal que (véase una matriz 3X3)
    ```console 
    11 12 13
    21 22 23
    31 32 33
      ```
    <details>
      <summary>SEE SOLUTION</summary>

       ```python
        n : int = int(input("Dame la N"))
        m : int = int(input("Dame la M"))
        matriz : str = ""
        for i in range(1, n + 1, 1):
            for j in range(1, m + 1, 1):
                matriz = matriz + str(i) + str(j) + " "
            matriz += "\n"
        print(matriz)
        matriz : str = ""
        i : int = 1
        j : int = 1
        while (i <= n):
            while (j <= m):
                matriz = matriz + str(i) + str(j) + " "
                j = j + 1
                i = i + 1
            matriz += "\n"
        print(matriz)
       ```

</details>

## Ejercicios con funciones

1. Definir una función que dados dos números (el primero menor que el segundo) muestre por pantalla todos los números
   pares que hay en dicho intervalo

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def paresintervalo(n,m):
      for i in range (n,m,1)
         if(i%2==0):
            print (i)
   ```

</details>

2. Definir una función que dados dos números (el primero menor que el segundo) RETORNE una cadena con todos los impares
   del intervalo

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def imparesintervalo(n,m):
      salida=“”
      for i in range (n,m,1)
         if(i%2!=0):
      return salida
   ```

</details>

3. Definir una función que dada una nota (numérica) devuelva si es un “SUSPENSO”, “APROBADO”, “NOTABLE” o
   “SOBRESALIENTE””

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def notastring(nota):
      salida=“”
      If (nota<5):
         salida=“SUSPENSO”
      elif (nota>=5)&(nota<7):
         salida =“APROBADO”
      elif (nota>=7)&(nota<9):
         salida =“NOTABLE”
      else:
         salida= “SOBRESALIENTE”
   return salida
   ```

</details>

4. Definir una función DNIValido que, dado un número de DNI, retorne True si es válido y False si no lo es. Para que un
   número de DNI sea válido debe de tener 9 dígitos y una letra mayúscula

    <details>
      <summary>SEE SOLUTION</summary>

       ```python
        def validardni(dni):
        if len(dni) == 9:
            for i in range(0, len(dni)):
                letter : str = dni[i]
                is_number : bool = not (letter in '1234567890') & i < 8
                last_is_letter : bool = (ord('A') <= ord(letter) <= ord('Z')) & (i == 8)
                if is_number:
                    return False
                else:
                    if last_is_letter:
                        return True
        
        return False
       ```

</details>

5. Definir una función que dada una cantidad de grados celsius, retorne el equivalente en escala Kelvin y Farenheit. (
   0ºC= 273 ºK, ºF= ℃ * 1.8000+32.00

    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def dameGrados(centigrados):
      gradosKelvin=centigrados+273
      gradosFarenheit=centigrados* 1.8000+ 32.00
      return gradosKelvin,gradosFarenheit
   kelvin,farenheit = dameGrados(30)
   ```
   </details>

6. Definir una función que dado el peso y altura de un paciente muestre por pantalla (1) su IMC y (2) su estado
   siendo este:
   ```math
   IMC = \frac{Peso}{Altura^2}
   ```
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def dameimc(peso, altura):
     imc = peso / (altura ** 2)
     if (imc < 18.5):
       print("El IMC es de", imc, "tienes un peso bajo")
     elif ((imc >= 18.5) & (imc <= 24.9)):
       print("El IMC es de", imc, "tienes un peso Normal")
     elif ((imc >= 25) & (imc <= 29.9)):
       print("El IMC es de", imc, "tienes Sobrepeso")
     else:
       print("El IMC es de", imc, "tienes Obesidad"
   ```

</details>

7. Definir una función que dada la longitud de tres lados h,c1,c2, retorne si puede formarse un triangulo con los mismos
   o no, en caso afirmativo, muéstrese por pantalla el área:
   ```math
   h >= c + c
   ```
      ```math
   s = \frac{a + b + c}{2}
   ```
      ```math
   Area = \sqrt{s(s - a)(s - b)(s - c)}
   ```
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def estriangulovalido(h, cuno, cdos):
      if (h <= (cuno + cdos)):
         area = (((h + cuno + cdos) / 2) * (((h + cuno + cdos) / 2) - h) * (((h + cuno + cdos) / 2) - cuno) * (((h + cuno + cdos) / 2) - cdos)) ** (1 / 2)
         print("El área es ", area)
         return True
      else:
        return False
   ```

</details>

8. Definir una función esprimo, que reciba un número x y compruebe si es primo o no:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def esprimo(n):
      if n <= 1:
         return False
      for i in range(2, int(n**0.5) + 1):
         if n % i == 0:
            return False
      return True
   ```

</details>

9. Crear una función que dado un intervalo [A,B], invoque a la función creada anteriormente para mostrar únicamente los
   números primos en ese intervalo:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def dameprimosintervalo(a, b):
      for i in range(a, b + 1, 1):
         if (esprimo(i)):
            print(i)
   ```

</details>

10. Crear una función que compruebe si una palabra es palíndromo (se lee igual en ambos sentidos ej. ojo, nadan,radar…):

    <details>
      <summary>SEE SOLUTION</summary>

      ```python
      def espalindromo(palabra):
         palabradelreves="“
         for i in range (len(palabra)-1,-1,-1):
            palabradelreves+=palabra[i];
         return palabra==palabradelreves
         
      def espalindromoslicing(palabra):
         return palabra==palabra[::-1]
      ```

</details>

11. Implementar una función que permita a dos jugadores jugar a piedra papel o tijera. El programa pedirá por teclado a
    ambos jugadores que seleccionen opción, siendo: (1) Piedra, (2) Papel(3) Tijera de manera iterativa hasta que uno de
    los dos gane y mostrará el vencedor
    <details>
      <summary>SEE SOLUTION</summary>

      ```python
      def piedra_papel_tijera():
         player_a = 0
         player_b = 0
         while player_a == player_b:
            player_a = int(input("Dime que opción quiere jugador A:\n1)Piedra\n2)Papel\n3)Tijera "))
            player_b = int(input("Dime que opción quiere jugador B:\n1)Piedra\n2)Papel\n3)Tijera "))
         if (player_a == 1 and player_b == 3) | (player_a == 2 and player_b == 1) | (player_a == 3 and player_b == 2):
            print("Ha ganado el Jugador A")
         else:
            print("Ha ganado el Jugador B")
      ```

</details>

## Ejercicios con ficheros
1. Definir una funcion que dada la ruta de un fichero muestre su contenido:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def leelineaspares(ruta:str):
       f = open(ruta, ’r’)
       lista = f.readlines()
       for  línea in lista:
           print (línea.strip())
       f.close()
   ```

</details>

2. Definir una funcion que dada la ruta de un fichero muestre el contenido de las líneas pares:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def leelineaspares(ruta):
       f = open(ruta, ’r’)
       lista = f.readlines()
       nlinea = 1
       for  línea in lista:
           if(nlinea%2==0):
               print (línea.strip())
           nlinea+=1	
       f.close()
   ```

</details>

3. Definir una función, que dada la ruta de un fichero, pida línea a línea el contenido del mismo hasta que el usuario
   escriba END:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def escribeentrada(ruta):
       f = open(ruta, ’a’)
       linea= input(“Dame la siguiente línea \n”)
       while (linea!=“END”	):
           f.write(linea)
           linea=input (“Dame la siguiente línea \n”) 	f.close()

   ```

</details>

4. Definir una función,que lea de un fichero lineas y escriba en otros dos ficheros: (1) las líneas pares y (2) las impares:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def escribelineaspareseimpares(rutaentrada,rutapares,rutaimpares):
       finput = open(rutaentrada, 'r')
       foutputpares=open(rutapares, 'a')
       foutputimpares = open(rutaimpares, 'a')
       lista = finput.readlines()
       nlinea = 1
       for  linea in lista:
           if(nlinea%2==0):
               foutputpares.write(linea)
           else:
               foutputimpares.write(linea)
           nlinea+=1
       finput.close()
       foutputpares.close()
       foutputimpares.close()
   
    escribelineaspareseimpares(ficheroentrada)
   ```

</details>

5. Definir una función, que lea por entrada los elementos de una lista de números hasta que el usuario introduzca un 0 y
   retorne dicha lista:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def leelista():
       lista=[]
       item= float(input("Dame el elemento que quieres introducir \n"))
       while (item!=0):
           lista.append(item)
           item= float(input("Dame el  siguiente elemento \n"))
       return lista
   print(leelista())
   ```

</details>

6. Definir una función que tome por entrada una lista de números y retorne dos listas: una con los pares y otra con los impares:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def clasificaparimpar(lista):
       listapares=[]
       listaimpares= []
       for i in lista:
           if (i%2==0):
               listapares.append(i)
           else:
               listaimpares.append(i)
   
       return listapares,listaimpares
   pares,impares=clasificaparimpar([1,2,3,4,5,6,7,8,9])
   print(pares)
   print(impares) 
   ```

</details>

7. Definir una función que tome como entrada una lista con elementos de varios tipos (Flotantes, Enteros, Cadenas, Booleanos) 
  y retorne cuatro listas con los elementos de cada tipo:
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def clasificalistas(lista):
       listastrings=[]
       listaenteros=[]
       listaflotantes=[]
       listabooleanos=[]
       for i in lista:
           if type(i)==type("String"):
               listastrings.append(i)
           elif type(i)==type(1):
               listaenteros.append(i)
           elif type(i)==type(2.0):
               listaflotantes.append(i)
           elif type(i)==type(True):
               listabooleanos.append(i)
       return listastrings,listaenteros,listaflotantes,listabooleanos
   
   list=["Hola",1.0,2,True,"Pepe",2,2.3,False]
   strings,enteros,flotantes,booleanos=clasificalistas(list)
   ```

</details>

8. Definir una función que dada una lista con números enteros, compruebe elemento a elemento y elimine aquellos que son múltiplos de 2
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def eliminamultiplosdos(lista):
       copialista=[]
       copialista.extend(lista)
       for i in copialista:
           if(i%2==0):
               lista.remove(i)
       return lista
   
   listamultiplos=list(range(1,100))
   listamultiplos=eliminamultiplosdos(listamultiplos)
   ```

</details>

9. Definir una función que reciba una lista de flotantes y un porcentaje a aplicar. La función debe de incrementar todos
   los elementos de la lista con ese porcentaje y retornarla
    <details>
      <summary>SEE SOLUTION</summary>

   ```python
   def incrementaporcentaje(lista,porcentaje):
       for i in range(0,len(lista)):
           lista[i]=lista[i]*(1+(porcentaje/100))
       return  lista
   
   lis= [1.3,5.5,1.7,1.9,7]
   lis=incrementaporcentaje(lis,20)
   print(lis)
   ```

</details>


10. Definir una función que reciba una lista y retorne otra sin elementos duplicados
    <details>
      <summary>SEE SOLUTION</summary>

      ```python
      def eliminaduplicados(lista):
          listasinduplicados=[]
          for i in lista:
              if ((i in listasinduplicados)==False):
                  listasinduplicados.append(i)
          return listasinduplicados
      listaduplicados= [2,2,2,4,5,5,5,6,7,7,8,8,8,8]
      listasinduplicados=eliminaduplicados(listaduplicados)
      print(listasinduplicados) )
      ```

</details>


11. Implementar una función que dada la ruta de un [fichero con las temperaturas](data/31_FI_Pyhton_temperatures.csv)
    en el que se tienen el año con las temperaturas de sus doce meses separadas por comas, devuelva una lista de
    tuplas   `[Año,máxTemp]`

   Extracto del fichero:

   ```console 
    1901,22.4,24.14,29.07,31.91,33.41,33.18,31.21,30.39,30.47,29.97,27.31,24.49,28.96,23.27,31.46,31.27,27.25
    1902,24.93,26.58,29.77,31.78,33.73,32.91,30.92,30.73,29.8,29.12,26.31,24.04,29.22,25.75,31.76,31.09,26.49
    1903,23.44,25.03,27.83,31.39,32.91,33,31.34,29.98,29.85,29.04,26.08,23.65,28.47,24.24,30.71,30.92,26.26
    1904,22.5,24.73,28.21,32.02,32.64,32.07,30.36,30.09,30.04,29.2,26.36,23.63,28.49,23.62,30.95,30.66,26.4
    1905,22,22.83,26.68,30.01,33.32,33.25,31.44,30.68,30.12,30.67,27.52,23.82,28.3,22.25,30,31.33,26.57
    1906,22.28,23.69,27.31,31.93,34.11,32.19,31.01,30.3,29.92,29.55,27.6,24.72,28.73,23.03,31.11,30.86,27.29
    1907,24.46,24.01,27.04,31.79,32.68,31.92,31.05,29.58,30.67,29.87,27.78,24.44,28.65,24.23,29.92,30.8,27.36
    1908,23.57,25.26,28.86,32.42,33.02,33.12,30.61,29.55,29.59,29.35,26.88,23.73,28.83,24.42,31.43,30.72,26.64
    1909,22.67,24.36,29.22,30.79,33.06,31.7,29.81,29.81,30.06,29.25,27.69,23.69,28.38,23.52,31.02,30.33,26.88
    1910,23.24,25.16,28.48,31.42,33.51,31.84,30.42,29.86,29.82,28.91,26.32,23.37,28.53,24.2,31.14,30.48,26.2
    ...
    
  ```

   <details>
      <summary>SEE SOLUTION</summary>

   ```python
     def getlistmaxtemperatures(filepath):
         f = open(filepath, 'r')
         content = f.readlines()
         output = []
         for line in content:
             split_line = line.split(",")
             output.append([split_line[0], max(split_line[1:])])
         f.close()
         return output
     # Other solution
     def getlistmaxtemperatures_loop(filepath):
         f = open(filepath, 'r')
         content = f.readlines()
         output = []
         for line in content:
             split_line = line.split(",")
             max_temp = -100.0
             for temp in split_line[1:]:
                 tempmonth = float(temp)
                 if max_temp < tempmonth:
                     max_temp = tempmonth
             output.append([split_line[0], max_temp])
         f.close()
         return output

   ```

</details>

12. Definir una función que, dada la ruta de un fichero con un extracto bancario, devuelva el balance (positivo o
    negativo) de la cuenta, así como el importe de los 3 mayores movimientos

Extracto del fichero:

   ```console 
   Fecha_operación;fecha_valor;concepto;importe
   30/10/2023;30/10/2023;Netflix;12.32
   31/10/2023;31/10/2023;Supermercado;50.00
   01/11/2023;01/11/2023;Gasolina;45.25
   02/11/2023;02/11/2023;Restaurante;30.75
   03/11/2023;03/11/2023;Electricidad;80.00
   ...
   ```
    
   <details>
         <summary>SEE SOLUTION</summary>

   ```python
    def devuelvebalance_gastos(rutafichero):
      f = open(rutafichero, 'r')
      lineas = f.readlines()
      lista_movimientos = []
      balance = 0
      for i in range(1, len(lineas)):
         split_line = lineas[i].strip().split(";")
         importe = float(split_line[len(split_line) - 1])
         balance += importe
         lista_movimientos.append(importe)
      lista_movimientos.sort()
      return balance, lista_movimientos[-3:]
  ```

 </details>
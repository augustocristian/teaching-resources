# Python exercises VOL I

## Contenido

- [Ejercicios condicionales](#ejercicios-de-condicionales)
- [Ejercicios con bucles](#ejercicios-de-bucles)
- [Ejercicios con funciones](#ejercicios-con-funciones)
- [Ejercicios con ficheros](#ejercicios-con-ficheros)

## Ejercicios de condicionales

Proximamente...

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

1. Definir una función DNIValido que, dado un número de DNI, retorne True si es válido y False si no lo es. Para que un
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

## Ejercicios con ficheros

1. Implementar una función que dada la ruta de un [fichero con las temperaturas](data/31_FI_Pyhton_temperatures.csv)  en
   el que se tienen el año con las temperaturas de sus doce meses separadas por comas, devuelva una lista de
   tuplas   `[Año,máxTemp]  `
   
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


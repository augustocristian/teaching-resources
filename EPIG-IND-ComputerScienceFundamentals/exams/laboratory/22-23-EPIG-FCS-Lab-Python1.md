# Laboratory Exam Python(FOR) Computer Science Fundamentals 17th November 2022

1. Se nos ha encargado realizar un pequeño programa que muestre el cambio actual de varias criptodivisas. El programa
   tomará por teclado una cantidad en dólares y una opción, siendo las opciones disponibles: (1) Bitcoin (1
   BTC=17.362,4\$), (2) Ethereum (1 ETH=1278,85\$), (3) Monero (1 XMR= 124,99\$) y Dogecoin (1 DOGE = 0,08 USD). La
   salida del programa tiene que ser como la siguiente:

   ```console
   > ¿Qué cantidad de dólares quieres convertir? 
        3.0
   > Introduce que criptomoneda quieres:
       1) Bitcoin (BTC)
       2) Ethereum (ETH)
       3) Monero (XMR)
       4) Dogecoin (DOGE)
        2
   > 3.0 $ son 0,00234585…. ETH
    ```
2. Se nos ha encargado realizar un pequeño programa que valide si una cuenta de banco es correcta. El programa tomará
   por teclado la cuenta bancaria la cual será válida si cumple el estándar IBAN: tiene que tener una longitud de 24
   caracteres, siendo los dos primeros caracteres letras MAYÚSCULAS. El programa debe mostrar por pantalla una salida
   como la siguiente:
   ```console
   > Dame la cuenta bancaria con el BIC: ES1900720101510528170010
     La cuenta ES1900720101510528170010 es VÁLIDA
   > Dame la cuenta bancaria con el BIC: E11900720101510528170010
     La cuenta E11900720101510528170010 es INVÁLIDA
    ```
3. Realizar un programa que permita a dos jugadores jugar a piedra papel o tijera. El programa pedirá por teclado a
   ambos jugadores que seleccionen opción, siendo: (1) Piedra, (2) Papel (3) Tijera de manera iterativa hasta que uno de
   los dos gane. La salida tiene que ser similar a la siguiente:

   ```console
   > Opciones:
      1) Piedra
      2) Papel
      3) Tijera  
     El jugador A selecciona: 
      1
     El jugador B selecciona: 
      1
   > ¡Nadie ha ganado!
   > Opciones:
     1) Piedra
     2) Papel
     3) Tijera  
    El jugador A selecciona: 
     1
    El jugador B selecciona: 
     2
   > ¡Uno de los dos jugadores ha ganado!
    ```
4. Realiza un programa que permita mostrar por pantalla dos tipos de matrices con padding. El programa pedirá por
   teclado las dimensiones (N y M) y un número para seleccionar el tipo a imprimir. El primer tipo tiene un padding
   estándar (rodeada de ceros) mientras que el segundo tipo tiene un padding intra-fila y columna. Véase el ejemplo:

    1. Padding:
      ```console
       0  0   0  0 
       0 A22 A23 0
       0 A32 A33 0
       0  0   0  0
      ```
    2. Padding intra-fila:
      ```console
       A11 0 A13 0  
       0 A22 0 A24  
       A31 0 A33 0  
       0 A42 0 A44
      ```
   El comportamiento del programa tiene que ser similar al siguiente:
   ```console
    > ¿Qué número de filas tiene la matriz (N)?
       3
    > ¿Qué número de columnas tiene la matriz (M)?
       3
    > Introduce el tipo de matriz a imprimir:
      1) Padding Standard
      2) Padding intra-fila-columna
       1
    >  0   0   0  
       0  A22  0  
       0   0   0
     ```
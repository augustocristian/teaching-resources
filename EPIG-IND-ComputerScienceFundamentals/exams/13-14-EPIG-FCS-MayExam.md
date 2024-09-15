# Exam Computer Science Fundamentals 20th May 2014

1. Considera la expresión "El número x es par y menor que 20". Escribe una expresión booleana en Python sobre la
   variable x que tenga el mismo significado que la expresión anterior.
   ```text
   
   
   
   
   
   
   
   ```

2. Aplica la negación a la expresión anterior, aplica las leyes de De Morgan a esa expresión y escribe el resultado sin
   que aparezcan negaciones. ¿Qué devolvería la expresión para x=12?
   ```text
   
   
   
   
   
   
   
   ```

3. Dada la función:

   ```python
   def contar(a,b):
         f = open('num.txt','r')
         c = 0      
         for n in f:          
            if int(n) > a and int(n) < b:              
               c = c + 1      
         f.close()     
         return c 
   ```

   y el fichero:

   ```txt
   7 
   3 
   5 
   1 
   3 
   5 
   2 
   ```
   
   Indica el resultado de las siguientes llamadas:
   
   | Expresión    | Resultado |
   |--------------|-----------|
   | contar(1,5)  |           |  
   | contar(4,3)  |           | 
   | contar(7,10) |           |

4. Se tienen las siguientes variables: a = 4, b = 9, c = 2.0, d = "xx". Para cada expresión de la tabla siguiente,
   indicar si la expresión es correcta o no. Si lo fuera, indicar el resultado y su tipo. Si es incorrecta indicar
   brevemente por qué. :

   | Expresión      | ¿Correcta? | Tipo y resultado / Causa del error |
   |----------------|------------|------------------------------------|
   | `b/a`          |            |                                    |
   | `d*b/a`        |            |                                    |
   | `c**a+1`       |            |                                    |
   | `a%b!=c`       |            |                                    |
   | `float(b/a*2)` |            |                                    |

5. La siguiente función debería calcular la media de tres números:
   ```python
   define media(n1 n2 n3);
      M = n1+n2+n3 / flota(2)      
      retrun m
   ```
    1. Reescríbela corrigiendo los errores
       ```python
       # Resolve the exercise here
       
 
       
       ```
    2. Tenemos un fichero con notas. Cada línea almacena 3 notas de cada alumno separadas por comas. Haz un programa
       que, utilizando la función del apartado anterior, muestre en pantalla la nota media de aquellos alumnos que han
       aprobado.
       ```python
        # Resolve the exercise here



       
       
       


       ```

6. Explica en breves palabras qué se conoce como path y nombre completo de un archivo.
   ```text



   
   ```
7. Enumerar las categorías de Software de Sistema.
   ```text


   
   ```

8. Se desea diseñar e implementar una base de datos que recopila información sobre cirujanos, intervenciones e
   instrumental quirúrgico de una clínica.

   Sobre los cirujanos interesa saber su nombre y teléfono. Sobre las
   intervenciones, su nombre, el identificador del cirujano que las realiza, su duración en minutos y si se necesita
   avisar al banco de sangre o no. Sobre el instrumental, el nombre y el tipo. El tipo sólo puede ser ‘Retractor’,
   ‘Pinza’, ‘Tijera’, ‘Bisturí’.

   Un cirujano puede realizar varias intervenciones. Un instrumento puede utilizarse en
   varias intervenciones y una intervención puede usar varios instrumentos.

   Es posible que en alguna tabla haya que añadir campos para relacionarlas. Es posible que haya que añadir alguna tabla
   para implementar alguna relación N:M.
   
   **Se pide: Diseñar la base de datos que permita almacenar y gestionar estos datos y dibujar los correspondientes
   diagramas Entidad-Relación.**
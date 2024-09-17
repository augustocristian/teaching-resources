# Laboratory Exam Access Computer Science Fundamentals 20th October 2022

Impleméntese en Access las tablas, relaciones y restricciones del siguiente modelo entidad relación de una cierta base
de datos (aproximación) con la estructura de los diferentes Clubes
de la región, alineados con el Consejo Superior de Deportes (CSD):

1. Asígnense las relaciones y cree las claves foráneas (FK) oportunas (Intencionadamente, las relaciones señaladas entre
   las entidades no se corresponden con las respectivas claves,
   tampoco están representadas las claves foráneas.)
2. Los atributos licencia y CIF son cadenas de 5 y 8 caracteres respectivamente, nótese que son las claves primarias de
   las entidades.
3. Los valores posibles para el atributo Nivel de la entidad Entrenador son: I, II, III, IV, V. Se
   controlará que no se puedan introducir otros.
4. El atributo Disciplina de la entidad Deportista puede no existir.
5. El valor del atributo EsOlimpica de la entidad Federación es booleano y por defecto será “No”.
6. Las fechas (FechaNac y FechaCreac) deben de ser del tipo adecuado y controlarse que no se pueda introducir una fecha
   inválida(futura).
7. El atributo presupuesto de la entidad Federación debe de ser del tipo adecuado, no puede ser negativo.
8. Los atributos Nombre, Apellidos, Comunidad y Email de las distintas entidades son cadenas de caracteres, debe de
   requerirse su introducción.

   ```mermaid
   erDiagram
       Entrenador {
           string Licencia PK
           date fechaNac
           string nombre
           string apellidos
           string nivel
       }
   
       Deportista {
           string Licencia PK
           date fechaNac
           string nombre
           string apellidos
           string disciplina
       }
   
       Club {
           string Licencia PK
           date fechaCreac
           string nombre
           string comunidad
           string email
       }
   
       Federacion {
           string CIF PK
           date fechaCreac
           string nombre
           boolean esOlimpica
           float presupuesto
       }
   
       CSD {
           string CIF PK
           string nombre
       }
   
       Entrenador ||--o{ Deportista: ""
       Club ||--o{ Deportista: ""
       Federacion ||--o{ Club: ""
       CSD ||--o{ Federacion: ""
       Club ||--o{ Entrenador: ""
   ```

2. Sobre la base de datos Ingeniería que se proporciona rellena con datos, realícense las
   siguientes tareas:
    1. **Consulta 1**: Listado de Ingenieros (Nombre y Apellidos), ordenados alfabéticamente, adscritos al departamento
       de Calidad con la suma de los presupuestos de sus proyectos de más de 50.000€.
    2. **Consulta 2**: Listado de proyectos que participan ingenieros con el departamento ubicado en Gijón y contratados
       después del 1/08/2009
    3. **Informe**: Listado ingenieros con su departamento ordenados por apellidos y nombre.  
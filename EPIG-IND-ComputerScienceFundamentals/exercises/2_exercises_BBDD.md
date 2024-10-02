# DDBB Ordenadores

Dibujar el modelo entidad-relación de la base de datos ordenadores con las siguientes entidades:

- `Ordenadores (PCs)`: tienen un ID y un precio.
- `Procesador (CPU)`: tienen un ID y una descripción.
- `Disco`: tiene un ID, una descripción y una capacidad.
- `Tarjeta Gráfica`: tiene un ID, una capacidad y una descripción.
- `Memoria`: tiene un ID, una capacidad y una velocidad.
- `Fabricante`: tiene un ID, una dirección, un teléfono y un CIF.
- `Tipo de procesador`: tiene un ID, una descripción y un tipo de litografía.
- `Tipo de memoria`: tiene un ID y una descripción.

Además sabemos que:

Todos los componentes (procesadores, tarjetas gráficas, memoria y discos) tienen un fabricante que puede ser compartido
por todos ellos.

Los procesadores tienen un tipo de procesador asociado, este puede ser compartido por varios de ellos.

Tanto tarjetas gráficas como memorias van asociados a un tipo de memoria que puede ser común a todas ellas.

Los ordenadores tienen un componente de cada tipo (procesadores, tarjetas gráficas, memoria y discos), estos componentes
pueden ser compartidos por todos ellos.

<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
    pcs {
        VARCHAR(20) pcid PK
        VARCHAR(20) id_cpu FK
        VARCHAR(20) id_disco FK
        VARCHAR(20) id_tgrafica FK
        VARCHAR(20) id_memoria FK
        DECIMAL(10) precio
    }

    cpu {
        VARCHAR(20) id_cpu PK
        VARCHAR(100) descripcion
        VARCHAR(20) id_fabricante FK
        VARCHAR(20) id_tipo_procesador FK
    }

    tipo_procesador {
        VARCHAR(20) id_tipo_procesador PK
        VARCHAR(100) descripcion
        INTEGER t_litografia
    }

    disco {
        VARCHAR(20) id_disco PK
        VARCHAR(100) descripcion
        INTEGER capacidad
        VARCHAR(20) id_fabricante FK
    }

    memoria {
        VARCHAR(20) id_memoria PK
        VARCHAR(20) id_tipo_memoria FK
        VARCHAR(20) id_fabricante FK
        INTEGER capacidad
        INTEGER velocidad
    }

    fabricante {
        VARCHAR(20) id_fabricante PK
        VARCHAR(80) direccion
        VARCHAR(15) telf
        VARCHAR(9) CIF
    }

    tgrafica {
        VARCHAR(20) id_tgrafica PK
        VARCHAR(20) id_tipo_memoria FK
        VARCHAR(20) id_fabricante FK
        INTEGER capacidad
        VARCHAR(100) descripcion
    }

    tipo_memoria {
        VARCHAR(20) id_tipo_memoria PK
        VARCHAR(100) descripcion
    }

%% Relación entre cpu y su fabricante y tipo de procesador
    cpu ||--o{ tipo_procesador: ""
    cpu ||--o{ pcs: ""
%% Relaciones de fabricante
    fabricante ||--o{ cpu: ""
    fabricante ||--o{ disco: ""
    fabricante ||--o{ memoria: ""
    fabricante ||--o{ tgrafica: ""
%% Relación entre disco y su fabricante
    disco ||--o{ pcs: ""
%% Relación entre memoria y sus componentes
    memoria ||--o{ tipo_memoria: ""
    memoria ||--o{ pcs: ""
%% Relación entre tgrafica y sus componentes
    tgrafica ||--o{ tipo_memoria: ""
    tgrafica ||--o{ pcs: ""
```

</details>

# DDBB Hospitales

Dibujar el modelo entidad-relación de la base de datos hospitales compuesto de las siguientes entidades:

- `Hospital`: con un ID, un nombre, dirección y teléfono.
- `Sala`: con un ID, un nombre, y un número de camas.
- `Estancias`: con un ID, una fecha de entrada y salida.
- `Doctores`: con un ID y un nombre.
- `Plantilla`: con un ID, un nombre, una función, turno y salario.
- `Especialidades`: con su ID y su nombre.
- `Enfermedades`: con un ID y su nombre.
- `Pacientes`: con su ID, nombre, dirección, fecha de nacimiento, sexo y número de la seguridad social.

Además sabemos que:

Un paciente puede realizar una o varias estancias, asociadas a una misma o diferentes enfermedades.

Las estancias pueden realizarse en una misma o diferentes salas. Estas salas pertenecen a un hospital, el cual puede
tener varias de estas.

Una sala tiene asociada una plantilla, compuesta por uno o varios empleados.

El hospital tiene uno o varios doctores, pertenecientes a una especialidad.

<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
    hospital {
        VARCHAR(5) Id_Hospital PK
        VARCHAR(20) nombreHospital
        VARCHAR(30) direccion
        VARCHAR(20) telefono
    }

    pacientes {
        VARCHAR(8) Id_Paciente PK
        VARCHAR(20) nombrePaciente
        VARCHAR(20) direccion
        DATE fechaNacimiento
        VARCHAR(1) Sexo
        VARCHAR(12) NSS
    }

    enfermedades {
        VARCHAR(5) Id_Enfermedad PK
        VARCHAR(20) nombreEnfermedad
    }

    estancias {
        INTEGER Id_Estancia PK
        VARCHAR(8) Id_Paciente FK
        DATE fechaEntrada
        DATE fechaSalida
        VARCHAR(5) Id_Hospital FK
        INTEGER Id_Sala FK
        VARCHAR(5) Id_Enfermedad FK
    }

    sala {
        INTEGER Id_Sala PK
        VARCHAR(5) Id_Hospital FK
        VARCHAR(25) nombreSala
        INTEGER numCamas
    }

    doctor {
        VARCHAR(8) Id_Doctor PK
        VARCHAR(5) Id_Hospital FK
        VARCHAR(25) nombreDoctor
        VARCHAR(5) Id_Especialidad FK
    }

    plantilla {
        VARCHAR(8) Id_Empleado PK
        VARCHAR(5) Id_Hospital FK
        INTEGER Id_Sala FK
        VARCHAR(25) nombreEmpleado
        VARCHAR(25) funcion
        VARCHAR(1) turno
        FLOAT salarioanual
    }

    especialidades {
        VARCHAR(5) Id_Especialidad PK
        VARCHAR(15) nombreEspecialidad
    }

%% Relaciones
    especialidades ||--o{ doctor: ""
    pacientes ||--o{ estancias: ""
    enfermedades ||--o{ estancias: ""
    hospital ||--o{ sala: ""
    hospital ||--o{ doctor: ""
    sala ||--o{ estancias: ""
    hospital ||--o{ plantilla: ""

```

</details>

# DDBB Pedidos

Dibujar el modelo entidad relación de la base de datos pedidos online con las siguientes entidades:

- `Productos`: con su ID, nombre, precio, estado y fecha de creación.
- `Etiquetas de producto`: Con su ID y nombre.
- `Pedidos`: con su ID, estado y fecha de creación.
- `País`: con su ID (código), nombre y nombre del continente al que pertenece.
- `Tienda`: con su ID, nombre, fecha de creación y su administrador.
- `Usuarios`: con su ID, nombre completo y fecha de registro.
- `Temporada`: con su ID, fecha de inicio y fecha de fin.

Además sabemos que:

Un producto puede estar en varios pedidos en cierta cantidad, a la vez que un pedido está compuesto por varios
productos. Los productos pueden tener una o varias etiquetas y una etiqueta estar en varios productos.

Un usuario pertenece a un país, a su vez este puede tener varios usuarios. De idéntica manera una tienda pertenece a un
país y un país tiene varias tiendas.

Las tiendas tienen varios productos, pero cada producto es vendido únicamente por una tienda.

Las tiendas organizan su facturación en temporadas, una tienda puede tener varias temporadas.

Existe un usuario único que es el administrador de la tienda, este a su vez puede administrar diferentes tiendas.

<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
    productos {
        INTEGER Id_Producto PK
        INTEGER Id_Vendedor FK
        VARCHAR(25) nombre
        INTEGER precio
        VARCHAR(1) estado
        DATE fechaCreacion
    }

    etiquetas_producto {
        INTEGER Id_Producto FK
        VARCHAR(5) Id_Etiqueta FK
    }

    etiquetas {
        VARCHAR(5) Id_Etiqueta PK
        VARCHAR(25) nombre
    }

    items_pedido {
        INTEGER ID_Pedido FK
        INTEGER ID_Producto FK
        INTEGER cantidad
    }

    pedidos {
        INTEGER Id_Pedido PK
        INTEGER ID_Usuario FK
        VARCHAR(1) estado
        DATE fechaCreacion
    }

    pais {
        VARCHAR(4) Id_Pais PK
        VARCHAR(25) nombre
        VARCHAR(25) nombreContinente
    }

    tienda {
        INTEGER Id_Pais PK
        VARCHAR(4) Id_Pais FK
        VARCHAR(25) nombre
        DATE fechaCreacion
        INTEGER Id_Admin FK
    }

    Usuarios {
        INTEGER Id_Usuario PK
        VARCHAR(25) nombreCompleto
        DATE fechaCreacion
        VARCHAR(4) Id_Pais FK
    }

    Temporada {
        INTEGER Id_Temporada PK
        INTEGER Id_Vendedor FK
        VARCHAR(4) Id_Pais FK
        DATE fechaInicio
        DATE fechaFin
    }

%% Relaciones
    productos ||--o{ etiquetas_producto: ""
    etiquetas ||--o{ etiquetas_producto: ""
    pedidos ||--o{ items_pedido: ""
    productos ||--o{ items_pedido: ""
    Usuarios ||--o{ pedidos : ""
    pais ||--o{ tienda: ""
    pais ||--o{ Usuarios: ""
    tienda ||--o{ Temporada: ""
    tienda ||--o{ productos: ""


```

</details>

# DDBB MarketPlace

Dibujar el modelo entidad-relación de la base de datos:

- `Autores`: tiene un ID, nombre, país y URL
- `Libro`: tiene un ID o ISBN, un año de publicación, un título y un precio
- `Editorial`: tiene un ID, un nombre, dirección, teléfono y URL
- `Vendedor online`: tiene un ID, un email y una URL
- `Cesta de la compra`: tiene un ID y un número de referencia
- `Comprador`: tiene un ID, un nombre, dirección, email y número de tarjeta de crédito
- `Pedido`: tiene un ID, fecha y dirección

Además sabemos que:

Un libro puede estar escrito por uno o varios autores, pero pertenece a una sola editorial, la cual tiene varios libros.

Un vendedor tiene en stock varios libros, a su vez un mismo libro puede estar ofrecido por varios vendedores.

Una cesta de la compra pertenece a un solo comprador, este tiene una única cesta en la que puede tener varios libros, y
de estos varias unidades.

Un pedido pertenece a un solo cliente, los clientes pueden tener varios pedidos. Un pedido se compone de varios libros,
los cuales pueden estar en varios pedidos en una serie de unidades.

<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
%% Entidades
    Autor {
        INTEGER Id_Autor
        VARCHAR(25) nombre
        VARCHAR(25) pais
        VARCHAR(35) URL
    }

    Autoria {
        INTEGER Id_Autoria PK
        INTEGER ISBN FK
        INTEGER Id_Autor FK
    }

    Libro {
        INTEGER ISBN PK
        INTEGER anioPublicacion
        VARCHAR(25) titulo
        FLOAT precio
    }

    Editorial {
        INTEGER Id_Editorial PK
        VARCHAR(25) nombre
        VARCHAR(35) direccion
        VARCHAR(9) telefono
        VARCHAR(35) URL
    }

    VendedorOnline {
        INTEGER Id_Vendedor PK
        VARCHAR(25) email
        VARCHAR(35) URL
    }

    CestaCompra {
        INTEGER Id_Cesta PK
        INTEGER Id_Comprador FK
        INTEGER cantidad
    }

    Comprador {
        INTEGER Id_Comprador PK
        VARCHAR(25) nombre
        VARCHAR(35) direccion
        VARCHAR(25) email
        VARCHAR(25) numTarjeta
    }

    Pedido {
        INTEGER Id_Pedido
        DATE fecha
        VARCHAR(35) direccionEnvio
    }
    ItemsCesta{
        INTEGER Id_ItemsCesta PK
        INTEGER Id_Cesta FK
        INTEGER ISBN FK
        INTEGER cantidad
    }

%% Relaciones
    Autor ||--o{ Autoria: ""
    Libro ||--o{ Autoria: ""
    Libro }o--|| Editorial: ""
    VendedorOnline ||--o{ Libro: ""
    Comprador ||-- ||CestaCompra: ""
    Comprador ||--o{ Pedido: ""
%% Relaciones N:M
    CestaCompra ||--o{ ItemsCesta: ""
    Libro ||--o{ ItemsCesta: ""
    VendedorOnline ||--o{ Libro: ""
    Libro ||--o{ Pedido: ""

```

</details>

# DDBB Protectora de animales:

Dibujar el modelo entidad-relación de la base de datos protectora de animales con las siguientes entidades:

- `Centro`: tiene un identificador, una dirección, un teléfono, un email y un dueño.
- `Recinto`: tiene un id, una superficie y un tipo.
- `Animal`: tiene un id (microchip), un tipo, una fecha de entrada, una fecha de salida y un peso.
- `Vacuna`: tiene un id, un nombre y una fecha de caducidad.
- `Voluntario`: tiene un id, nombre, email, teléfono y una dirección.
- `Adopción`: tiene un id, una fecha y unas observaciones.
- `Colaboración`: tiene un id y una fecha.
- `Adoptante`: tiene un id, un nombre, una dirección y un teléfono.

Además sabemos que:

Un centro tiene varios recintos, los cuales pertenecen a un único centro. En estos recintos pueden albergar a varios
animales.

Un animal puede tener varias vacunas, a su vez varios animales pueden estar vacunados con la misma vacuna.

Los voluntarios pueden realizar colaboraciones, estás consisten en llevar a uno o varios animales a su casa durante un
fin de semana.

Los adoptantes realizan adopciones de un animal, un adoptante puede realizar varias adopciones.


<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram

%% Entidades
    CENTRO {
        int id PK
        string direccion
        string telefono
        string email
        string dueno
    }

    RECINTO {
        int id PK
        int Id_Centro FK
        float superficie
        string tipo

    }

    ANIMAL {
        int microchip PK
        int Id_Recinto FK
        string tipo
        date fecha_entrada
        date fecha_salida
        float peso
    }

    VACUNA {
        int id PK
        string nombre
        date fecha_caducidad
    }

    VOLUNTARIO {
        int id PK
        string nombre
        string email
        string telefono
        string direccion
    }

    ADOPCION {
        int id PK
        int Id_Animal FK
        int Id_Adoptante FK
        date fecha
        string observaciones

    }

    COLABORACION {
        int id PK
        int Id_Voluntario FK
        date fecha
    }

    ADOPTANTE {
        int id PK
        string nombre
        string direccion
        string telefono
    }
%%Tablas intermedias para la N a M    
    COLABORACION_ANIMAL {
        int id PK
        int Id_Colaboracion FK
        int Id_Animal FK
    }
    ANIMALES_VACUNAS {
        int id PK
        int Id_Animal FK
        int Id_Vacuna FK
    }

%% Relaciones
    CENTRO ||--o{ RECINTO : ""
    RECINTO ||--o{ ANIMAL : ""


    VOLUNTARIO ||--o{ COLABORACION : ""
    ANIMAL ||--o{ COLABORACION_ANIMAL : ""
    COLABORACION ||--o{ COLABORACION_ANIMAL : ""

    ADOPTANTE ||--o{ ADOPCION : ""
    ADOPCION ||--|| ANIMAL : ""
    ANIMAL ||--o{ ANIMALES_VACUNAS : ""
    VACUNA ||--o{ ANIMALES_VACUNAS : ""
    
```

</details>

# DDBB Empresas de Construcción:

Dibujar el modelo entidad-relación de la base de datos de unas empresas de construcción con las siguientes entidades:

- `Empresa`: tienen un id (CIF), un nombre y una dirección fiscal.
- `Edificación`: tienen un id (numcatrastro), un número de plantas, una superficie y una fecha de licitación.
- `Aparejador`: tiene un id (numcolegiado), una edad, un nombre, una dirección, un correo y un salario.
- `Obrero`: tiene un id, un DNI, un nombre, una edad y un salario
- `Arquitecto`: tiene un id (numcolegiado), una edad, un nombre, dirección, correo y un salario
- `Capataz`: tiene un id, un DNI, un nombre, una edad y un salario.
- `Plantilla`: tiene un Id y un nombre

Además sabemos que:

Una empresa puede trabajar en varias edificaciones, a su vez en una edificación pueden trabajar varias plantillas

Las edificaciones tienen asignado un arquitecto y un aparejador, los arquitectos y aparejadores pueden tener asignadas
varias edificaciones.

Los obreros pertenecen a una única plantilla, esta plantilla está formada por varios obreros y un capataz.El capataz
puede dirigir varias plantillas.

En una edificación pueden trabajar varias plantillas, a su vez una plantilla puede trabajar en varias edificaciones.


<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
%% Entidades
    EMPRESA {
        string CIF PK
        string nombre
        string direccion_fiscal
    }

    EDIFICACION {
        int numcatrastro PK
        int Id_Arquitecto FK
        int Id_Aparejador FK
        int numero_plantas
        float superficie
        date fecha_licitacion
    }

    APAREJADOR {
        int numcolegiado PK
        int edad
        string nombre
        string direccion
        string correo
        float salario
    }

    OBRERO {
        int id PK
        string DNI
        string nombre
        int edad
        float salario
    }

    ARQUITECTO {
        int numcolegiado PK
        int edad
        string nombre
        string direccion
        string correo
        float salario
    }

    CAPATAZ {
        int id PK
        string DNI
        string nombre
        int edad
        float salario
    }

    PLANTILLA {
        int id PK
        int Id_Capataz FK
        string nombre
    }

    PLANTILLA_EDIFICACION {
        int id PK
        int Id_Plantilla FK
        int Id_Edificacion FK
    }
    EMPRESA_EDIFICACION {
        int id PK
        int Id_Empresa FK
        int Id_Edificacion FK
    }

%% Relaciones
    EMPRESA ||--o{ EMPRESA_EDIFICACION : ""
    EDIFICACION ||--o{ EMPRESA_EDIFICACION : ""

    EDIFICACION }o--|| ARQUITECTO : ""
    EDIFICACION }o--|| APAREJADOR : ""

    EDIFICACION ||--o{ PLANTILLA_EDIFICACION : ""
    PLANTILLA ||--o{ PLANTILLA_EDIFICACION : ""

    PLANTILLA }|--|| CAPATAZ : ""
    PLANTILLA ||--o{ OBRERO : ""

```

</details>

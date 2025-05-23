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
- `Plantilla`: con un ID, un nombre y turno.
- `Especialidades`: con su ID y su nombre.
- `Enfermedades`: con un ID y su nombre.
- `Pacientes`: con su ID, nombre, dirección, fecha de nacimiento, sexo y número de la seguridad social.
- `Empleados`: con su ID, nombre, apellidos, puesto y salario.

Además sabemos que:

Un paciente puede realizar una o varias estancias, asociadas a una misma o diferentes enfermedades.

Las estancias pueden realizarse en una misma o diferentes salas. Estas salas pertenecen a un hospital, el cual puede
tener varias de estas.

Una sala tiene asociada una plantilla, compuesta por uno o varios empleados. Una misma plantilla puede trabajar en varias Salas.

El hospital tiene uno o varios doctores, pertenecientes a una especialidad.

<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
    Hospital {
        VARCHAR(5) Id_Hospital PK
        VARCHAR(20) nombreHospital
        VARCHAR(30) direccion
        VARCHAR(20) telefono
    }

    Pacientes {
        VARCHAR(8) Id_Paciente PK
        VARCHAR(20) nombrePaciente
        VARCHAR(20) direccion
        DATE fechaNacimiento
        VARCHAR(1) Sexo
        VARCHAR(12) NSS
    }

    Enfermedades {
        VARCHAR(5) Id_Enfermedad PK
        VARCHAR(20) nombreEnfermedad
    }

    Estancias {
        INTEGER Id_Estancia PK
        VARCHAR(8) Id_Paciente FK
        DATE fechaEntrada
        DATE fechaSalida
        VARCHAR(5) Id_Hospital FK
        INTEGER Id_Sala FK
        VARCHAR(5) Id_Enfermedad FK
    }

    Sala {
        INTEGER Id_Sala PK
        VARCHAR(5) Id_Hospital FK
        VARCHAR(25) NombreSala
        INTEGER NumCamas
    }

    Doctor {
        VARCHAR(8) Id_Doctor PK
        VARCHAR(5) Id_Hospital FK
        VARCHAR(25) NombreDoctor
        VARCHAR(5) Id_Especialidad FK
    }

    Plantilla {
        VARCHAR(8) Id_Plantilla PK
        INTEGER Id_Sala FK
        VARCHAR(25) Nombre
        VARCHAR(1) Turno
    }

    Especialidades {
        VARCHAR(5) Id_Especialidad PK
        VARCHAR(15) NombreEspecialidad
    }

%% Relaciones
    Especialidades ||--o{ Doctor: ""
    Pacientes ||--o{ Estancias: ""
    Enfermedades ||--o{ Estancias: ""
    Hospital ||--o{ Sala: ""
    Hospital ||--o{ Doctor: ""
    Sala ||--o{ Estancias: ""
    Plantilla ||--o{ Sala: ""

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
    Productos {
        INTEGER Id_Producto PK
        INTEGER Id_Vendedor FK
        VARCHAR(25) Nombre
        INTEGER Precio
        VARCHAR(1) Estado
        DATE FechaCreacion
    }

    Etiquetas_Producto {
        INTEGER Id_Etiq_Prod PK
        INTEGER Id_Producto FK
        VARCHAR(5) Id_Etiqueta FK
    }

    Etiquetas {
        VARCHAR(5) Id_Etiqueta PK
        VARCHAR(25) Nombre
    }

    Items_Pedido {
        INTEGER Id_Item_Ped PK
        INTEGER Id_Pedido FK
        INTEGER Id_Producto FK
        INTEGER Cantidad
    }

    Pedidos {
        INTEGER Id_Pedido PK
        INTEGER Id_Usuario FK
        VARCHAR(1) Estado
        DATE FechaCreacion
    }

    Pais {
        VARCHAR(4) Id_Pais PK
        VARCHAR(25) Nombre
        VARCHAR(25) NombreContinente
    }

    Tienda {
        INTEGER Id_Tienda PK
        VARCHAR(4) Id_Pais FK
        VARCHAR(25) Nombre
        DATE FechaCreacion
        INTEGER Id_Admin FK
    }

    Usuarios {
        INTEGER Id_Usuario PK
        VARCHAR(25) NombreCompleto
        DATE FechaCreacion
        VARCHAR(4) Id_Pais FK
    }

    Temporada {
        INTEGER Id_Temporada PK
        INTEGER Id_Vendedor FK
        VARCHAR(4) Id_Pais FK
        DATE FechaInicio
        DATE FechaFin
    }

%% Relaciones
    Productos ||--o{ Etiquetas_Producto: ""
    Etiquetas ||--o{ Etiquetas_Producto: ""
    Pedidos ||--o{ Items_Pedido: ""
    Productos ||--o{ Items_Pedido: ""
    Usuarios ||--o{ Pedidos : ""
    Pais ||--o{ Tienda: ""
    Pais ||--o{ Usuarios: ""
    Tienda ||--o{ Temporada: ""
    Tienda ||--o{ Productos: ""
    Usuarios ||--o{ Tienda: ""


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

Un libro puede estar escrito por uno o varios autores y un autor puede escribir muchos libros.

Un libro  pertenece a una sola editorial, la cual tiene varios libros.

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
        VARCHAR(25) Nombre
        VARCHAR(25) Pais
        VARCHAR(35) URL
    }

    Autoria {
        INTEGER Id_Autoria PK
        INTEGER ISBN FK
        INTEGER Id_Autor FK
    }

    Libro {
        INTEGER ISBN PK
        INTEGER AnoPublicacion
        VARCHAR(25) Titulo
        FLOAT Precio
    }

    Editorial {
        INTEGER Id_Editorial PK
        VARCHAR(25) Nombre
        VARCHAR(35) Direccion
        VARCHAR(9) Telefono
        VARCHAR(35) URL
    }

    VendedorOnline {
        INTEGER Id_Vendedor PK
        VARCHAR(25) Email
        VARCHAR(35) URL
    }

    CestaCompra {
        INTEGER Id_Cesta PK
        INTEGER Id_Comprador FK
        INTEGER Cantidad
    }

    Comprador {
        INTEGER Id_Comprador PK
        VARCHAR(25) Nombre
        VARCHAR(35) Direccion
        VARCHAR(25) Email
        VARCHAR(25) NumTarjeta
    }

    Pedido {
        INTEGER Id_Pedido
        DATE Fecha
        VARCHAR(35) DireccionEnvio
    }
    ItemsCesta{
        INTEGER Id_ItemsCesta PK
        INTEGER Id_Cesta FK
        INTEGER ISBN FK
        INTEGER Cantidad
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

Los voluntarios pueden realizar una o varias colaboraciones, una colaboración es realizada exclusivamente por un voluntario.

Las colaboraciones consisten en llevar a uno o varios animales a su casa durante un fin de semana, un animal puede participar en varias colaboraciones. 

Los adoptantes realizan adopciones de un animal, un adoptante puede realizar varias adopciones.


<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram

%% Entidades
    Centro {
        int Id_Centro PK
        string Direccion
        string Telefono
        string Email
        string Dueno
    }

    Recinto {
        int Id_Recito PK
        int Id_Centro FK
        float Superficie
        string Tipo

    }

    Animal {
        int Microchip PK
        int Id_recinto FK
        string Tipo
        date FechaEntrada
        date FechaSalida
        float Peso
    }

    Vacuna {
        int Id_Vacuna PK
        string Nombre
        date FechaCaducidad
    }

    Voluntario {
        int Id_Voluntario PK
        string Nombre
        string Email
        string Telefono
        string Direccion
    }

    Adopcion {
        int id_Adopcion PK
        int Id_Animal FK
        int Id_Adoptante FK
        date Fecha
        string Observaciones

    }

    Colaboracion {
        int Id_Colaboracion PK
        int Id_Voluntario FK
        date Fecha
    }

    Adoptante {
        int id_Adoptante PK
        string Nombre
        string Direccion
        string Telefono
    }
%%Tablas intermedias para la N a M    
    Colaboracion_Animal {
        int id_Colab_Animal PK
        int Id_Colaboracion FK
        int Id_Animal FK
    }
    Animales_Vacunas {
        int Id_Animal_Vacuna PK
        int Id_Animal FK
        int Id_Vacuna FK
    }

%% Relaciones
    Centro ||--o{ Recinto : ""
    Recinto ||--o{ Animal : ""

    Voluntario ||--o{ Colaboracion : ""
    Animal ||--o{ Colaboracion_Animal : ""
    Colaboracion ||--o{ Colaboracion_Animal : ""

    Adoptante ||--o{ Adopcion : ""
    Adopcion ||--|| Animal : ""
    Animal ||--o{ Animales_Vacunas : ""
    Vacuna ||--o{ Animales_Vacunas : ""
    
```

</details>

# DDBB Empresas de Construcción:

Dibujar el modelo entidad-relación de la base de datos de unas empresas de construcción con las siguientes entidades:

- `Empresa`: tienen un id (CIF), un nombre y una dirección fiscal.
- `Edificación`: tienen un id (NumCatrastro), un número de plantas, una superficie y una fecha de licitación.
- `Aparejador`: tiene un id (NumTecnico), una edad, un nombre, una dirección, un correo y un salario.
- `Obrero`: tiene un id, un DNI, un nombre, una edad y un salario
- `Arquitecto`: tiene un id (NumColegiado), una edad, un nombre, dirección, correo y un salario
- `Capataz`: tiene un id, un DNI, un nombre, una edad y un salario.
- `Plantilla`: tiene un Id y un nombre

Además sabemos que:

Una empresa puede trabajar en varias edificaciones, a su vez en una edificación pueden trabajar varias empresas.

Una edificación tiene asignado un arquitecto y un aparejador, los arquitectos y aparejadores pueden tener asignadas
varias edificaciones.

Los obreros pertenecen a una única plantilla, esta plantilla está formada por varios obreros y un capataz.El capataz
puede dirigir varias plantillas.

En una edificación pueden trabajar varias plantillas, a su vez una plantilla puede trabajar en varias edificaciones.


<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
%% Entidades
    Empresa {
        string CIF PK
        string Nombre
        string DireccionFiscal
    }

    Edificacion {
        int NumCatrastro PK
        int Id_Arquitecto FK
        int Id_Aparejador FK
        int NumeroPlantas
        float Superficie
        date FechaLicitacion
    }

    Aparejador {
        int NumTecnico PK
        int Edad
        string Nombre
        string Direccion
        string Correo
        float Salario
    }

    Obrero {
        int id PK
        string DNI
        string Nombre
        int Edad
        float Salario
    }

    Arquitecto {
        int NumColegiado PK
        int Edad
        string Nombre
        string Direccion
        string Correo
        float Salario
    }

    Capataz {
        int Id_Capataz PK
        string DNI
        string Nombre
        int Edad
        float Salario
    }

    Plantilla {
        int Id_Plantilla PK
        int Id_Capataz FK
        string Nombre
    }

    Plantilla_Edificacion {
        int id_Plantilla_Edif PK
        int Id_Plantilla FK
        int Id_Edificacion FK
    }
    Empresa_Edificacion {
        int id PK
        int Id_Empresa FK
        int Id_Edificacion FK
    }

%% Relaciones
    Empresa ||--o{ Empresa_Edificacion: ""
    Edificacion ||--o{ Empresa_Edificacion: ""

    Edificacion }o--|| Arquitecto: ""
    Edificacion }o--|| Aparejador : ""

    Edificacion ||--o{ Plantilla_Edificacion : ""
    Plantilla ||--o{ Plantilla_Edificacion : ""

    Plantilla }|--|| Capataz : ""
    Plantilla ||--o{ Obrero : ""

```

</details>

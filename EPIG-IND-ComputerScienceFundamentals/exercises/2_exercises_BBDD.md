# DDBB Ordenadores

Dibujar el modelo entidad-relación de la base de datos ordenadores con las siguientes entidades:

- Ordenadores (PCs): tienen un identificador y un precio
- Procesador (CPU) tiene un identificador y una descripción.
- Disco: tiene un ID, una descripción y una capacidad
- Tarjeta Gráfica: tiene un ID, una capacidad y una descripción
- Memoria: tiene un ID, una capacidad y una velocidad
- Fabricante: tiene un ID, una dirección, un teléfono y un CIF
- Tipo de procesador: tiene un ID, una descripción y un tipo de litografía.
- Tipo de memoria: tiene un ID y una descripción

Además sabemos que:

Todos los componentes (procesadores, tarjetas gráficas, memoria y discos) tienen un fabricante que puede ser compartido
por todos ellos.

Los procesadores tienen un tipo de procesador asociado, este puede ser compartido por varios de ellos.

Tanto tarjetas gráficas como memorias van asociados a un tipo de memoria que puede ser común a todas ellas.

Los ordenadores tienen un componente de cada tipo (procesadores, tarjetas gráficas, memoria y discos), estos componentes
pueden ser compartidos por todos ellos

<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
    pcs {
        VARCHAR(20) pcid
        VARCHAR(20) cpu
        VARCHAR(20) disco
        VARCHAR(20) tgrafica
        VARCHAR(20) memoria
        DECIMAL(10) precio
    }

    cpu {
        VARCHAR(20) id_cpu
        VARCHAR(100) descripcion
        VARCHAR(20) id_fabricante
        VARCHAR(20) id_tipo_procesador
    }

    tipo_procesador {
        VARCHAR(20) id_tipo_procesador
        VARCHAR(100) descripcion
        INTEGER t_litografia
    }

    disco {
        VARCHAR(20) id_disco
        VARCHAR(100) descripcion
        INTEGER capacidad
        VARCHAR(20) id_fabricante
    }

    memoria {
        VARCHAR(20) id_memoria
        VARCHAR(20) id_tipo_memoria
        VARCHAR(20) id_fabricante
        INTEGER capacidad
        INTEGER velocidad
    }

    fabricante {
        VARCHAR(20) id_fabricante
        VARCHAR(80) direccion
        VARCHAR(15) telf
        VARCHAR(9) CIF
    }

    tgrafica {
        VARCHAR(20) id_tarjeta_grafica
        VARCHAR(20) id_tipo_memoria
        VARCHAR(20) id_fabricante
        INTEGER capacidad
        VARCHAR(100) descripcion
    }

    tipo_memoria {
        VARCHAR(20) id_tipo_memoria
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

- Hospital: con un ID, un nombre, dirección y teléfono
- Sala: con un ID, un nombre, y un número de camas.
- Estancias: con un ID, una fecha de entrada y salida
- Doctores: con un ID y un nombre
- Plantilla: con un ID, un nombre, una función, turno y salario.
- Especialidades: con su ID y su nombre
- Enfermedades: con un ID y su nombre
- Pacientes: con su ID, nombre, dirección, fecha de nacimiento, sexo y número de la seguridad social.

Además sabemos que:

Un paciente puede realizar una o varias estancias, asociadas a una misma o diferentes enfermedades.

Las estancias pueden realizarse en una misma o diferentes salas. Estas salas pertenecen a un hospital, el cual puede
tener varias de estas.

Una sala tiene asociada una plantilla, compuesta por uno o varios empleados.

El hospital tiene uno o varios doctores, pertenecientes a una especialidad

<details>
  <summary>SEE SOLUTION</summary>

```mermaid
erDiagram
    hospital {
        VARCHAR(5) IdHos
        VARCHAR(20) nomhos
        VARCHAR(30) direc
        VARCHAR(20) telf
    }

    pacientes {
        VARCHAR(8) IdPac
        VARCHAR(20) NomPac
        VARCHAR(20) Direc
        DATE FechaNac
        VARCHAR(1) S
        VARCHAR(12) NSS
    }

    enfermedades {
        VARCHAR(5) IdEnf
        VARCHAR(20) nomenf
    }

    estancias {
        INTEGER IdEstan
        VARCHAR(8) IdPac
        DATE fechaent
        DATE fechasal
        VARCHAR(5) IdHos
        INTEGER CodSala
        VARCHAR(5) IdEnf
    }

    sala {
        VARCHAR(5) IdHos
        INTEGER CodSala
        VARCHAR(25) nomsala
        INTEGER numcamas
    }

    doctor {
        VARCHAR(8) IdDoc
        VARCHAR(5) IdHos
        VARCHAR(25) nomdoc
        VARCHAR(5) IdEsp
    }

    plantilla {
        VARCHAR(8) IdEmp
        VARCHAR(5) IdHos
        INTEGER CodSala
        VARCHAR(25) nomemp
        VARCHAR(25) funcion
        VARCHAR(1) turno
        FLOAT salarioanual
    }

    especialidades {
        DomNumPositivo IdEsp
        VARCHAR(15) nomespecialidad
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

# DDBB Pedidos (DRAFT)

Dibujar el modelo entidad relación de la base de datos pedidos online con las siguientes entidades:

- Productos: con su id, nombre, precio, estado y fecha de creación.
- Etiquetas de producto: Con su id y nombre.
- Pedidos: con su id, estado y fecha de creación.
- País: con su id (código), nombre y nombre del continente al que pertenece.
- Tienda: con su id, nombre, fecha de creación y su administrador.
- Usuarios: con su id, nombre completo y fecha de registro.
- Temporada: con su id, fecha de inicio y fecha de fin.

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
        INTEGER id_producto
        VARCHAR(25) nombre
        INTEGER IDVendedor
        INTEGER precio
        VARCHAR(1) estado
        DATE fechacreacion
    }

    etiquetas_producto {
        INTEGER id_producto
        VARCHAR(5) id_etiqueta
    }

    etiquetas {
        VARCHAR(5) id_etiqueta
        VARCHAR(25) nombre
    }

    items_pedido {
        INTEGER IDPedido
        INTEGER IDProducto
        INTEGER cantidad
    }

    pedidos {
        INTEGER id
        INTEGER IDUsuario
        VARCHAR(1) estado
        DATE fechacreacion
    }

    pais {
        VARCHAR(4) codigo
        VARCHAR(25) nombre
        VARCHAR(25) nombreContinente
    }

    tienda {
        INTEGER id
        VARCHAR(4) codigo_pais
        VARCHAR(25) nombre
        DATE fechacreacion
        INTEGER Id_Admin
    }

    Usuarios {
        INTEGER id
        VARCHAR(25) nombrecompleto
        DATE fechacreacion
        VARCHAR(4) codigo_pais
    }

    Temporada {
        INTEGER id
        INTEGER IDVendedor
        VARCHAR(4) codigo_pais
        DATE fechainicio
        DATE fechafin
    }

%% Relaciones
    productos ||--o{ etiquetas_producto: ""
    etiquetas ||--o{ etiquetas_producto: ""
    pedidos ||--o{ items_pedido: ""
    productos ||--o{ items_pedido: ""
    pedidos ||--o{ Usuarios: ""
    tienda ||--o{ pais: ""
    Usuarios ||--o{ pais: ""
    tienda ||--o{ Temporada: ""
    Temporada ||--o{ productos: ""

```

</details>

# DDBB MarketPlace (DRAFT)

Dibujar el modelo entidad-relación de la base de datos:

- Autores: tiene un identificador, nombre, país y URL
- Libro: tiene un identificador (ISBN), un año de publicación, un título y un precio
- Editorial: tiene un identificador, un nombre, dirección, teléfono y URL
- Vendedor online: tiene un identificador, un email y una URL
- Cesta de la compra: tiene un identificador y un número de referencia
- Comprador: tiene un identificador, un nombre, dirección, email y número de tarjeta de crédito
- Un pedido: tiene un identificador, fecha y dirección

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
        INTEGER id_autor
        VARCHAR(25) nombre
        VARCHAR(25) pais
        VARCHAR(35) URL
    }

    Autoria {
        INTEGER id_autoria
        INTEGER ISBN
        INTEGER id_autor
    }

    Libro {
        INTEGER ISBN
        INTEGER anio_publicacion
        VARCHAR(25) titulo
        FLOAT precio
    }

    Editorial {
        INTEGER id_editorial
        VARCHAR(25) nombre
        VARCHAR(35) direccion
        VARCHAR(9) telefono
        VARCHAR(35) URL
    }

    VendedorOnline {
        INTEGER id_vendedor
        VARCHAR(25) email
        VARCHAR(35) URL
    }

    CestaCompra {
        INTEGER id_cesta
        INTEGER ISBN
        INTEGER id_comprador
        INTEGER cantidad
    }

    Comprador {
        INTEGER id_comprador
        VARCHAR(25) nombre
        VARCHAR(35) direccion
        VARCHAR(25) email
        VARCHAR(25) num_tarjeta_credito
    }

    Pedido {
        INTEGER id_pedido
        DATE fecha
        VARCHAR(35) direccion_envio
    }

%% Relaciones
    Autor ||--o{ Autoria: ""
    Libro ||--o{ Autoria: ""
    Libro }o--|| Editorial: ""
    VendedorOnline ||--o{ Libro: ""
    CestaCompra ||--o{ Libro: ""
    Comprador ||--o{ CestaCompra: ""
    Comprador ||--o{ Pedido: ""
%% Relaciones N:M
    VendedorOnline ||--o{ Libro: ""
    Libro ||--o{ Pedido: ""

```

</details>

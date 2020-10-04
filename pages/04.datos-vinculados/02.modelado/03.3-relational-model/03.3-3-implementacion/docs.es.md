---
title: '3.3 Implementación'
taxonomy:
    category:
        - docs
---

El software construido sobre este modelo, conocido como software de administración de bases de datos relacionales (RDMS), se ha desarrollado ampliamente durante las últimas décadas y actualmente se encuentra en una etapa muy madura. Probablemente todo el mundo haya oído hablar en algún momento de MySQL, el RDMS de código abierto más popular utilizado para aplicaciones web, o M3-SQL, un RDMS propietario desarrollado por Microsoft. Otro fabricante conocido es Oracle. Los sistemas de gestión de colecciones, los inventarios de archivos y los catálogos de bibliotecas se construyen sobre un RDMS.

La mayoría de los sistemas de bases de datos funcionan en una configuración cliente-servidor, donde el servidor ejecuta un RDMS y el cliente interactúa con él mediante declaraciones SOL. Las aplicaciones para consumidores y pequeñas empresas, como Microsoft Access, simplifican la estructura al ofrecer una interfaz gráfica de usuario que funciona directamente sobre un archivo de base de datos local. Para RDMS normal, también existen interfaces gráficas para clientes, pero la comunicación subyacente se realiza en SQL.

Por ejemplo, se puede crear una tabla en MySQL con:
```
CREATE TABLE Work (
   id INT AUTO_INCREMENT PRIMARY KEY,
   title VARCHAR(100),
   creator INT,
   collection INT,
   year CHAR(4),
   Style VARCHAR(40)
);
```
Esto crea una nueva tabla llamada `Work` con una columna de `ID` de número entero `(INT)`, una columna de título textual (`VARCHAR (100)` , que significa una cadena de caracteres con longitud variable, máximo 100) y un número entero de `creator` y las columnas `collection` una columna `year` de 4 caracteres y una columna `estilo` de 4 caracteres. La columna `id` es especial, ya que debería proporcionar un identificador único para cada registro. Por lo tanto, tiene las etiquetas `AUTO_INCREMENT` (por lo que los nuevos números se asignan automáticamente) y `PRIMARY KEY` (para que la base de datos sepa que este es un campo único).

To insert data in this table, we can use:

```
INSERT INTO Work (title, creator, collection, year, style)
   VALUES (‘Guernica’, 43, 20, 1937, ‘Cubism’);
```
We supply the table name, followed by the names of the fields and then the values for these fields. Strings are surrounded by single quotes (and single quotes within strings are escaped by a backslash}. Note how we did not supply a value for the id field, as this value is automatically generated (and will default to 1, 2, 3, ... on an empty table).

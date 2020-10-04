---
title: '3.3 Implementación'
taxonomy:
    category:
        - docs
---

Software built on top of this model, referred to as relational database management software (RDMS), has been extensively developed over the last decades and is currently at a very mature stage. Everyone has probably heard at some point about MySQL, the most popular open-source RDMS used for web applications, or M3-SQL, a proprietary RDMS developed by Microsoft. Another well known manufacturer is Oracle. Collection management systems, archival inventories and library catalogues are all built on top of a RDMS.

El software construido sobre este modelo, conocido como software de administración de bases de datos relacionales (RDMS), se ha desarrollado ampliamente durante las últimas décadas y actualmente se encuentra en una etapa muy madura. Probablemente todo el mundo haya oído hablar en algún momento de MySQL, el RDMS de código abierto más popular utilizado para aplicaciones web, o M3-SQL, un RDMS propietario desarrollado por Microsoft. Otro fabricante conocido es Oracle. Los sistemas de gestión de colecciones, los inventarios de archivos y los catálogos de bibliotecas se construyen sobre un RDMS.

La mayoría de los sistemas de bases de datos funcionan en una configuración cliente-servidor, donde el servidor ejecuta un RDMS y el cliente interactúa con él mediante declaraciones SOL. Las aplicaciones para consumidores y pequeñas empresas, como Microsoft Access, simplifican la estructura al ofrecer una interfaz gráfica de usuario que funciona directamente sobre un archivo de base de datos local. Para RDMS normal, también existen interfaces gráficas para clientes, pero la comunicación subyacente se realiza en SQL.

Por ejemplo, se puede crear una tabla en MySQL con:

```
CREATE TABLE Work (
   id INT AUTO_INCREMENT PRIMARY KEY,
   title VARCHAR( 100),
   creator INT,
   collection INT,
   year CHAR(4),
   Style VARCHAR(40)
);
```
This makes a new table called Work with an integer id column `(INT)`, a textual `title column (VARCHAR(100)`, meaning a string of characters with variable length, maximum 100), and integer creator and collection columns a 4-character year column, and a 40-character style column. The id column is special, since it should provide a unique identifier for each record. Therefore, it has the labels `AUTO_INCREMENT` (so new numbers are assigned automatically) and `PRIMARY KEY` (so the database knows that this is a unique field).

To insert data in this table, we can use:
```
INSERT INTO Work (title, creator, collection, year, style)
   VALUES (‘Guernica’, 43, 20, 1937, ‘Cubism’);
```
We supply the table name, followed by the names of the fields and then the values
for these fields. Strings are surrounded by single quotes (and single quotes within
strings are escaped by a backslash}. Note how we did not supply a value for the
id field, as this value is automatically generated (and will default to 1, 2, 3, .-. 1
an empty table).

3.4 Search and retrieval

After several records have been inserted, we can retrieve them with SELECT
queries. For instance:

SELECT * FROM Work;

will select all records in the Work table. If we only want the titles of works by
Picasso (assuming he has identifier 43 in the Creator table), we can do:

SELECT title FROM Work WHERE creator=43:

This is only a basic introduction to SQL, as end-users are only confronted with
predefined SQL queries accessible through a graphical interface of a collection
management system. However, it is important to understand through the
example the logic behind the SQL query language. Section 5 will build further
on this example to illustrate how the SPAROL query language works.
---
title: '3.5 Cambio'
taxonomy:
    category:
        - docs
---

La sección anterior sobre el formato tabular describió el poco impacto que tiene el cambio en la estructura de un archivo plano. Agregar nuevas columnas o eliminar las existentes no altera fundamentalmente cómo se pueden usar los datos tabulares. La situación no podría ser más diferente con las bases de datos relacionales. Agregar una tabla adicional requiere que el administrador de la base de datos reconsidere todo el esquema de la base de datos, ya que agregar una tabla adicional podría implicar una degradación del proceso de normalización.

Let us come back to our example. Imagine we want to add an entity
`Archivelltem` which describes the archival holdings of an artist that the institution
possesses, such as correspondence, notes, personal photographs, historical press
clippings, etc. 

How do we update our database with minimal effort? We can
create a table `Archivalltem` with the attributes `ID`, `document type`, `year`, `creator`,
and `collection`. Then the change can happen by just adding this single table.
However, that table would carry a considerable overlap with `Work`, as both have
a creator, collection, and year. This information spread becomes difficult to
manage in the end. If we want to respect the normalization requirements, we
cannot just add extra tables, but we also need to modify the existing tables.
Figure 2.3 shows a better integrated solution: the common attributes of `Work`
and `Archivailtem` are placed into a separate `Asset` table. 

TABLE 
Figure 2.3 To support archival items in a consistent way, the creator, collection, and year
fields must move from the Work table into a shared Asset table


However, this means
that the existing table and data structure has to be modified.
Apart from ensuring the normalization of the new database schema, the
modifications also impact external systems, such as the public front-end built to
give access to the data on the web. Performing these types of updates and
modifications every couple of months can be very cumbersome. In practice, these
modifications are often avoided, as there is no time to fundamentally rethink the
structure of the database. In this context, people often rely on lightweight and
ad hoc solutions, such as creating a standalone spreadsheet. This type of short-term
decision causes, over a period of years, tremendous issues with data
Onsistency, as reference data are scattered across different applications. We can
therefore conclude that it is not a trivial matter to update and maintain a database,
due to the complexity of modifying the database schema.
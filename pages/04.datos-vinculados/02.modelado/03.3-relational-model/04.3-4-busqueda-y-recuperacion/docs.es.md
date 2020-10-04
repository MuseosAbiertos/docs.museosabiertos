---
title: '3.4 Búsqueda y recuperación'
taxonomy:
    category:
        - docs
---

After several records have been inserted, we can retrieve them with SELECT
queries. For instance:
```
SELECT * FROM Work;
```
will select all records in the Work table. If we only want the titles of works by
Picasso (assuming he has identifier 43 in the Creator table), we can do:
```
SELECT title FROM Work WHERE creator=43:
```
This is only a basic introduction to SQL, as end-users are only confronted with
predefined SQL queries accessible through a graphical interface of a collection
management system. However, it is important to understand through the
example the logic behind the SQL query language. Section 5 will build further
on this example to illustrate how the SPARQL query language works.
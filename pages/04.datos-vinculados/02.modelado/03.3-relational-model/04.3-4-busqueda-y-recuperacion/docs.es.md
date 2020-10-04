---
title: '3.4 Búsqueda y recuperación'
taxonomy:
    category:
        - docs
---

Después de que se hayan insertado varios registros, podemos recuperarlos con consultas `SELECT`. Por ejemplo:

```
SELECT * FROM Work;
```
seleccionará todos los registros en la tabla de trabajo. Si solo queremos los títulos de las obras de Picasso (suponiendo que tenga el identificador 43 en la tabla `Creator`), podemos hacer:

```
SELECT title FROM Work WHERE creator=43:
```
Esta es solo una introducción básica a SQL, ya que los usuarios finales solo se enfrentan a consultas SQL predefinidas accesibles a través de una interfaz gráfica de un sistema de gestión de colecciones. Sin embargo, es importante comprender a través del ejemplo la lógica detrás del lenguaje de consulta SQL. 

La sección 5 se basará más en este ejemplo para ilustrar cómo funciona el lenguaje de consulta SPARQL.
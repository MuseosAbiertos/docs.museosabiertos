---
title: '2.3 Búsqueda y recuperación'
taxonomy:
    category:
        - docs
---

¿Cuáles son las implicaciones de este modelo de datos para la búsqueda y recuperación de metadatos?

Un vistazo rápido a los metadatos en la Tabla 2.2 brinda una descripción general de las limitaciones del enfoque de archivo tabular. Por ejemplo, el nombre del creador se expresa de diferentes maneras ('Pablo Picasso' y 'Picasso'), ya que codificamos la misma realidad cada vez que describimos un nuevo objeto que hizo este artista. Para un ser humano, es sencillo asignar estas dos representaciones diferentes a la misma realidad. Probablemente también haya notado la presencia de "Koons, Jeff", en el que las comillas se utilizan para proteger la coma que separa la familia y el nombre.

Al realizar una búsqueda de texto completo en una cadena de caracteres, un algoritmo tendrá más problemas para ofrecer buenos resultados de búsqueda. Por lo tanto, supongamos que desea actualizar sus metadatos y codificar el nombre del creador de manera uniforme. Ahora imagina que no tienes tres registros (como es el caso en nuestro ejemplo} sino un par de cientos de miles... 

Administrar tus metadatos en una lista tabular implicaría que necesitarías revisar todos estos registros para ver dónde aparece una de las diferentes grafías del nombre del creador y actualizarla si es necesario a la grafía preferida. Este método de trabajo está destinado a introducir inconsistencias en sus metadatos. A nivel computacional, la búsqueda y recuperación es muy ineficaz con este enfoque, ya que nuevamente la totalidad de sus registros de metadatos deben verificarse para ver si contienen un valor específico. Los archivos tabulares tampoco ofrecen las herramientas adecuadas para imponer reglas sobre cómo codificamos los valores, lo que resulta en inconsistencias en la forma en que codificamos los metadatos.

Los problemas solo empeoran cuando empieza a pensar en buscar en varios archivos en este formato. Otra institución podría tener sus propios datos tabulares que contienen información relevante para usted, pero ¿cómo podría realizar una consulta en archivos planos independientes de manera coherente? Los usuarios competentes de Microsoft Excel pueden hacer uso de macros y tablas de búsqueda para crear vínculos entre varios archivos independientes, pero estas funcionalidades no se pueden utilizar fuera de Excel. Esto implica que ya no tiene un formato independiente de la plataforma y la aplicación.

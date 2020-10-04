---
title: '3.2 Metodología de diseño'
taxonomy:
    category:
        - docs
---

Building a relational model is a difficult task that requires a lot of experience.
Nonetheless, there are some guiding principles that you can use:

* The first task is to discover the entity types that the database will contain, Typically, entities correspond to independent concepts in the world of which there will be many, and each one has properties of its own.
In our example, it is certain that ‘Work’ will be an entity type, as the database will contain several works. It is also likely that ‘Creator’ will be an entity type, as it is independent from Work and there will be many of them. However, an entity type of ‘Country’ will probably not be necessary, as we will only need the country’s name and no other properties. However, for
other use cases, it might be meaningful to encode ‘Country’ as an entity type.

* For every entity type, a table will be created in the database. Each row in the table will have a unique identifier, often a  numeric value that is automatically generated. Each property of the entity will be a column in the table, and each column can have a value type. Our ‘Work’ table might have a textual field for the title and a date field for the creation date (or a four-
digit field if we only plan to store the year). 

* Next, one-to-many relationships must be modelled. They provide a mechanism for a record in a table to link to one record in another table, and the record in the second table can receive several such incoming links. As each entity has a unique identifier, we can add a column to the first table that will contain this identifier. That way, the objects in the first table can
Point to an item in the second table. For instance, the “Work’ table should contain a ‘Creator’ column that stores the identifier of the creator. That way, each work can be associated with one creator, and each creator can then be associated with several works.

* Finally, many-to-many relationships should be described. As fields in databases are traditionally not multi-valued, we must find another way for a record in a table to point to several records in another table. This is done by having a third relationship table, which has one column for identifiers of the first table and one column for identifiers of the second table. That way, we
can find all items that belong together by traversing the rows of this table. Additional columns might describe properties of the relationship. In case works are authored by many creators, we could opt to represent them as a many-to-many relationship. Then, we would have a third table called ‘Creatorship’ with columns ‘work’ and ‘creator’ that store the respective identifiers. We might add a textual column ‘role’ describing how the person was involved in the creation of the work.


The above points are merely guidelines. In practice, there are many possible motivations behind the choice for a certain design decision. There will always be trade-offs between optimal modelling flexibility, performance and simplicity.
This is well illustrated by the option of whether to allow multiple creators for a work, This might allow you to describe the reality more closely, at the expense of a more complex (and possibly slower) data model.

Let us come back to our example. In order to have a sufficiently complex scheme, extra attributes, such as style, were added, as in Figure 2.2. 
It should be clear that there is no such thing as one unique and perfectly adequate model, as the same reality can be interpreted in multiple ways.


TABLA 
 
- Creator __a
_| first name surname birth year | death year
Pablo Picasso 1881 | +973
Jett Koons 1955 null
| Work :
ID | title OS | creator | collection year | style
5 | Guernica 143) - 20 1937 | cubism
? First Communion 43 (22) 1595 realism
16 Puppy Sf /18 | 1992 conceptual
| Collection
ID/ | _ name address
18 Guagenheim Bilbac
20 | Museo Reina Sofia | Madrid
(22) Museo Picasso Barcelona

Figure 2.2 An example entity relation model with the relationships highlighted


Depending on the importance you give to an aspect of the reality you are modelling, you either decide to consider it as an entity or as an attribute. Despite the simplicity of the scheme in Figure 2.2, many readers of this book probably would come up with different versions of the scheme. For example, one could decide to reduce the entity Collection to an attribute of the entity Work, if you do not consider the address as an independent aspect that needs to be documented. The process of placing separate entities in separate tables is called normalization. Unfortunately, the more tables that need to be accessed to
reconstruct the related metadata of an item, the slower operations will become. Therefore, a meaningful balance should be found between what data will be stored in a single table and what data is stored as a relationship.

The added complexity on the modelling level is made up for by the advantages offered by having a single record for an entity, that can be referred to with a unique ID. For example, every time you need to refer to the fact that an object is housed in a specific collection, you do not have to re-encode the metadata in relation to the address of where the collection is managed and other attributes of the entity Collection. You simply refer to the ID of the collection, and the same applies to other entities such as Creator. This approach ensures a lot more consistency. Those IDs are typically indexed to ensure the corresponding rows can be fetched in a fast way without traversing the entire table.

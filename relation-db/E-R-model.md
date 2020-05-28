### What is E-R data model

E-R data model is abbreviated from entity-relationship data model used to database design. It is a model to descripe the real world objects and relationships of objects. 

E-R data model usually used to relational database desing.

### Definition

#### What is entity and entity set? 

Entity refers to particular objects or indivuduals.  While entity set is a collection of individuals.

Entity set usually refers to a collections of objects of the same type.

The first thing for design of E-R model is to find all the entities.

#### What is relationship and relationship set.

Relations descripes the relationships among entities. Relation refers to a particular relationship of two or more entities. While relation set refers to a collection of relations of the same type.

I think finding the relations of entities is the key to database design. Usually entities are related, we can use relationships to descripe this kind of relations. 

Relation set can be defined by the mathmactical formula. The definition is nothing more than set and tuple.  

{<e1, e2, e3, ... en> | e1 is in E1, e2 is in E2 ... en is in En, where E1, E2, ... En is entity set}

### Cardinalities.
Cardinalities used to define how many kinds of  relationships.

- one to one
- one to many
- many to one
- many to many.


### E-R model and relational database schema.

Entity can be translated to table in relational database. While relationship can be translated in to relational database by primary key and foreign key.  But primary key and foreign key can only express the one to one , one to many or many to one relationships. It can't express many to many relationship well, so we can add a intermediate table to express the many to many relationship

But E-R model can't express attribute type, and some constraints. 







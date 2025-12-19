***
#### Conceptual Design
**External Level (view)**: Describes different parts of the database to different users
**Conceptual Level (logical):** How data is perceived by the users

**IsA**
Partial: Some superclass entity may not be in any class
Total: A superclass entity must belong to some class
Disjoint: A superclass entity belongs to no more than a single class
Overlapping: Classes may overlap (can be both)

**Weak Entity**
Must have total participation in this identifying relationship

**Aggregation**
Allows us to treat a relationship set as an entity set for purposes of participation in other relationships

#### Relational Model
**Physical Data Independence**: Ability to modify physical schema without changing logical schema
**Logical Data Independence**: Ability to change the conceptual schema without changing applications
**Schema**: Specifies name of relation plus name and domain of each attribute
**Instance**: A table with rows and columns
**Cardinality**: Number of rows in a table
**Degree**: Number of columns (attributes)
**Integrity Constraint**: Condition that must be true for any instance of the database

**Destroying and Altering Relations**
Drop Table
* Destroys the relation. Schema information and tuples are deleted
Alter Table
* The schema is altered by adding a new attribute

**Referencial Integrity**
No action
* Delete/update is rejected
Cascade
* Also updates/deletes all tuples that refer to the updated/deleted tuple
Set null / set default
* Referencing tuple value is set to the default foreign key value
***
**Cardinality Ratio**: Specifies the number of relationships in the set that an entity can participate in

**One to one**
* An entity in A is associated with at most one entity in B and vice versa
**One to many**
* An entity in A is associated with any number of entities in B
**Many to one**
* An entity in B is associated with any number of entities in A
**Many to many**
* An entity in A is associated with any number of entities in B and vice versa

`Overlap Constraints`:
* **Disjoint**: a superclass entity belongs to no more than a single class
* **Overlapping**: Classes may overlap

`Covering Constraints`:
* **Total**: A superclass entity must belong to some class
* **Partial**: Some superclass entity may not be in any class

`Weak Entities`:
* Can be defined uniquely only by additionally considering the key of another owner

#### SQL Constraints
***
**Integrity Constraint**: Conditions/rules that must be true for any instance of the database
* 
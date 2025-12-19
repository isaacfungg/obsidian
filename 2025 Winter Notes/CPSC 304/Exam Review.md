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

#### Normal Forms
**Normalization**: The process of removing redundancy from data

**1NF**
* Each attribute in a tuple has only one value
**2NF**
* No partial key dependency
* For every X->Y where X is a minimal key and Y is a non-key attribute, then no proper subset of X determines Y
**BCNF**
* LHS has to be a superkey

###### Deriving Additional FDs:
**Closure of F (F⁺):** all functional dependencies you can **derive or infer** from the given ones using the basic rules (reflexivity, augmentation, transitivity).
- **Reflexivity:**  
    If a set of attributes includes another set, it functionally determines it.  
    → If `Y ⊆ X`, then `X → Y`.  
    **Example:** `{A, B} → A` (because A is part of {A, B}).
- **Augmentation:**  
    You can add the same attributes to both sides of a dependency.  
    → If `X → Y`, then `XZ → YZ`.  
    **Example:** `A → B` ⇒ `AC → BC`.
- **Transitivity:**  
    You can link dependencies through a shared attribute.  
    → If `X → Y` and `Y → Z`, then `X → Z`.  
    **Example:** `A → B` and `B → C` ⇒ `A → C`.
**Union:**  
If two FDs have the same left side, you can combine their right sides.  
→ If `X → Y` and `X → Z`, then `X → YZ`.  
**Example:** `A → B` and `A → C` ⇒ `A → BC`.

**Decomposition:**  
If an FD has multiple attributes on the right, you can split it.  
→ If `X → YZ`, then `X → Y` and `X → Z`.  
**Example:** `A → BC` ⇒ `A → B` and `A → C`.

#### Data Warehousing

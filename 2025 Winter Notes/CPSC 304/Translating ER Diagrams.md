***
#### Translating Participation Constraints
**One to many**
We can capture participation constraints by using a NOT NULL

**Many to Many**
If we have many to many `MoviePeople` *worksOn* `Movie` with NOT NULL, *workOn* may contain only valid values but it does not ensure EVERY `MoviePeople` *worksOn* `Movie` and EVERY `Movie` has some `MoviePeople`

**One to One**
With one to one we can use the NOT NULL paired with the UNIQUE.

#### Translating Weak Entity Sets
* A weak entity set has total participation.
* Weak entity set and its identifying relationship set are translated into a single table (like many to one)
* When the owner entity is deleted, all owned weak entities must also be deleted
* The foreign key is implicitly NOT NULL so we do not need to specify that it is not null

#### Translating ISA Hierarchies
* Superclass table contains all superclass attributes
* Subclass table contains primary key of superclass and the subclass attributes
* 

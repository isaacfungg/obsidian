**User Stories**
* Role - goal - benefit
* Definition of done: How the story can be validated by both the developer and the owner
* Engineering notes: Often used to capture key interactions of the feature with other parts of the system
* Effort estimate: Fibonacci sequence is often used when assigning a point value

**INVEST**
* Independent
	* Stories need to be independent
* Negotiable
	* Open to discussion
* Valuable
	* Value to the user or customer
* Estimatable
	* Small and clear enough to estimate effort
* Small
	* Can be completed in one sprint
* Testable
	* Has clear acceptance criteria

#### Black Box Testing
**Boundary Value Analysis**
* Includes inputs inside and outside the boundary
**Equivalence Class Partitioning**
* Technique that splits inputs or outputs into valid and invalid classes.
**Input Partitioning**
* Group input ranges that should produce the same output.
**Output Partitioning**
* Group outputs that represent the same behavior or result.
#### Static Analysis
**Static analyses**: Only inputs the program text itself and does not need to execute
* Formatting + Linting
**Dynamic analyses**? Needs to run the program
**Syntax**: Defines the set of valid tokens
**Semantics**: Define what the tokens actually mean

#### Process
**Scrum**: An Agile framework that organizes work into fixed-length sprints with defined roles and ceremonies to deliver small, regular product increments.
**Kanban:** An Agile method that manages work through a continuous flow using a visual board, focusing on limiting work in progress and improving delivery speed.
* More rapid releases than scrum
* Keeps daily standup but no sprint planning or sprint reviews

**Risks**
* User
* Requirements
* Project Complexity
* Planning & Control
* Team
* Organizational Environment

#### Agile Principles
Code must be able to do these three things:
* Its job
* Afford Change
* Be understandable

#### Specifications
**Functional Requirements**: Describe what the system must do
**Non-functional Requirements**: Describe properties the system must have
#### Code Smells
**Law of Demeter**: Too many dereferences mean the method is probably in the wrong spot
**Feature Envy**: A class uses too many details from another class
**Experiential Symptom**: Problem that is recognizes through repeated maintenance
**Divergent Changes**: One class keeps changing for unrelated reasons
**Shotgun Surgery**: One change forces edits to many classes

#### Design Principles
**Coupling**: How strongly connected different programs are to each other
* Strong coupling is problematic because it affects evolvability and maintainability
**Cohesion**: How well elements belong to each other in a class
**Decomposition**: Breaking down complex description into more manageable pieces
**Abstraction**: Hiding unimportant details
**Encapsulation**: Bundling data and behaviour together

#### API
**Semantic Versioning**: Versions public APIs using MAJOR.MINOR.PATCH format
**Idempotency**: Performing a VERB multiple times has the same result for the server resources as performing it once

#### Security
**Stride**
* Spoofing: Pretend to be someone else
* Tampering: Modifying data
* Repudiation: Denying performing a tasks
* Information Disclosure: Access private information
* Denial of Service: Halt service
* Elevation of Privilege
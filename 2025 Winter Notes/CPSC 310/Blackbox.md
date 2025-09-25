***
**Equivalence classes** are the groups of inputs that are treated the same by the program because they should produce similar behavior or output.
Example: For an input field that only accepts ages **1–100**:

- One equivalence class = valid ages (1–100)
- Another = invalid ages (<1)
- Another = invalid ages (>100)

**Boundary Value Analysis (BVA)** is a testing technique focused on inputs at the edges (boundaries) of valid and invalid ranges, since bugs often occur there.
Example: if valid age = **1–100** → test `0, 1, 2, 99, 100, 101`.

**State Transition Testing** checks how a system behaves when moving between different states based on inputs or events.
- A **state** = condition of the system at a point in time.
- A **transition** = movement from one state to another triggered by an event.
    
Example: A login system:
- State: “logged out” → input correct password → transition → “logged in.”
- Invalid input may keep you in “logged out” or lock the account.

**User Acceptance Testing (UAT)** is the final testing phase where real users (or clients) verify that the software meets their needs and requirements.

`Static Analyses`: Any programmatic analysis of a program that only inputs the program text itself and does not need to execute the program
* Formatting: Enforcing consistent code syntax
* Linting: Enforcing consistent code syntax & enforcing good semantics of code
`Dynamic Analyses`: Needs to run the program, so also require inputs
`Syntax`: Defines the set of valid tokens that are allowed
`Semantics`: Define what the tokens actually mean

###### Kinds of Tests
**Smoke
* Quick check that the app starts and main features work
* Fast test to catch major issues
**Regression
* 
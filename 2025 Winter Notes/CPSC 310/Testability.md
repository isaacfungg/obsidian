***
##### Assertions
**Four-phase test**
* Focuses on test structure
* Structured approach to writing unit test that has four parts:
	* Setup: Prepare the environment for tests
	* Exercise: Run the code or function being tested
	* Verify: Check that the output matches expectation
	* Teardown: Clean up the resources or reset the environment
**Give-When-Then**
* Focuses on behaviour
* Given: Sets up the initial state or context
* When: Performs the main action being tested
* Then: Verifies the expected outcome


**Normal conditions**: The normal conditions represent the way we expect the code to be used.
**Unexpected conditions**: The unexpected conditions arise when the code is used in unexpected ways.
**Boundary conditions**: All programs consume input; by testing boundary values we can ensure our program will successfully operate with the breadth of inputs the program might encounter.
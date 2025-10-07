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


**Testability – Key Notes**
- **Definition:** Quality attribute that determines how easily software can be tested; doesn’t affect functionality but impacts validation effort.
- **Goal:** Enable tests to execute code, trigger defects, and observe incorrect results for verification.
    
**Four Properties of Testability:**
1. **Controllability:**
    - Ability to programmatically control the system/code under test.
    - Improves via dependency injection, additional parameters, or modular design.
    - Example: Decouple logic from UI for easier testing.
2. **Observability:**
    - Ability to observe outcomes and detect defects.
    - Improve by returning data, exposing state, or defining clear expected results.
    - Challenge: unclear or conflicting specifications.
3. **Isolateability:**
    - Ability to pinpoint where a fault occurs.
    - Achieved by decomposing large code, or using **mocks/stubs** to simulate dependencies.
    - Helps improve performance, determinism, and test coverage.
4. **Automatability:**
    - Ability to run tests without human input.
    - Enables continuous integration, regression testing, and reduces manual effort.
    - Provides visibility and confidence in system stability.
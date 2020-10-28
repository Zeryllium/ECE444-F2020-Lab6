# ECE444-F2020-Lab6

This code is adapted from https://github.com/mjhea0/flaskr-tdd

---
### Q3: What are the pros and cons of TDD?

Test-driven development (TDD) is a process where tests are written prior to developing the application code. By this 
process, we can see the benefits and detriments are as follows:

##### Benefits:
- TDD ensures a high degree of test coverage as the code is written to pass the desired functionality specified in 
the tests.
    - Additionally, this helps with updating or refactoring older code as new code can be tested on the old unittests 
    to ensure that the same functionality is preserved.
    - Similarly, developer collaboration and developer onboarding (training new team members) is significantly easier 
    as the tests provide a cohesive safety net that can quickly catch errors.
- Ensures that each unit is properly configured to work with the interfaces it is designed for (I/O contracts).
    - This also shifts more of the developer focus on optimizing and standardizing the interfaces, which makes 
    developing a new unit within the same interfaces much easier.
    - At the same time, this promotes making modular and minimum units; a shared component between multiple units 
     can and should be refactored into its own separate unit such that any error in functionality of the shared code 
     can be fixed in one location (rather than needing to find all copies of that shared code in each unit)  
- Documentation of each unit is significantly easier to write as the details on the functionality, inputs, and outputs 
of the unit are already captured by the unittests.

##### Detriments:
- It is significantly harder to start programming the test code prior to writing any application code as it is 
difficult to judge the exact format or structure of the internal components for each unit.
    - Unittests written in this manner have to treat each unit as a blackbox.
    - "Plumbing code" that primarily deal with routing, communicating, or interfacing with multiple units is hard to 
    test with unittests in this manner. 
        - These tests generally have to be promoted to integration or system tests
- Likewise, maintaining a high degree of TDD is difficult due to the high initial development cost (time) and the 
difficulty in applying TDD retroactively to older code.

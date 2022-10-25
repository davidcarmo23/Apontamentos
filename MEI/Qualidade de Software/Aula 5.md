# Today's Goals
![[Pasted image 20221025184818.png]]

## Unit Testing 
- Testing the smallest "unit" that can be tested
- Tested in **isolation** from all other units
	- **Mock** the results from other classes
- Test input = method calls
- Test oracle = assertions on output/class variables

- For a unit, tests should:
	- Test all "jobs" associated with the unit
	- Set and check value of all class variables
![[Pasted image 20221025185336.png]]

### Advantages
- Increases confidence in changing/maintaining code.
- Codes are more reusable. To make unit testing possible, codes need to be 'modular'
- Are more reliable than developer tests
- Less effort to find and fix defects found during unit testing
- The cost of fixing a defect is lesser
- Debugging is easy

## System Testing
- After testing units, test their **integration**
	- Integrate units in one subsystem
	- Then integrate the subsystems
- Test through a **defined interface**
![[Pasted image 20221025185702.png]]

- Functional tests at the system level are used to ensure that the behaviour of the system adheres to the requirements specification. All functional requirements for the system must be achievable by the system.
- Funcitonal tests are black box in nature. Focus in inputs and the proper outputs.
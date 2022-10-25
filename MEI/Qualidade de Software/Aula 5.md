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
- **Functional tests** are *black box* in nature. Focus in inputs and the proper outputs.
- This is the only phase of testing which test *both* functional and non-functional requirements of the system

## Unit vs System Testing
- Unit tests focus on a **single class**
	- Simple functionality, more freedom
	- Few method calls
- System tests **bring many classes together**
	- Focus on testing through an interface
	- One interface call triggers many internal calls
		- Slower test execution
	- May have complex input and setup

- **Tests can be written early in the project**
	- Requirements discuss high-level functionality
	- Can create tests using requirements
- Creating tests support requirement refinement
- Can be made concrete once code is built


## Interface Types
![[Pasted image 20221025190355.png]]
![[Pasted image 20221025190404.png]]

## Interface Errors
![[Pasted image 20221025190429.png]]

## Testing Percentages
![[Pasted image 20221025190448.png]]

## Testing
![[Pasted image 20221025190507.png]]

## Creating System-Level Tests
![[Pasted image 20221025190525.png]]

### Independently Testable Functionality
- **A well-defined function that can be tested in (relative) isolation**
	- Based on the "verbs" - what can we do with this system?
	- High-level functionality offered by an interface
	- UI - look for user-visible functions


#### Units and "Functionality"
- An independently testable function is a capability of the software
	- Can be at class, subsystem or system level
	- **Defined by an interface**

### Identify Input Choices
- What choices do we make when using a function?
	- **Anything we control that can change the outcome**
- What are the **inputs** to that feature?
- What **configuration choices** can we make?
- Are there **environmental factors** we can vary?

#### Parameter Characteristics
![[Pasted image 20221025191109.png]]

#### Parameter Context
![[Pasted image 20221025191127.png]]

### Identifying Representative Values
- We know the functions
- We have a set of choices
- What values should we try?
	- For some choices, finite set
	- For many, near-infinite set
- **What about exhaustively trying all options ?**
![[Pasted image 20221025191253.png]]


## Boundary Values

- Errors tend to occur at the boundary of a partition.
- Remember to select inputs from those boundaries.

Boundary value testing focuses on the boundaries between equivalence classes, simply because that is where so many defects hide

- Method
![[Pasted image 20221025191712.png]]

## Internal Interaction
- **Low-level functions are expected to interact**
	- Usually this is planned
	- Sometimes unplanned interactions break the system
	- **We want to select tests that thoroughly test interactions**

## Triggering Interactions
- **Interactions** result from combining **values** of individual **choices**
- Want to detect, manage, and resolve inadvertent interactions

## Fire and Flood Control
- FireControl activates sprinklers when fire detected.
- FloodControl cuts water supply when water detected on floor
- **Interaction means building burns down**

## Selecting Test Specifications
- We want to select interesting specifications
- **Category-Partition Method**
	- Apply constraints to reduce the number of specifications
- **Combinatorial Interaction Testing**
	- Identify a subset that covers all interactions between pairs of choices

### Category-Partition Method
![[Pasted image 20221025192255.png]]

#### Identify Choices
![[Pasted image 20221025192321.png]]

#### Identify Representative Values
![[Pasted image 20221025192410.png]]

#### Generate Test Case Specifications
![[Pasted image 20221025192500.png]]

### Combinatorial Interaction Testing

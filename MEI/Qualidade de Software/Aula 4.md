# Goals
![[Pasted image 20221011201810.png]]

# Verification
- Ensuring that an implementation conforms to its specification
	*AKA* -> Under these conditions, does the software work?
- Proper V&V produces dependable software
	**Testing is the primary verification activity**
# Software Testing
- An investigation into system quality
- Based on sequences of *stimuli* and *observations*
	- *Stimuli* that the system must react to.
	- *Observations* of the system reactions
	- *Verdicts* on correctness
![[Pasted image 20221012154528.png]]

**The main purpose of testing is to find fault**
Tests must reflect normal system usage and extreme boundary events



## Bugs ? What are those?
- **Bug is an overloaded term**
	- Does it refer to the bad behavior observed?
	- Is it the source code mistake that led to that behavior?
	- Is it both or either?

	
## Faults and Failures
- *Failure*
	- An execution that yields an incorrect result.
- *Fault*
	- The problem that caused a failure
	- Mistake in the code, omission from the code, misuse
	- **When we observe a failure, we try to find the fault**


# Testing Scenarios
- *Verification*
	- Demonstrate that  software meets the specification
	- Tests tend to reflect "normal" usage
	- Any lack of conformance is a fault
- *Resilience*
	- Show that software can handle rare/extreme situations
	- Tests tend to reflect extreme usage
		- Large volume of data , null data, malformed data , attacks

## Axiom of Testing
Program testing can be used to show the presence of bugs, but **never their absence**

## Test Suite and Test Case
- A *Test suite* is collection of *test cases*
	- Executed together
	- Each test case should be independent
- May have multiple suites in one project
	- Different types of tests, different resource/time needs
- A test case consists of
	- Initialization, test steps, inputs, oracles, tear down


## Anatomy of a Test Case
![[Pasted image 20221012155720.png]]

- **Initialization** 
	- Any steps that must be taken before test execution. 
- **Test Steps** 
	- Interactions with the system, and comparisons between oracle and actual values. 
- **Tear Down** 
	- Any steps that must be taken after test execution


## Test Input
- Any deliberate interactions with a software feature
	- *Generally , call a function through an interface*
- Environment manipulation
	- Set up a database with particular records 
	- Set up simulated network environment
	- Create/delete files
	- Control available CPU/memory/disc space
- Timing
	- Before/at/after deadline
	- Varying frequency/volume of input

## Test Creation and Execution
- Can be *human-driven*
	- Exploratory testing, alpha/beta testing
- or *automated*
	- Test written as code
	- Capture/replay tools can re-execute UI-based tests
	- Automated input generation
## Sources of Input
- *Black Box (Functional) Test Design*
- Use Knowledge about how the system should act to design test cases
	- Requirements, comments, user manuals, intuition
- Tests can be designed before code is written
	- (test-driven development)

- **White Box (Structural) Test Design**
- Input chosen to exercise part of the code
- Usually based on *adequacy criteria*
	- Checklists based on program elements
	- *Branch Coverage* -> Make all conditional statements evaluate to all outcomes (if-statements, switches, loops)
- Fill in the gaps in black-box test design

# Test Oracle - Definition
- A predicate that determines whether a program is correct or not.
	- Based on observations of the program. 
	- Output, timing, speed, energy use, ... 
- Will respond with a *pass* or a *fail* verdict. 
- Can be specific to one test or more general.

## Test Oracle Components
- **Oracle Information**
	- Embedded information used to judge the correctness of the implementation, given the inputs.
- **Oracle Procedure**
	- Code that uses that information and relevant observations to arrive at a verdict. 
	- Often as simple as.
![[Pasted image 20221012161101.png]]

## Oracles are Code
- Oracles must be developed
	- Like the project and is built from the requirements
		- is subject to interpretation by the developer
		- may contain faults
- A faulty oracle can be trouble
	- May result in false positives - “pass” when there was a fault in the system. 
	- May result in false negatives - “fail” when there was not a fault in the system

## Expected-Value Oracles
- Simplest oracle - what exactly should happen ?
- Writen for a single test case, not reusable
![[Pasted image 20221012161419.png]]

## Property-based Oracles
Rather than comparing actual values, use properties about results to judge sequences
Uses assertions, contracts, and other logical properties
![[Pasted image 20221012161506.png]]

## Properties
- Usually written at "function" level
	- For a method or high-level API/UI function
	- Properties based on behavior of that function
- Work for any input to that function
- Trade-off: limited by number of properties
	- Faults missed even if specified properties are obeyed
	- More properties = more expensive to write

## Implicit Oracles
- Check properties expected of any program
	- Crashes and exceptions
	- Buffer overruns
	- Deadlock
	- Memory Leaks
	- Excessive energy usage or downloads
- Faults that do not require expected output to detect

# Testing Stages
- We interact with *systems* through *interfaces*.
	- APIs, GUIs, CLIs 
- Systems built from *subsystems*.
	- With their own interfaces. 
- Subsystems built from *units*. 
	- Communication via method calls. 
	- Set of methods is an interface.

- *Unit Testing*
	- Do the methods of a class work?
- *System-level Testing*
	- *System (Integration) Testing*
		- (Subsystem-level) Do the collected units work? 
		- System-level) Does high-level interaction through APIs/UIs work?
	- *Exploratory Testing*
		- Does interaction through GUI's work?

- *Acceptance Testing / AB Testing*
	- Give product to a set of users to check whether it meets their needs.
		- Alpha/beta Testing - controlled pools of users, generally on their own machine. 
		- Acceptance Testing - controlled pool of customers, in a controlled environment, formal acceptance criteria 
	- Can expose many faults. 
	- Can be planned during requirements elicitation

# Automation vs Human-Driven
- Unit/System Testing heavily use automation
	- Tests written as code
	- Executed repeatedly, often on check-in
- Exploratory/Acceptance Testing often human-driven
	- Humans interact with app
	- Based on scenarios, without pre-planned input
	- Some tool support, but not often repeated exactly

# The V-Model of Development
![[Pasted image 20221012164244.png]]

# Unit Testing
- Testing the smallest "unit" that can be tested
	- Often, a class and its methods
- Tested in *isolation* from all other units
	- *Mocks* the results from other classes
- Test input = method calls
- Test oracle = assertions on output/class variables

- For a unit, tests should be
	- Test all jobs associated with the unit
		- Individual methods belonging to a class.
		- Sequences of methods that can interact.
	- Set and check class variables. 
		- Examine how variables change after method calls.
		- Put the variables into all possible states (types of values)

- Unit tests should cover: 
	- Set and check class variables 
		- Can any methods change identifier, temperature, pressure? 
	- Each “job” performed by the class. 
		- Single methods or method sequences.
		- Vary the order methods are called. 
		- Each outcome of each “job” (error handling, return conditions)

## System (Integration) Testing
- After testing units, test their *integration*
	- Integrate units in one subsystem
	- Then integrate the subsystems
- Test input through a defined interface
	- Focus on showing that functionality accessed through interfaces is correct
	- Subsystems: "Top-level" Class, API
	- System: APY,
## System Testing
## Interface Errors
## GUI Testing
## Exploratory Testing
## Testing Percentages
## Testing
## Acceptance Testing
### Acceptance Testing Types
### Acceptance Testing Stages
## Test Plans
### Why make a Test Plan ?
### Analyze the Product
### Develop the Test Strategy
## Testing Scope
## Identify Testing Types
## Create Test Logistics
## Define Test Objectives
## Define Test Criteria
## Resource Planning
## Plan Test Environment
## Schedule Estimation
[[MEI/Qualidade de Software/Aula 5]]
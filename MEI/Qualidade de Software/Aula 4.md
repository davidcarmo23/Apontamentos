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
	- **Generally , call a function through an interface**
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
- **Black Box (Functional) Test Design**
- Use Knowledge about how the system should act to design test cases
	- Requirements, comments, user manuals, intuition
- Tests can be designed before code is written
	- (test-driven development)

- **White Box (Structural) Test Design**
- Input chosen to exercise part of the code
- Usually based on **adequacy criteria**
	- Checklists based on program elements
	- **Branch Coverage** -> Make all conditional statements evaluate to all outcomes (if-statements, switches, loops)
- Fill in the gaps in black-box test design

# Test Oracle - Definition
- A predicate that determines whether a program is correct or not. ▪ Based on observations of the program. ▪ Output, timing, speed, energy use, ...  Will respond with a pass or a fail verdict.  Can be specific to one test or more general.

## Test Oracle Components
## Oracles are Code
## Expected-Value Oracles
## Property-based Oracles
## Properties
## Implicit Oracles
# Testing Stages

[[MEI/Qualidade de Software/Aula 5]]
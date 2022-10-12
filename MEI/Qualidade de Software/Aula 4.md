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
- May have multiple 

## Anatomy of a Test Case
## Test Input
## Test Creation and Execution
## Sources of Input
# Test Oracle - Definition
## Test Oracle Components
## Oracles are Code
## Expected-Value Oracles
## Property-based Oracles
## Properties
## Implicit Oracles
# Testing Stages

[[MEI/Qualidade de Software/Aula 5]]
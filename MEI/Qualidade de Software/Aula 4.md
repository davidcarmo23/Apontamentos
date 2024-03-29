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
		- System: API, GUI, CLI
	
	## System Testing
	Subsystem made up classes of A, B, and C. We have performed unit testing... 
	- Classes work together to perform subsystem functions. 
	- Tests applied to the interface of the subsystem they form.
	- Errors in combined behavior not caught by unit testing.
	
	## Interface Errors
	- Interface Misuse
		- Malformed data, order, number of parameters
	- Interface Misunderstanding
		- Incorrect assumptions made about called component
		- A binary search called with an unordered array
	- Timing Errors
		- Producer of data and consumer of data access data in the wrong order
	
	
	## GUI Testing
	- Tests designed to reflect *end-to-end* user journeys
		- From opening to closing
		- Often based on *scenarios*
	- GUI Testing
		- Deliberate tests, specific input
		- May be automated or human-executed
	- Exploratory Testing
		- Open-ended, human-driven exploration
	
	
	## Exploratory Testing
	- Tests are not created in advance. 
	- Testers check the system on-the-fly.
		- Guided by scenarios. 
		- Often based on ideas noted before beginning. 
	- Testing as a thinking idea. 
		- About discovery, investigation, and role-playing. 
		- Tests end-to-end journeys through app.
		- Test design and execution done concurrently
	
	- Tester write down ideas to give direction, then create critical, pratical , and useful tests
		- Requires minimal planning. Tester chooses next action based on result of current action
	- Can find subtle faults missed by formal testing
		- Allows tester to better learn system functionality, and identify new ways of using features
	
	## Testing Percentages
	- Unit tests verify behavior of a single class. *70%*
	- System tests verify class interactions. *20%*
	- GUI tests verify end-to-end journeys. *10%*
	![[Pasted image 20221012165840.png]]
	
	## Testing
	- 70/20/10 recommended
	- Unit tests execute quickly, relatively simple
	- System tests more complex, require more setup, slower to execute
	- UI tests very slow, may require humans
	- Well tested units reduce likelihood of integration issues, making high levels of testing easier
	
	## Acceptance Testing
	- Once the system is internally tested, it should be placed in the hands of users for feedback. 
	- Users must ultimately approve the system. 
	- Many faults do not emerge until the system is used in the wild. 
		- Alternative operating environments. 
		- More eyes on the system.
		- Wide variety of usage types
	
	### Acceptance Testing Types
	- *Alpha Testing* 
		- A small group of users work closely with development team to test the software. 
	- *Beta Testing* 
		- A release of the software is made available to a larger group of interested users. 
	- *Formal Acceptance Testing* 
		- Customers decide whether or not the system is ready to be released.
	
	### Acceptance Testing Stages
	- *Define acceptance criteria* 
		- Work with customers to define how validation will be conducted, and the conditions that will determine acceptance. 
	- *Plan acceptance testing* 
		- Decide resources, time, and budget for acceptance testing. Establish a schedule. Define order that features should be tested. Define risks to testing process.
	- *Derive acceptance tests.* 
		- Design tests to check whether or not the system is acceptable. Test both functional and non-functional characteristics of the system. 
	- *Run acceptance tests* 
		- Users complete the set of tests. Should take place in the same environment that they will use the software. Some training may be required.
	- *Negotiate test results*
		- It is unlikely that all of the tests will pass the first time. Developer and customer negotiate to decide if the system is good enough or if it needs more work
	- *Reject or accept the system*
		- Developers and customer must meet to decide whether the system is ready to be released.
	
	## Test Plans
	-  Plan for how we will test the system. 
		- *What* is being tested (units, subsystems, features). 
		- *When* it will be tested (required stage of completion).
		- *How* it will be tested (what scenarios do we run?).
		- *Where* we are testing it (types of environments). 
		- *Why* we are testing it (what purpose do tests serve?). 
		- *Who* will be responsible for writing test cases (assign responsibility to team members).
	
	### Why make a Test Plan ?
	- Guides development team
	- Helps people outside the team understand the testing process
	- Documents rationale for scope of testing, how we judge results, why we chose a strategy
	
	### Analyze the Product
	- Must understand the product before you can test it
		- What are the needs of the users?
		- Who will use the product?
		- What will it be used for?
		- What are the dependencies of the product?
	- Review requirements and documentation
	- Interview stakeholders and developers
	- Perform a product walkthrough (if code is running).
	
	### Develop the Test Strategy
	- Document defining
		- Test Objectives (and how to achieve them)
		- Testing Effort and Cost
	
	![[Pasted image 20221012173841.png]]
	
	## Testing Scope
	- *What are you planning to test?*
		- Software, hardware, middleware
	- And What are you *NOT* going to test?
		- Gives project members a clear understanding about what you are responsible for
	- Must take into account
		- Requirements, budget, skills of you testing team
	
	![[Pasted image 20221012174029.png]]
	
	## Identify Testing Types
	![[Pasted image 20221012174046.png]]
	
	## Create Test Logistics
	- Who will write and execute test cases?
		- What types of testers do you need? 
			- Skills needed for the targeted domain 
		- What is the budget for testing?
			- How many people can you hire to test? 
	- When will each testing activity occur? 
		- When to design and when to execute tests.
		- Pair with appropriate stage of development. 
			- Unit development -> unit testing -> system testing -> ...
	
	## Define Test Objectives
	- What are the goals of the testing process?
		- What features, system elements need to be tested?
		- What quality attributes do we need to demonstrate?
		- For each feature or quality, what scenarios do we want to walk through?
	- Does not include a list of specific tests
		- But, at a high level, should detail scenarios we plan to examine by writing one or more test cases
	
	## Define Test Criteria
	![[Pasted image 20221012174304.png]]
	
	## Resource Planning
	![[Pasted image 20221012174312.png]]
	
	## Plan Test Environment
	![[Pasted image 20221012174323.png]]
	
	## Schedule Estimation
	![[Pasted image 20221012174334.png]]
	
	[[MEI/Qualidade de Software/Aula 5]]
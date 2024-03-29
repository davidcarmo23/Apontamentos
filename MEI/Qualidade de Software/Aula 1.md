		# When is software ready for release ?
		- *When we can't find any bugs*
		- *When we have finished testing*
		- *When the quality*
		
		## Software Quality
		Everyone wants **high-quality** software but the definition of quality isn't the same for everyone
		
		*Quality* encompasses both **what** the system does and **how** it does it
			`How quickly it runs`
			`How secure it is`
			`How available its services are`
			`How easily it scales to more users`
		
		*Quality* is hard to measure and assess objectively
		
		## Quality Attributes
		Describe **desired properties** of the system
		*Developers* prioritize attributes and design system that meets chosen thresholds
		
		
		- *Dependability*  (Most relevant ) -> Ability to consistently offer correct functionality, even under unforeseen or unsafe conditions
		- *Performance* -> Ability to meet timing requirements. When events occur, the system must respond quickly
		- *Security* -> Ability to protect information from unauthorized access whole providing service to authorized users
		- *Scalability* -> Ability to grow the system to process more concurrent requests
		- *Availability* -> Ability to carry out a task when needed, to minimize “downtime”, and to recover from failures
		- *Modifiability* -> Ability to enhance software by fixing issues, adding features, and adapting to new environments
		- *Testability* -> Ability to easily identify faults in a system. Probability that a fault will result in a visible failure.
		- *Interoperability* -> Ability to exchange information with and provide functionality to other systems.
		- *Usability* -> Ability to enable users to perform tasks and provide support to users.  How easy it is to use the system, learn features, adapt to meet user needs, and increase confidence and satisfaction in usage.
		
		### Others
		*Resilience*
		*Supportability*
		*Portability*
		*Development Efficiency*
		*Time to Deliver*
		*Tool Support*
		
		The Qualities **often conflict**
			Fewer subsystems improves performance, but hurts modifiability. 
			Redundant data helps availability, but lessens security. 
			Localizing safety-critical features ensures safety, but degrades performance.
		
		It's important to decide what is important and set a threshold on when it's good enough
		
		## Quality Assurance
		General Principals of QA
		- Know what you are doing
		- Know what you should be doing
		- Know how to measure the difference
		
		### When is software ready for release ? 
		It's ready when you can argue that it's *dependable*
		- Correct, reliable, safe and robust
		- Shown  through **Verification and Validation**
		
		## Verification and Validation
		Activities that must be performed to consider the software **done**.
		
		*Verification* -> Are we building the product right ?
			The process of proving that the software conforms to its specified functional and non-functional requirements.
		
		Does the software work as intended? ▪ Shows that software is dependable.
		
		*Validation* -> Are we building the right product ? 
			The process of proving that the software meets the customer’s true requirements, needs, and expectations.
		Does the software meet the needs of your users? ▪ Shows that software is useful. ▪ This is much harder.
		
		Both of these are important
			A well verified system might not meet the user's needs
			A system can't meet the user's needs unless it is well-constructed
		
		**Testing is the primary activity of verification**
		
		## Verification
		**Verification** is an experiment -> Perform trials, evaluate results, gather evidence
		
		*Specification and Implementation* are roles
			Usually source code and requirement specification
			But also...
				- Detailed design and high-level architecture
				- Design and requirements
				- Test cases and requirements
				- Source code and user manuals
		
		## Software Testing
		- Investigation into system quality
		- Based on sequences of **stimuli** and **observations**
			- *Stimuli* that the system must react to
			- *Observations* of system reactions
			- *Verdicts* on correctness
		
		![[Pasted image 20220926194322.png]]
		
		## Validation
		- Does the software fulfill the user's **actual needs**?
		- 
		Not the same as conforming to a specification.
			▪ If we specify two buttons and implement all behaviors related to those buttons, we can achieve verification. 
			▪ If the user expected a third button, we have not achieved validation.
		
		## Required Level of V&V
		Depends on:
		- **Software Purpose** -> The more critical, the more important that it's reliable
		- **User Expectations** -> Users may tolerate bugs because the benefits outweigh cost of failure recovery
		- **Marketing Environment** -> Competing products - features and cost - and speed to market.
		
		### When does V&V start?
		Can start **as soon as the project starts**
		- Feasibility studies must consider quality assessment. 
		- Requirements can be used to derive test cases. 
		- Design can be verified against requirements. 
		- Code can be verified against design and requirements. 
		- Feedback can be sought from stakeholders at any time.
		
		### Static Verification
		Analysis of system artifacts to discover problems
		*Proofs* ->  Posing hypotheses and making arguments for their validity using specifications, system models, etc.
		*Inspections* -> Manual sanity check on artifacts by people or tools, searching for issues
		
		**Advantages**
		One error can hide other errors.  Inspections not impacted by program interactions. 
		Incomplete systems can be inspected without special code to run partial system. 
		Inspection can assess quality attributes such as maintainability, portability, code style, program inefficiencies, etc.
		
		## Dynamic Verification
		Exercising and observing the system to argue that it meets the requirements. 
		- **Testing**: Formulating sets of input to demonstrate requirement satisfaction or find faults
		- **Fuzzing**: Generating semi-random input to locate crashes and other anomalies. 
		- **Taint Analysis**: Monitoring how faults spread by corrupting system variables.
		
		**Advantages**
		
		Discovers problems from runtime interaction, timing problems, or performance issues.
		Often cheaper than static verification.
			▪ Easier to automate. 
			▪ However, cannot prove that properties are met - cannot try all possible executions
		
		## The trade-Off game
		Software engineering is the process of designing, constructing and maintaining the best software possible given the available resources. Always trading off between what we want, what we need, and what we've got.
		
		*Better, faster, or cheaper - pick any two*
		
		## Perfect Verification
		Verification is an instance of the **halting problem**
		
		There is at least one program for which any technique cannot obtain an answer in finite time. Testing - cannot exhaustively try all inputs. 
		Must accept some degree of inaccuracy
		
		## Verification Trade-Offs
		**Pessimistic Inaccuracy** -> not guaranteed to program even if the it possesses X
		**Optimistic Inaccuracy** -> may accept program that does not possess X
		**Property Complexity** -> if X is too difficult to check, substitute simpler property Y
		
		### How can we assess Readiness
		Finding all faults is nearly impossible.
		Instead, decide when to stop V&V. 
		Need to establish criteria for acceptance. 
			How good is “good enough”? 
		Measure dependability and other quality attributes and set threshold to meet.
		
		### Product Readiness
		Put it in the hands of human users. 
		**Alpha/Beta Testing** 
			▪ Small group of users using the product, reporting feedback and failures.
			▪ Use this to judge product readiness. 
			▪ Make use of dependability metrics for quantitative judgement (metric > threshold). 
			▪ Make use of surveys as a qualitative judgement.
			
		### Ensuring Quality of Successive Releases
		V&V do not end with the release of the software. 
		
		▪ Software evolves - new features, environmental adaptations, bug fixes. 
		▪ Need to test code, retest old code, track changes. 
		▪ When code changes, rerun tests to ensure tested elements still works. 
		▪ Retain tests that exposed faults to ensure they do not return.
		
		### Improving the Development Process
		Try to learn from your mistakes in the next project. 
		▪ Collect data during development. 
		• Fault information, bug reports, project metrics (complexity, # classes, # lines of code, test coverage, etc.). 
		▪ Classify faults into categories. 
		▪ Look for common mistakes. 
		▪ Learn how to avoid such mistakes. 
		▪ Share information within your organization.
		
		## Software Testing Myths
		![[Pasted image 20220926223504.png]]
		
		[[MEI/Qualidade de Software/Aula 2]]
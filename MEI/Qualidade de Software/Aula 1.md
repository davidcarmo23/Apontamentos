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
- 
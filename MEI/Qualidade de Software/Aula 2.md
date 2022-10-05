[[MEI/Qualidade de Software/Aula 1]]

# Correctness
- A program is **correct** if it is always consistent with its specification
- Depends on quality and detail of requirements
	Easy to show with respect to a weak specification
	Often impossible to prove with a detailed specification
- Correctness is rarely probably achieved

# Reliability
- Statistical approximation of correctness
- The likehood of correct behavior from some period of observed behavior
	Time Period, number of system executions
- Measured relative to a specification and usage profile (expected pattern of interaction)
	Dependent on how the system is used by a type of user

# Dependence on Specifications
- Correctness and reliability
	- Success relative to the strength of the specification
		- **Hard to meaningfully prove anything for strong spec**
	- Severity of a failure is not considered
		- **Some failures are worse than others**
- Safety revolves around **a restricted specification**
- Robustness revolves around **everything not specified**

# Safety 
- Safety is the **ability to avoid hazards**
	- *Hazard* -> defined undesirable situation
		- Generally serious problems
- Relies on the specification of hazard
	- What the hazard is and how it will be avoided in the software
	- We prove or show evidence that the hazard is avoided
	- Only concerned with hazards, so proofs are often possible

# Robustness
- Software that is correct may fail when the assumptions of its design are violated
	- How it fails matters
- **Software that gracefully fails is robust**
	- Design the software to counteract unforeseen issues or perform graceful degradation of services
		- Looking at how a program could fail and handling those situations
	- Cannot be proved, but is a goal to aspire to

# Dependability Property Relations




[[MEI/Qualidade de Software/Aula 3]]
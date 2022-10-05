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
![[Pasted image 20221005112452.png]]


# Measuring dependability
- Must establish a criteria for when the system is dependable enough to release
	- Correctness hard to prove conclusively. 
	- Robustness/Safety important, but do not demonstrate functional correctness.
	- **Reliability is the basis for arguing dependability**. 
		- Can be measured. 
		- Can be demonstrated through sufficient volume of testing.

# What is Reliability?
- Probability of failure-free operation for a **specified time** in a **specified environment** for a **given purpose**
	- Depends on the system and type of user
- How well users **think** the system provides services they require

## Improving Reliability
- **Improved when faults in the most frequently-used parts of the software are removed**
![[Pasted image 20221005113021.png]]


## Reliability is measurable
- Reliability can be defined and measured
- Reliability requirements can be specified:
	- **Non-functional** requirements define number of failures that are acceptable during normal use or time in which system is allowed to be unavailable
	- **Functional** requirements define how the software avoids, detects, and tolerates failures

## How to measure Reliability
- Hardware metrics often aren't suitable for software since they are based on component failures and the design is assumed to be correct
- Software failures are always design failures
	- Often the system is available even though a failure has occurred
	- Metrics consider **failure rates, uptime and time between failures**

## Metric 1 : 

[[MEI/Qualidade de Software/Aula 3]]
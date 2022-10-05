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

## Metric 1 : Availability
- Can the software carry out a task when needed ?
	- Encompasses **reliability** and **repair**
		- Does the system tend to show correct behavior ?
		- Can the system recover from an error ?
- The ability to mask or repair faults such that the cumulative outages do not exceed a required value over a time interval
	- **Both a reliability measurement and an independent quality attribute**
- Measured as **(uptime) / (total time observed)**
![[Pasted image 20221005114037.png]]
### Availability Considerations
- Time to repair is the time until the failure is no longer observable
	- Can be hard to define
- Software can remain partially available more easily than hardware
- If code containing fault is executed, but the system is able to recover there was no failure


## Metric 2 : Probability of Failure on Demand (POFOD)
- Likelihood that a request will fail
- **(failures/requests over observed period)**
- Used in situations where a failure is serious

## Metric 3 : Rate of Occurrence of Fault (ROCOF)
- Frequency of occurrence of unexpected behavior
- **(number of failures / total time observed)**
- Most appropriate metric when requests are made on a regular basis (such as a shop).

## Metric 4 : Mean Time Between Failures (MTBF)
- Average length of time between observed failures.
- Used for systems with long user sessions, where crashes can cause major issues

## Metric 5 : Mean Time To Recover (MTTR)
- Average time to recover from failure.

## Probabilistic Availability
- Probability that system will provide a service within required bounds over a specified time interval. 
	- **Availability = MTBF / (MTBF + MTTR)**


# Reliability Economics
- May be cheaper to accept unreliability and pay for failure costs
- Depends on social/political factors and system
	- Reputation for unreliability may hurt more than cost of improving reliability. 
	- Cost of failure depends on risks of failure. 
		- Health risks or equipment failure risk requires high reliability. 
		- Minor annoyances can be tolerated.

# Performance
- Ability to meet timing requirements
- Characterize pattern of input events and responses
	- Requests served per minute
	- Variation in output time
- Driving factor in software design
	- Often at the expense of other quality attributes
	- **All** systems have performance requirements

## Performance Measurements
- **Latency** -> The time between the arrival of the stimulus and the system’s response to it.
	- Time it takes to complete an interaction
	- **Responsiveness** : how quickly the system responds to routine tasks
	- ![[Pasted image 20221005115454.png]]
	- **Turnaround time** = time to complete larger tasks
	- ![[Pasted image 20221005115526.png]]
- **Response Jitter** -> The allowable variation in latency
	- ![[Pasted image 20221005115624.png]]
- **Throughput** -> Usually number of transactions the system can process in a unit of time
	- ![[Pasted image 20221005115641.png]]
	- ![[Pasted image 20221005115705.png]]
- **Deadlines in processing** -> Points where processing must have reached a particular stage
	- ![[Pasted image 20221005115725.png]]
- **Number of events not processed** because the system was too busy to respond
	- ![[Pasted image 20221005115806.png]]

# Scalability 
- Ability to process increasing number of requests
	- While meeting performance requirements
- Horizontal scalability
	- Adding more resources to logical units
		- Adding another server to a cluster
		- Elasticity
- Vertical scalability
	- Adding more resources to a physical unit

- How can we effectively utilize additional resources?
- Requires that additional resources
	- Result in performance improvement
	- Did not require undue effort to add
	- Did not disrupt operations
- The system must be design to scale

## Assessing Scalability
- Ability to address more requests is often part of the **performance assessment**
- Assessing scalability directly measures impact of adding or removing resources. 
- Response measures reflect: 
	- Changes to performance. 
	- Changes to availability. 
	- Load assigned to existing and new resources.

# Security
- Ability to protect data and information from unauthorized access
	- **while still providing access to people and systems that are authorized**
- Can we protect software from attacks ?
	- Unauthorized access attempts
	- Attempts to deny service to legitimate users

- Processes that allow owners of resources to control access
	- Who: Actors (systems or users). 
	- Resources are sensitive elements, operations, and data of the system. 
	- Policies define legitimate access to resourced. 
	- Enforced by security mechanisms used by actors to gain access to resources.
	- ![[Pasted image 20221005120657.png]]

## Security Characterization (CIA)
- Confidentiality
	- Data and services protected from unauthorized access
- Integrity
	- Data/Services not subject to unauthorized manipulation
- Availability
	- The system will be available for legitimate use

## Supporting CIA
- Authentication : Verifies identities of all parties
- Nonrepudiation : Guarantees that the sender cannot deny sending, and recipient cannot deny receiving
- Authorization : Grants privilege of performing a task

## Security Approaches
- Achieving security relies on:
	- Detecting attacks. 
	- Resisting attacks. 
	- Reacting to attacks. 
	- Recovering from attacks.

- Objects being protected are:
	- Data at rest.  
	- Data in transit.
	- Computational processes

## Security is Risk Management
- **Not simply secure/not secure**
	- All systems will be compromised. 
	- Try to avoid attack, prevent damage, and quickly recover.
	- Balance risks against cost of guarding against them.
	- Set realistic expectations!
	- ![[Pasted image 20221005121255.png]]

## Assessing Security
- Measure of system’s ability to protect data from unauthorized access while still providing service to authorized users
- Assess how well the system responds to attacks
	- Stimuli are attacks from external systems/users or demonstrations of policies (log-in, authorization). 
	- Responses: auditing, logging, reporting, analyzing.
- No universal metrics for measuring 
[[MEI/Qualidade de Software/Aula 3]]
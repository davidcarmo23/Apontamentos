# Goals
![[Pasted image 20221005140413.png]]

# Scenarios
- A description of an interaction between an external entity and the system. Defines:
	- Event that triggers the scenario
	- Interaction initiated by the external entity
	- The response required of the system (defined in terms of quality attributes)
- Similar to use cases or user stories, but examines both quality and functionality

![[Pasted image 20221005140602.png]]

## Scenario Usage
![[Pasted image 20221005140626.png]]

## Scenario Format
![[Pasted image 20221005140756.png]]
![[Pasted image 20221005140810.png]]
![[Pasted image 20221005140823.png]]

## Response Measures
- Most quality measurements are non-deterministic
	- **Time-based measures should be probabilistic**
		- 95% of the time, the response should be N. **(common case)** 
		- 99% of the time, the response should be M. **(worst case)**
	- For real-time systems, time measurements should give **absolute bounds**
		- Look at worst case scenario
	- For other measures, gives an absolute threshold

## What do we do with Scenarios ? 
- System Design 
- Stakeholder Negotiation
- Exploratory Testing
	- Human experiments with app
- Formal Test Cases
	- Assign specific input and check response

## Good Scenarios
- Credible 
	- Realistic scenario
- Valuable
	- Can be directly used during architectural definition
- Specific
	- Addresses a single, concrete situation
- Precise
	- Intended user of scenario should be clear about the described situation and response
- Comprehensible
	- Writing should be unambiguous and free of jargon

## Effective Scenario Use
- **Identify a focused scenario set**
	- Too many scenarios can be distracting
	- Prioritize no more than 15-20
- **Use distinct scenarios**
	- Avoid having multiple scenarios centered around near identical events. Redundant
	- Consider demands placed on the system
- **Use scenarios early**
	- Most impactfull early in development to focus design activities on most important aspects of the system

# Reliability Scenarios
- **The ability to minimize the number of observed failures**
- Scenarios revolve around one function accessed through an interface
	- Give context on type of user if it impacts system execution or perceived reliability

## Reliability Metrics
- POFOD: (failures/ requests over period) 
- ROCOF: (failures / total time observed) 
- MTBF: Average time between observed failures. 
- **Availability is a quality attribute of its own**

## Reliability Scenarios
![[Pasted image 20221005142754.png]]
![[Pasted image 20221005142905.png]]
![[Pasted image 20221005142939.png]]

# Availability Scenarios
- Ability of the system to mask or repair failures such that the outage period does not exceed a required valuer over a time period
- **Measure how the system responds to failure**
	- What does the system do to return to normal ?
	- How long does it take?
- **Stimuli should always be a failure**
- Response measures should always include a measure of availability
	- Availability threshold
		- (“Availability must be at least 0.9999”)
	- Time to detect or repair fault
		- (“95% of the time, the failure is detected within 5ms”)
	- Time system in degraded mode
		- (“95% of the time, must be back online within 10 minutes”)
- Scenarios must distinguish physical failures in the system and the software's perception of the failure
	- Do not assume software is omniscient
- Scenarios tend to deal with:
	- Failure of internal component or external system
	- Reconfiguration of physical system
	- Maintenance or reconfiguration

![[Pasted image 20221005144635.png]]
![[Pasted image 20221005144709.png]]
![[Pasted image 20221005144727.png]]
![[Pasted image 20221005144742.png]]

# Performance Scenarios
- Measure system 
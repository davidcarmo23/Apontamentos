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
	- Realisti
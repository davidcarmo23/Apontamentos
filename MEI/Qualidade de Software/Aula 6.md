# Today's Goals
![[Pasted image 20221025192610.png]]

## Exploratory Testing
- Testers check the system on-the-fly
	- Guided by scenarios
	- Often based on ideas noted before beginning
- Testing as a thinking idea
	- About discovery, investigation, and role-playing
	- Tests end-to-end journeys through app
	- Test design and execution done concurrently

- Tester write down ideas to give direction, then create tests "live"
	- Tester chooses next action based on results seen
- Can find subtle faults missed by formal testing
	- Allows tester to better learn system functionality, and identify new ways of using features

### Session-Based Exploratory Testing
![[Pasted image 20221025193520.png]]

### Session Report Items
- **Mission: Overall goal**
- **Charter: Features and scenarios to focus on**
- **Start and end time of session**
- **Duration of session**
- **Testing notes** - Journal of actions taken
- **Fault information** - Describe each fault. File a bug report, include tracker ID.
- **Issues Information** - If an issue prevents or complicates testing, describe it.
	- Include **data files**
- **Set-up Time** - % of time required to set-up
- **Test Design and Execution Time** - % of time spent purely on testing

### Tips for Exploratory Testing
- Divide the application into modules or features, then try to further divide
- Make a checklist of all the features and put a check mark when each is covered
- Start with a basic scenario and then gradually enhance it to add more features to test it
![[Pasted image 20221025193926.png]]

### Pair-Based Exploratory Testing
![[Pasted image 20221025194106.png]]

### Automating Exploratory Testing
![[Pasted image 20221025194132.png]]
![[Pasted image 20221025194208.png]]

#### Capture and Replay Tools
![[Pasted image 20221025194155.png]]

### Using Tours in Exploratory Testing
![[Pasted image 20221025194242.png]]

### Exploratory Tours
![[Pasted image 20221025194303.png]]
#### Business District
![[Pasted image 20221025194321.png]]

#### Guidebook Tour
![[Pasted image 20221025194338.png]]

##### Guidebook Variants
![[Pasted image 20221025194354.png]]

#### Fed-Ex Tour
![[Pasted image 20221025194415.png]]

#### Historic District
![[Pasted image 20221025194510.png]]

#### Bad Neighborhood Tour
![[Pasted image 20221025194526.png]]

#### Museum Tour
![[Pasted image 20221025194542.png]]

#### Entertainment District
![[Pasted image 20221025194607.png]]

#### Supporting Actor Tour
![[Pasted image 20221025194629.png]]

#### Tourist District
![[Pasted image 20221025194644.png]]

#### Supermodel Tour
![[Pasted image 20221025194707.png]]

#### Hotel District


## Automation vs Human-Driven
- Unit/System Testing heavily use automation
	- Tests written as code
	- Executed repeatedly, often on check-in
- Exploratory/Acceptance Testing often human-driven
	- Humans interact with app
	- Based on scenarios, without pre-planned input
	- Some tool support, but not often repeated exactly

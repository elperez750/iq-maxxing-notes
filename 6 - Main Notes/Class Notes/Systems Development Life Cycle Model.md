


2026-03-31 11:11

Status: #baby 

Tags: [[Software Development]], [[Project Management]]

# Systems Development Life Cycle Model

##### Author: Nathan White


## References
https://cwu.instructure.com/courses/116264/files/15993920?module_item_id=4657550



### Notes

## What is SDLC

- Basically first developed int he 1960s to mange large projects
- SDLC is a model defining a process of a set of phases for planning, analysis, design, implementation, maintenances


![[Pasted image 20260331182528.png|621]]



### Planning phase

###### The request is initialized by someone who acts as a sponsor for the idea

#### The objective of the different phases are:
- To determine how the request fits with the company’s strategy or business goals.

###### Basically ask the question if the software is needed in the first place. I can honestly see this solving so many headaches in the future


- To conduct a feasibility analysis, which includes an analysis of the technical feasibility (is it possible to create this?), the economic feasibility (can we afford to do this?), and the legal feasibility (are we allowed to do this?).

###### There many ambitious ideas. I'm sure that the founders of Meta or Microsoft or Netflix were fighting through these things. But the difference is the confidence and the amount of risk these people were willing to take. 


- To recommend a go/no go for the request. If it is a go, then a concept proposal is also produced for management to approve

###### Essentially shut it down before it has the potential to waste a lot of money.

### Analysis Phase:


#### Once the concept is approved, the project is formalized with a new project team

#### The goal of this phase is the following:
-  Document key procedures

###### I feel like this would be better off in the planning stage. Unless by key procedures, it's getting more into the nitty gritty of things.


- Identify and Interview key stakeholders.

###### And users as well. Unless a user is considered a stake holder.



- Develop the data requirements
- To produce a system-requirements document as the result of this phase. This has the details to begin the design of the system.

###### From my analysis, this is basically the step where the project gains more traction and were ideas are formalized better. For example, in the planning phase someone might say "Lets build an ai agent in our shopping app", and the analysis phase might be figuring out what it would need to do.

### Design Phase
#### Once the system requirements are approved, the team may be reconfigured to bring in more members. This phase aims for the project team to take the system requirements document created in the previous phase and develop the specific technical details required for the system. 


#### The following objectives are:
- Translate the business requirements into specific technical requirements

###### So from my understanding, the analysis stage was just getting the big pieces of the project formalized, now in the design phase, the tech teams for example are  determining things such as the tech stack


- Design the user interface, database, data inputs and outputs, and reports
- Produce a system-design document as the result of this phase. This document will have everything a programmer will need to create the system.

###### Basically responsibilities for each person. 


### Implementation Phase


#### Once a system design is approved, the software code finally gets written in the programming phase, and the development effort for other elements such as hardware also happens. The purpose is to create an initial working system. 


#### The following objectives are:

- Develop the software code, and other IS components. Using the system- design document as a guide, developers begin to code or develop all the IS project components.
- Test the working system through a series of structured tests such as:
	- The first is a unit test, which tests individual parts of the code for errors or bugs.
	- Next is a system test, where the system's different components are tested to ensure that they work together properly.
	- Finally, the user-acceptance test allows those that will be using the software to test the system to ensure that it meets their standards.
	- Iteratively test any fixes again to address any bugs, errors, or problems found during testing.
	- Train the users
	- Provide documentation
	- Perform necessary conversions from any previous system to the new system.
	- Produce, as a result, the initial working system that meets the requirements laid out in the analysis phase and the design developed in the design phase.

###### So the implementation stage is basically the coding and the testing. For example, the duties might be split in the design phase, and now the implementation stage everyone knows what to do.

###### I feel like this is honestly the fastest stage. It takes more effort to flush out an idea and then figure out requirements and costs. I feel like this is probably why [[AI]] will not take over our jobs anytime soon.

### Maintenance Phase

#### This phase takes place once the implementation phase is complete. In this phase, the system must have a structured support process in place to:

- Report bugs
- Deploy bug fixes
- Accept requests for new features
- Evaluate the priorities of reported bugs or requested features to be implemented
- Identify a predictable and regular schedule to release system updates and perform backups.
- Dispose of data and anything else that is no longer needed


###### I feel like in contrast to the implementation stage, this is probably the longest, as technically you could still be getting contacted about issues years after building the product. At the end of the day, there are software updates that must be accounted for.


## Waterfall Model

#### This is basically a specific instance of the SDLC model. 

#### The five phases are the following:
- Requirements
- Design
- Implementation
- Verification
- Maintenance

#### Each phase must be completed before the next phase can begin

###### Makes sense. Imagine building an app without knowing for sure what the app will do. Sounds like chaos.

![[Pasted image 20260331185130.png]]



### Advantages and Disadvantages of SDLC and Waterfall.

| Advantages                                                                                                             | Disadvanges                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The robust process to control and track changes to minimize the<br>number of risks can derail the project unknowingly. | Take time to record everything, which leads to additional cost and time to the schedule.                                                                               |
| Standard and transparent processes help the management of large teams.                                                 | Too much time spent attending meetings, seeking approval, etc. which lead to additional cost and time to the schedule.                                                 |
| Documentation reduces the risks of losing personnel, easier to add<br>people to the project.                           | Some members do not like to spend time writing, leading to the additional time needed to complete a project.                                                           |
| Easier to trace a problem in the system to its root whenever errors<br>are found, even after the project is completed. | It is difficult to incorporate changes or customers’ feedback since the project has to go back to one or more previous phases, leading<br>teams to become risk-averse. |

###### From what I'm getting, waterfall would be good for projects where not much changes and where everything is solid from the start. If the project takes too much, this kind of project management system would be terrible


###### For a project that would change a lot, I'm thinking that a project such as 




## Rapid Application Development (RAD)

#### This is a methodology which focuses less on planning and incorporating changes on an ongoing basis. This system focuses on getting feedback from users and immediately iterating on the product



![[Pasted image 20260331185858.png]]


### Requirements

#### This 

### User Design


### Construction


### Cutover
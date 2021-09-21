# Software Engineering

Software Engineering is the application of a systematic, disciplined, quantifiable approach to the development, operation and maintenance of software; that is, the application of engineering to software. (IEEE)

Simply put: The purpose of software engineering is to find ways of building quality software.

## 1. The software process model definition

To develop software we often use a software process model, aka a software life-cycle model. These mdels consist of a sequence of decisions:

- The activities;
- The order;
- The transition criteria;

### 1.1 Deciding factors on the choice of model

To decide which model to use there are a few criteria to keep in mind:

- The quality of requirements: A fixed **scope** is only possible with a clear set of requirements. If there are sudden changes and the **requirements** change it means the **scope** isn't fixed;
- Domain complexity: Is the company environment complex? If so it results in extra conditions being applied to the **scope**;
- Is the technology proven and/or complex? If it's complex it's difficult to set a fixed **scope**.
- Flexibility: Is flexibility important? Do we expect **requirements** to change? If so we again can't sit a fixed **scope**;
- Project size: When we have a small project it's easy to set a fixed **scope**, for a large project it isn't;
- Criticality: Criticality pertains to the compliance, medical or safety critical systems. If the criticality is high we need to have a fixed **scope**;
- Stakeholder involvement: Stakeholders might have their say in the definition of **requirements**;
- Team skills: Insight into the skills of the team is a necessity when defining the **requirements**. Are we capable of implementing the **requirements**;

### 1.2 The iron triangle

The key defining factors from above can be boiled down to the following three keywords:

- Scope
- Resources
- Time

The iron triangle helps decide which software process model to use:

- Waterfall: **Scope** is fixed but **time** and **resources** may vary.
- Iterative: **time** and **resources** are fixed but **scope** may vary.

## 2. Software process model: Waterfall

The Waterfall software process model takes a phase-by-phase approach where we (in order): Plan, build, test, review and deploy. In this approach the requirements are fixed as early as possible, as after the build process you cannot change the requirements any longer.

### 2.1 Waterfall problems

The Waterfall framework has a few problems:

- There's great difficulty in handling changing requirements, changes will be limited so this model should only be used when the requirements are well understood and the **scope** is fixed;
- It's difficult to handle technical risks;
- Customer feedback comes at the end which means you might end up with a product that doesn't satisfy customers;
- Mostly used for large projects where a system is developed at several locations:
	+ A lot of documentation with a lot of roles;
	+ The plan-driven nature of the Waterfall model helps coördinate the work;
	+ Useful for systems where compliance is key.

## 3. Software process model: Iterative

The Iterative software process model repeats the same development steps over and over until you reach the desired result where all requested functionality is covered.
In this process we:

- Plan and Evaluate;
- Gather requirements;
- Design and implement;
- Verify;

This way you can start with a small piece of functionality and iterate on it, even if the requirements changes without any issue.

### 3.1. RUP framework

- UP stands for Unified Software Development Process which is an iterative and incremental framework;
- RUP is an elaboration of UP which is owned by IBM;
- OpenUP, Open Unified Process, is an open-source framework maintained by the Eclipse Foundation;
- RUP-Op-Maat is an elaboration of RUP and is owned by Ordina;

RUP has four phases which are repeated over and over which ultimately delivers a potentially shippable product incrament:

- The inception phase:
	+ Scope all the work, initial budget estimates are made;
	+ Align visions;
	+ Identify risks and global planning;
	+ Define acceptance criteria which are testable;
	+ Produces the following artifacts:
		* Vision;
		* Risk list;
		* Use Case Model;
		* Acceptance Plan;
		* Global Software Development Plan (SDP);
- The elaboration phase:
	+ Prove the technical feasibility and validate the architecture;
	+ Create a design/proof-of-concept;
	+ Produces the following artifacts:
		* PoC;
		* Complete Software Development Plan (SDP);
		* SAD;
		* Test plan;
		* Development and testing environment;
- The construction phase:
	+ Focus on implementation;
	+ Do this in iterations/sprints;
- The transition phase:
	+ Focus on the deployment;
	+ Hand the product over to maintenance;

## 4. Software process model: Agile

Agile is seen as an incremental AND iterative process.

Agile development has analysis, design, implementation and testing in every iteration/sprint as opposed to RUP. Every sprint delivers a small product.

Agile uses a conversational approach where requirements are continuously negotiated during development. This way, risks or changes are identified at the start of a sprint which makes their impact minimal.

### 4.1 Agile problems

Agile is good in many ways but has a few problems:

- Difficult to plan the amount of iterations needed;
- Only works for smaller teams;
- Requires skilled people as every team member has many roles;
- Development is intense as the need to complete each feature within the corresponding iteration is pressuring;
- Active client/user involvement is required which means they need to be available during the project and which means the developers must comply and adapt to a change of culture;
- Risks lie with the customers as a fixed price tender is not possible;
- Product owner must manage the interests of the different stakeholders as they'll be tempted to keep demanding new functionality;
- Quality might lack as the product is a moving target with a 'code and fix' approach;
- Less documentation as 'the code' = 'the design'. This results in a slow start for newcomers, inefficient maintenance when there's a problem and a loss of the big picture;

### 4.2 Scrum framework

Scrum is a framework for organizing and managing work. It has a limited scope where the focus lies on self-organization of teams. The word **framework** means that you have to adapt Scrum to your specific situation, which results in a version of Scrum that is uniquely yours.

The word Scrum comes from the comparison with playing rugby. In rugby the whole team takes the ball forward, they scrum, as opposed to a relay race where a baton is passed on from player to player which is defined as waterfall.

Scrum, unlike RUP, doesn't say how to do:

- The requirements analysis;
- The business alignment;
- The project planning;
- The cost estimation;
- The definition of scope;
- How to put together a team;
- The architecture;
- The definition of the first sprint;

Also, Scrum doesn't have an ending, you either continue with the next sprint or stop the iteration.

#### 4.2.1 Scrum pros and cons

Scrum has a few pros:

- Scrum, like any Agile framework, creates accountability;
- Has a clear definition of results;
- Supports a change of plans due to constant renegotiation;
- Allows for immediate feedback;
- Has a focus on the business value with an efficient use of time and money;

Scrum also has a few cons, which are listed in the Agile problems in chapter 4.1.

#### 4.2.2 Scrum roles

Scrum defines a few roles:

- The product owner:
	+ Collaborates with the stakeholders;
	+ Relays to the development team;
	+ Defines and is responsible for the **product backlog**:
		* Defines the project scope;
		* Explains which features and functionality to build;
		* Defines priority for each feature;
	+ Determines a release date and the content in that release;
	+ Adjusts features and priority in every iteration as fit;
	+ Accepts or rejects work results;
- The Scrum master:
	+ Responsible for enacting the Scrum values and practices aka the **Scrum ceremonies**;
	+ Helps the team to understand and use self-organization;
	+ Removes roadblocks;
	+ Makes the **Scrum ceremonies** efficient and effective;
	+ Shields the team from external interferences;
- The Scrum team:
	+ A cross-functional collection of programmers, testers, designers, etc;
	+ Available full-time and preferably in the same room;
	+ Are self-organizing in the sense that no titles are given;
	
#### 4.2.3 Scrum ceremonies

Scrum has a few ceremonies that the Scrum master should enforce:

- The sprint planning:
	+ The product owner submits a set of features that are collected into a prioritzed list (**the product backlog**);
	+ The team selects items from the product backlog they believe they can commit to completing (**the sprint backlog**):
		* User stories can be broken down into tasks;
		* Tasks are estimated in hours (1-16 hours);
		* Estimation is done by the whole team collaboratively;
	+ No changes are made during a sprint;
	+ A sprint planning looks like the following:
		* Define a sprint goal and present the backlog;
		* Re-prioritize, re-estimate, split or combine stories using cards;
		* Do a task breakdown (without PO);
		* Estimate the velocity, draw the line (without PO);
- The daily standup/daily Scrum meeting:
	+ Takes about 15 minutes;
	+ Shows the Scrum board for an actual status;
	+ Is more about the team's current status as opposed to problem solving:
		* Everyone's allowed to be present;
		* Only the team members, Scrum master and product owner can talk;
	+ Helps to avoid other unnecessary meetings;
	+ Everyone answers three questions:
		* What did I do yesterday?
		* What will I do today?
		* Is anything in my way?
- The sprint demo & review:
	+ The team presents what it accomplished during the sprint;
	+ Typically takes the form of a demo of new features or underlying architecture;
	+ Is informal, prep takes a maximum of 2 hours and uses no slides;
	+ The whole team participates;
	+ Management, customers and developers from other projects are invited;
	+ The team only demonstrates tested usable pieces of code/software as they're completed stories on the **sprint backlog**;
- The sprint retrospective:
	+ A separate meeting for the Scrum team only;
	+ The process is inspected and adapted where fit;
	+ Typically done after every sprint of 1~2 weeks;
	+ Discusses what is and isn't working;
	+ Takes about 15~30 minutes;
	+ Focus on a few improvements per sprint;
	
#### 4.2.4 Scrum artifacts

The Scrum framework produces a few artifacts:

- Product backlog:
	+ Prioritizes items on priority;
	+ Top items are small and detailed so they can be moved to the next sprint;
	+ Bottom items are small and have few details, they need to be iterated on;
	+ As Agile is a **conversational approach** the product backlog items are refined through a series of conversations with stakeholders, the PO and developers;
	+ The product backlog consists of users stories that presents a small use case in the form of a user story: "As a X, In want to Y, so that I Z";
	+ Each item in the product backlog has a number of story points that indicate a certain complexity, represented by the Fibonacci sequence for example;
	+ Story point estimation is done using planning poker:
		* Estimates are done by the people who're going to do the work, but all team members attend;
		* Different viewpoints will be discussed and result in better estimates;
		* If a feature/item is deemed to large it has to be split into smaller ones;
		* A round of planning poker goes as follows:
			- Moderator reads the description of a user story;
			- Members ask questions to the product owner;
			- Each member picks a card that represents his/her estimate in story points;
			- All members show the cards simultaneously;
			- A group discussion takes place where the members with highest and lowest numbers explain themselves;
			- If there's no agreement made another round takes place;
- Sprint backlog:
	+ Has a sprint goal which is a short statement of what the work will be focuses on during the sprint;
	+ Is a snapshot of stories from the product backlog;
- Sprint burndown chart: A chart that is displays the amount of story points finished on each day;
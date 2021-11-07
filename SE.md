# Software Engineering

Software Engineering is the application of a systematic, disciplined, quantifiable approach to the development, operation and maintenance of software; that is, the application of engineering to software. (IEEE)

Simply put: The purpose of software engineering is to find ways of building quality software.

## 1. The software process model definition

To develop software we often use a software process model, aka a software life-cycle model. These models consist of a sequence of decisions:

-   The activities;
-   The order;
-   The transition criteria;

### 1.1 Deciding factors on the choice of model

To decide which model to use there are a few criteria to keep in mind:

-   The quality of requirements: A fixed **scope** is only possible with a clear set of requirements. If there are sudden changes and the **requirements** change it means the **scope** isn't fixed;
-   Domain complexity: Is the company environment complex? If so it results in extra conditions being applied to the **scope**;
-   Is the technology proven and/or complex? If it's complex it's difficult to set a fixed **scope**.
-   Flexibility: Is flexibility important? Do we expect **requirements** to change? If so we again can't sit a fixed **scope**;
-   Project size: When we have a small project it's easy to set a fixed **scope**, for a large project it isn't;
-   Criticality: Criticality pertains to the compliance, medical or safety critical systems. If the criticality is high we need to have a fixed **scope**;
-   Stakeholder involvement: Stakeholders might have their say in the definition of **requirements**;
-   Team skills: Insight into the skills of the team is a necessity when defining the **requirements**. Are we capable of implementing the **requirements**;

### 1.2 The iron triangle

The key defining factors from above can be boiled down to the following three keywords:

-   Scope
-   Resources
-   Time

The iron triangle helps decide which software process model to use:

-   Waterfall: **Scope** is fixed but **time** and **resources** may vary.
-   Iterative: **time** and **resources** are fixed but **scope** may vary.

## 2. Software process model: Waterfall

The Waterfall software process model takes a phase-by-phase approach where we (in order): Plan, build, test, review and deploy. In this approach the requirements are fixed as early as possible, as after the build process you cannot change the requirements any longer.

### 2.1 Waterfall problems

The Waterfall framework has a few problems:

-   There's great difficulty in handling changing requirements, changes will be limited so this model should only be used when the requirements are well understood and the **scope** is fixed;
-   It's difficult to handle technical risks;
-   Customer feedback comes at the end which means you might end up with a product that doesn't satisfy customers;
-   Mostly used for large projects where a system is developed at several locations:
    -   A lot of documentation with a lot of roles;
    -   The plan-driven nature of the Waterfall model helps coördinate the work;
    -   Useful for systems where compliance is key.

## 3. Software process model: Iterative

The Iterative software process model repeats the same development steps over and over until you reach the desired result where all requested functionality is covered.
In this process we:

-   Plan and Evaluate;
-   Gather requirements;
-   Design and implement;
-   Verify;

This way you can start with a small piece of functionality and iterate on it, even if the requirements changes without any issue.

### 3.1. RUP framework

-   UP stands for Unified Software Development Process which is an iterative and incremental framework;
-   RUP is an elaboration of UP which is owned by IBM;
-   OpenUP, Open Unified Process, is an open-source framework maintained by the Eclipse Foundation;
-   RUP-Op-Maat is an elaboration of RUP and is owned by Ordina;

RUP has four phases which are repeated over and over which ultimately delivers a potentially shippable product incrament:

-   The **I**nception phase:
    -   Scope all the work, initial budget estimates are made;
    -   Align visions;
    -   Identify risks and global planning;
    -   Define acceptance criteria which are testable;
    -   Produces the following artifacts:
        -   Vision;
        -   Risk list;
        -   Use Case Model;
        -   Acceptance Plan;
        -   Global Software Development Plan (SDP);
-   The **E**laboration phase:
    -   Prove the technical feasibility and validate the architecture;
    -   Create a design/proof-of-concept;
    -   Produces the following artifacts:
        -   PoC;
        -   Complete Software Development Plan (SDP);
        -   SAD;
        -   Test plan;
        -   Development and testing environment;
-   The **C**onstruction phase:
    -   Focus on implementation;
    -   Do this in iterations/sprints;
-   The **T**ransition phase:
    -   Focus on the deployment;
    -   Hand the product over to maintenance;

Keyword: **IECT**

## 4. Software process model: Agile

Agile is seen as an incremental AND iterative process.

Agile development has analysis, design, implementation and testing in every iteration/sprint as opposed to RUP. Every sprint delivers a small product.

Agile uses a conversational approach where requirements are continuously negotiated during development. This way, risks or changes are identified at the start of a sprint which makes their impact minimal.

### 4.1 Agile problems

Agile is good in many ways but has a few problems:

-   Difficult to plan the amount of iterations needed;
-   Only works for smaller teams;
-   Requires skilled people as every team member has many roles;
-   Development is intense as the need to complete each feature within the corresponding iteration is pressuring;
-   Active client/user involvement is required which means they need to be available during the project and which means the developers must comply and adapt to a change of culture;
-   Risks lie with the customers as a fixed price tender is not possible;
-   Product owner must manage the interests of the different stakeholders as they'll be tempted to keep demanding new functionality;
-   Quality might lack as the product is a moving target with a 'code and fix' approach;
-   Less documentation as 'the code' = 'the design'. This results in a slow start for newcomers, inefficient maintenance when there's a problem and a loss of the big picture;

### 4.2 Scrum framework

Scrum is a framework for organizing and managing work. It has a limited scope where the focus lies on self-organization of teams. The word **framework** means that you have to adapt Scrum to your specific situation, which results in a version of Scrum that is uniquely yours.

The word Scrum comes from the comparison with playing rugby. In rugby the whole team takes the ball forward, they scrum, as opposed to a relay race where a baton is passed on from player to player which is defined as waterfall.

Scrum, unlike RUP, doesn't say how to do:

-   The requirements analysis;
-   The business alignment;
-   The project planning;
-   The cost estimation;
-   The definition of scope;
-   How to put together a team;
-   The architecture;
-   The definition of the first sprint;

Also, Scrum doesn't have an ending, you either continue with the next sprint or stop the iteration.

#### 4.2.1 Scrum pros and cons

Scrum has a few pros:

-   Scrum, like any Agile framework, creates accountability;
-   Has a clear definition of results;
-   Supports a change of plans due to constant renegotiation;
-   Allows for immediate feedback;
-   Has a focus on the business value with an efficient use of time and money;

Scrum also has a few cons, which are listed in the Agile problems in chapter 4.1.

#### 4.2.2 Scrum roles

Scrum defines a few roles:

-   The product owner:
    -   Collaborates with the stakeholders;
    -   Relays to the development team;
    -   Defines and is responsible for the **product backlog**:
        -   Defines the project scope;
        -   Explains which features and functionality to build;
        -   Defines priority for each feature;
    -   Determines a release date and the content in that release;
    -   Adjusts features and priority in every iteration as fit;
    -   Accepts or rejects work results;
-   The Scrum master:
    -   Responsible for enacting the Scrum values and practices aka the **Scrum ceremonies**;
    -   Helps the team to understand and use self-organization;
    -   Removes roadblocks;
    -   Makes the **Scrum ceremonies** efficient and effective;
    -   Shields the team from external interferences;
-   The Scrum team:
    -   A cross-functional collection of programmers, testers, designers, etc;
    -   Available full-time and preferably in the same room;
    -   Are self-organizing in the sense that no titles are given;

#### 4.2.3 Scrum ceremonies

Scrum has a few ceremonies that the Scrum master should enforce:

-   The sprint planning:
    -   The product owner submits a set of features that are collected into a prioritzed list (**the product backlog**);
    -   The team selects items from the product backlog they believe they can commit to completing (**the sprint backlog**):
        -   User stories can be broken down into tasks;
        -   Tasks are estimated in hours (1-16 hours);
        -   Estimation is done by the whole team collaboratively;
    -   No changes are made during a sprint;
    -   A sprint planning looks like the following:
        -   Define a sprint goal and present the backlog;
        -   Re-prioritize, re-estimate, split or combine stories using cards;
        -   Do a task breakdown (without PO);
        -   Estimate the velocity, draw the line (without PO);
-   The daily standup/daily Scrum meeting:
    -   Takes about 15 minutes;
    -   Shows the Scrum board for an actual status;
    -   Is more about the team's current status as opposed to problem solving:
        -   Everyone's allowed to be present;
        -   Only the team members, Scrum master and product owner can talk;
    -   Helps to avoid other unnecessary meetings;
    -   Everyone answers three questions:
        -   What did I do yesterday?
        -   What will I do today?
        -   Is anything in my way?
-   The sprint demo & review:
    -   The team presents what it accomplished during the sprint;
    -   Typically takes the form of a demo of new features or underlying architecture;
    -   Is informal, prep takes a maximum of 2 hours and uses no slides;
    -   The whole team participates;
    -   Management, customers and developers from other projects are invited;
    -   The team only demonstrates tested usable pieces of code/software as they're completed stories on the **sprint backlog**;
-   The sprint retrospective:
    -   A separate meeting for the Scrum team only;
    -   The process is inspected and adapted where fit;
    -   Typically done after every sprint of 1~2 weeks;
    -   Discusses what is and isn't working;
    -   Takes about 15~30 minutes;
    -   Focus on a few improvements per sprint;

#### 4.2.4 Scrum artifacts

The Scrum framework produces a few artifacts:

-   Product backlog:
    -   Prioritizes items on priority;
    -   Top items are small and detailed so they can be moved to the next sprint;
    -   Bottom items are big and have few details, they need to be iterated on;
    -   As Agile is a **conversational approach** the product backlog items are refined through a series of conversations with stakeholders, the PO and developers;
    -   The product backlog consists of users stories that presents a small use case in the form of a user story: "As a X, I want to Y, so that I can Z";
    -   Each item in the product backlog has a number of story points that indicate a certain complexity, represented by the Fibonacci sequence for example;
    -   Story point estimation is done using planning poker:
        -   Estimates are done by the people who're going to do the work, but all team members attend;
        -   Different viewpoints will be discussed and result in better estimates;
        -   If a feature/item is deemed to large it has to be split into smaller ones;
        -   A round of planning poker goes as follows:
            -   Moderator reads the description of a user story;
            -   Members ask questions to the product owner;
            -   Each member picks a card that represents his/her estimate in story points;
            -   All members show the cards simultaneously;
            -   A group discussion takes place where the members with highest and lowest numbers explain themselves;
            -   If there's no agreement made another round takes place;
-   Sprint backlog:
    -   Has a sprint goal which is a short statement of what the work will be focuses on during the sprint;
    -   Is a snapshot of stories from the product backlog;
-   Sprint burndown chart: A chart that is displays the amount of story points finished on each day;

## 5. Requirements

A requirement is a single sentence that describes what the project should be able to do. This requirements pertains to behaviour, a challenge or a characteristic. It descibes the need of a stakeholder.
An example would be: "A customer should be able to pay with their credit card."
Requirements should be testable.

There are also certain things that are not requirements, such as: "The project has to be done using Agile." or "The amount of team members working on the project is limited to four people." or "Authentication should be possible using password and sms-codes."

Requirements pertain to the need of a user in relation to the product/application. So these are NOT requirements:

-   Demands regarding the development process;
-   Architecture or design choices (= A decision about how requirements should be realized);
-   Business rules;

### 5.1 The importance of requirements

Requirements form the foundation for:

-   Cost indication;
-   Planning;
-   Architecture and design;
-   Testing and acceptance;

Issues during the requirements process are the most important ones to rectify.

### 5.2 Root cause of incomplete requirements

-   Too little attention for the requirements analysis, jump the gun on development;
-   Lack of involvement of management and/or users;
-   A scope that isn't clear or that is too dynamic;
-   Stakeholders who don't communicate with each other;
-   Non-functional requirements that are not specific enough leading to bad architecture choices;
-   Requirements change but the change management process isn't in order

### 5.3 Why it is difficult to draw up requirements

-   Big IT systems are very complex;
-   There are many different stakeholder (groups) with different interests;
-   Stakeholders have unconscious expectations that they don't specify;
-   Priority, the difference between nice-to-have and cricial functionality, isn't clear;
-   The final solution is difficult to imagine:
-   Requirements might change over time;

### 5.4 The different types of requirements

-   **Functional**: What should the system do from the perspective of the stakeholders/users?
-   **Non-functional**: Conditions that apply to the way functionality is delivered.
    -   Availability and stability;
    -   Security;
    -   Performance, efficiency and scalability regarding reponse times, resource usage and concurrency;
    -   Adaptibility / expendability;
    -   Accessibility, friendliness to handicaps;
    -   Requirements regarding management: How does the system start? How do we monitor the system? How do we manage it?;
    -   Look and feel, does it attract users?;
    -   Requirements regarding laws and regulation;
-   **Constraint**: Constraints in the realization of the design.
    -   They constrain the space that developers have to realize a requirement;
    -   They could be constraints regarding OS, framework, API, programming language or database for example;
    -   They might also be constraints regarding time or budget;

### 5.5 The levels that requirements can have

-   **B**usiness requirements:
    -   Answer the why question;
    -   What an organization wants to accomplish with a certain system/product;
    -   Determines the scope and direction of the user requirements;
-   **U**ser requirements:
    -   From the view of the user;
    -   Describes what is delivered to the user;
    -   In a language that the user understands;
-   **S**ystem requirements:
    -   From the view of a developer:
        -   Technical solutions;
        -   Example: "Should comply with RFC 2131 (DHCP)";
        -   Example: "Authentication using LDAP";
    -   In a language that developers understand;
    -   Have a relation to one or more user requirements;

Keyword: **BUS**

### 5.6 What a business rule is

A business rule describes actions, definitions and handicaps that an organization establishes in order to reach their goals. A business rule comes forth from company policy, the law or from branch standards. They are indipendant from products and systems but they do determine them.

Take a look at the following examples:

-   At the customer intake a credit check doesn't take place;
-   Customers with payment due are placed onto a blacklist;
-   Students get 10% off;
-   The purchasing department has to use a list of suppliers that the company provides them with;

### 5.7 How you gather requirements

Gathering requirements is a circular process:

1. A scope is determined using the business rules;
2. An interview with the stakeholders is held in order to get requirements that fit in the initial scope (artifact: **Context diagram**);
3. Determine the goal by describing the requirements and verify this using the scope;

Keep in mind: Stakeholders have their own needs and requirements. Sometimes these requirements clash with those of other stakeholders. Also, stakeholders use their own vocabulary/terminology, make sure you don't duplicate requirements.

Instead of an interview with the stakeholders as mentioned in step 2 you might also:

-   Hold a workshop;
-   Brainstorm with stakeholders;
-   Study existing documentation;
-   Send out questionnaires;
-   Analyze the existing situation;
-   Iterate on prototypes/mock-ups (mostly used with an Agile approach);

#### 5.7.1 The context diagram

A context diagram consists of systems and end-users. A context diagram maps the product being realized to other processes and end users that can utilize the product.

Say you're developing a hotel booking system:

-   Reception:
    -   Can request receipts (out);
    -   Can check people in and out (in);
-   Hotel guest:
    -   Can reserve a room in the hotel (in);
    -   Receives a receipt (out);

### 5.8 How to prioritize requirements

A few factors are key to proiritization:

-   The business value;
-   The effort/complexity;
-   The certainty it is plausible;

A popular method to prioritize requirements is called MoSCoW:

-   **M**ust have:
    -   Non-negotiatable;
    -   Present in the Minimal Viable Product (MVP);
    -   Unable to deliver the end product without this;
    -   Not legal without it;
    -   Unsafe without it;
    -   Not viable without it;
-   **S**hould have:
    -   Important but not vital;
    -   Maybe painful to leave out but the product is still viable;
    -   May need some kind of workaround;
-   **C**ould have:
    -   Desirable but not as important as Should haves;
    -   Only useful if there is extra time and budget;
-   **W**ould have:
    -   Won't have this time around at all;
    -   Out of budget;
    -   Nice to have but doesn't have an impact;

The MoSCoW analyzed requirements can then be grouped into smaller parts using the walking skeleton method. Requirements are ordered from high priority to low. Priority is determined by asking yourself: _"Is this requirement needed for the smaller system in order for it to work?"_

A different method to order the MoSCoW analyzed requirements opposed to the walking skeleton method is the RICE method: **RICE = Reach \* Impact \* Confidence / Effort**.

-   Reach is measured in the number of people (per month) using the requirement;
-   Impact is the measured from 0 to 3;
-   Confidence is measured from 0 to 1 or 0% to 100%;
-   Effort is the number of weeks or days needed for the requirement to be developed;

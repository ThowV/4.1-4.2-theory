# Software Architecture

## 1. Types of architecture

There are numerous types of architectures:

-   Infrastructure;
-   Security;
-   CPU;
-   Technical;
-   Solution;
-   Etc.

In this document we'll mostly focus on the architecture of applications. Application architecture has a few architects to take note of:

-   Enterprise architect (**organizational scope**):

    -   Business/IT alignment;
    -   Enterprise IT planning;
    -   People processes and information to realize business goals;
    -   Is structured by 4 layers:
        -   **Business**: Processes and activities use ...;
        -   **Data**: Data that must be collected, organized, safeguarded and distributed using ...;
        -   **Application**: Applications such as custom or off-the-shelf software tools that run on ...;
        -   **Technology**: Technology such as computer systems and telephone networks;

-   Solutions architect (**organizational/project scope**):
    -   Focus on designing an overall solution for a client;
    -   Supports program and project managers in the design, planning and governance of IT-projects;
-   Security architect (**project scope**):
    -   Implement organizations security goals and policy;
-   Information architect (**project scope**):
    -   Makes information available to applications;
    -   Organization-wide data models;

There are a few frameworks for structuring an enterprise architecture with the goal of giving the user a broad insight into the many business processes:

-   Zachman (1987)
-   TOGAF (1995)
-   FEAF (1999)
-   TEAF (2000)
-   DOD AF (2003)
-   And many more minor frameworks!

## 2. Building vs software architecture

What are the differences between the architect roles in building/construction and software development?

| Building architecture                                                                                                                          | Software architecture                                                                                                 |
| ---------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Architect represents client, and serves as an interface between client and constructors.                                                       | Architect is usually employes by software developer and can therefore not act as a true representative of a customer. |
| Architect creates multiple views (different stakeholders) for sub-contractors to build their piece of the total building.                      | Same                                                                                                                  |
| Goal is to fulfil stakeholder needs in the most elegant manner.                                                                                | Same                                                                                                                  |
| Architect prepares an outline which becomes the guide for the builders to follow during construction.                                          | Role of the architect is not so clear.                                                                                |
| Architect must obtain permission by building authorities.                                                                                      | No permission required.                                                                                               |
| Supervising during the building phase: Architect monitors the work of all contractors to verify that they are using the appropriate materials. | Role of the architect is not so clear.                                                                                |
| Construction work is done by external labor.                                                                                                   | Software architect is usually part of the development team.                                                           |
| Architect prepares scale models of building project.                                                                                           | May provide PoC to prove technical feasibility.                                                                       |
| Buildings are visible.                                                                                                                         | Software is invisible and needs to be demonstrated.                                                                   |
| Buildings are static.                                                                                                                          | Software is dynamic.                                                                                                  |
| Building materials are not flexible.                                                                                                           | Software is extremely flexible.                                                                                       |
| Maintenance does not include new functionality, durability means capability to withstand change.                                               | Durability means capability to adapt change (evolutions or extensibility).                                            |
| Many types of buildings and domains.                                                                                                           | Same                                                                                                                  |
| Architect can use and rely on many quality standards.                                                                                          | Few quality standards are available.                                                                                  |

What is the role of the software architect?

-   Identify and engage stakeholders;
-   Understand and capture stakeholders' concern;
-   Create and take ownership of the definition of an architecture that addresses these concerns;
-   Understand the environment that the software is being built for;
-   Take a leading role in the realization of the architecture into a physical product or system;

## 3. What is (application/software) architecture

How to we define software architecture? Software architecture aims to:

-   Satisfy high-priority requirements;
-   Satisfy quality requirements;
-   Define components and interfaces;
-   Define how to implement components;

All of this results into requirements being made into implemantions. In other words:

> Architecture is about structure and vision.
>
> -- <cite>Simon Brown</cite>

> Architecture represents the significant decisions that shape the system, where significance is measured by cost of change.
>
> -- <cite>Grady Booch</cite>

-   Applications are a social construction:
    -   A body of code that's seen by developers as a single unit;
    -   A group of functionality that business customers see as a single unit;
-   Developers have a shared understanding (big picture) which is called architecture:
    -   How the system is divided into components and how components interact through interfaces;
-   Architecture is a 'social construct':
    -   Whether something is part of the architecture is entirely based on whether the developers think it is important.
-   Architecture is about things that developers perceive as hard to change;
-   A good architecture allows adding featur4es with less effort, time and cost;

## 4. Why do architecture

-   Manage complexity;
-   Avoid duplication (of functionality/code);
-   Creates a shared understanding of 'the big picture':
    -   A basis for further design and implementation;
    -   Align stakeholders and developers;
-   An architecture is a framework for evaluating requirements:
    -   Resolve conflicting requirements -> tradeoffs;
    -   What-if analysis;
    -   Emphasis is on system's quality attributes (non functional requirements).

Requirements desire architecture. Architecture influences requirements:

-   Requirements are an input to architecture:
    -   Requirements frame the architectural problem;
    -   You don't need all the requirements: Focus on **architecturally significant requirements** (ASR's);
-   Architecture will influence requirements:
    -   Stakeholders will understand risk/cost;
    -   Stakeholders will understand the possibilities;

## 5. Agile & architecture

-   Agile requires no big design up-front, but just enough for the things that are expensive to modify later;
-   Collective ownership: Every team member is an architect;
-   But Agile projects need architecture too:
    -   Structure and vision;
    -   Quantifying risks;
    -   Dealing with complex non-functional requirements and constraints;

## 6. Importance of stakeholders

-   Identifying stakeholders:
    -   Those who have an interest in concerns about the realization of the system;
    -   Or those who have money...;
-   Importance of stakeholders:
    -   Architectures are built for stakeholders;
    -   Decisions must reflect stakeholder needs;
-   The challange of stakeholders:
    -   Different stakeholders will have different concerns;
    -   These requirements will often conflict with each other and the budget;
    -   Stakeholders will 'speak a different language';

## 7. The Software Architecture Document (SAD)

A Software Architecture Document (SAD) is a set of products which documents an architecture in a way that is understandable for stakeholders. It demonstrates that the architecture has met their concerns (requirements).

Creating a SAD has its challenges:

-   Different stakeholders need different things from the SAD;
-   You never have enough time to fully document the architecture;
-   You have to leave some areas undefined or vaguely defined without losing credibility;
-   The SAD needs to capture design decisions and the rationale clearly without confusing readers with options;
-   Some stakeholders are very knowledgeable, others are not;
-   How much detail should you put in the SAD?;
-   You need a "sales and marketing" document to convince stakeholders of your architecture's viability, fitness for purpose and cost-effectiveness;
-   The SAD needs to be sufficiently detailed to unequivocally answer all the important decisions;
-   You have to explain "why" and "so what" as well as just "what";
-   At what point does the SAD become a design? Does that matter?;

In order to cover these challenges you must include multiple abstraction layers. A checklist is available (R&W):

-   [ x ] Are all requirements documented?;
-   [ x ] Are all key architectural decisions documented?;
-   [ x ] Are all viewpoints from the chosen **viewpoint set** documented?
-   [ x ] Does the SAD have the right abstraction level, given the skills of your stakeholders? In other words: Will it not confuse the stakeholders upon reading?;
-   [ x ] Does the section of the SAD aimed at non-technical audiences avoid the use of technical jargon?;
-   [ x ] Do you know how the SAD will be maintained?;
-   [ x ] Have you provided a glossary of terms?;
-   [ x ] Are there any issues requiring management attention?;

## 8. Views and viewpoints

Archictecture is about defining structures, not one, but many!:

-   Functional structure: How does the application work?;
-   Information structure: How does information flow through the application?;
-   Process/concurrency structure: Synchronization, data sharing problems etc;
-   Implementation structure: What frameworks/libraries are used?;

An example of viewpoints would be the different views of a house as it's built:

-   The salesperson wants a pretty picture where the house is finished;
-   The electrician wants a map of all cables etc;
-   The plumber wants a map of all pipes;
-   The builders wants a blueprint with all measurements included;

A view is a representation of the whole system, as seen by specific stakeholders who have specific concerns. By using multiple views we can explain to the different stakeholders how their concerns are met. Therefore views solve the problem that it is not possible to capture all the functional features (and quality properties) in a single model;

One view, also known as viewpoint set, consists of one or more viewpoints/models (diagrams, most common: UML) that represent it.

A viewpoint set consists of multiple views. There are many standard viewpoint sets, a few of which are listed here:

-   RUP 4+1;
-   Rozanski & Woods (R&W);
-   RM-ODP (ISO);
-   SEI (CMU);
-   Siemens;
-   Garland & Anthony;

This document will further explain RUP 4+1 and Rozanski & Woods (which is an extension of RUP 4+1).

### 8.1 Architectural models

A model is an abstract, simplified or partial representation of some aspects of an architecture. The purpose of a model is communicatie key structural or behavioral elements of the architecture to one or more stakeholders. A good model is just good enough to achieve the purpose for which you have created it.

We mostly use sketches as, qualititve, models: Informal graphic diagrams. Stakeholders don't like to use quantitative models with a lot of data in them.

A modeling specification often used to create views is called UML, which stands for Unified Modeling Language:

-   As sketch:
    -   Informal;
    -   Focus on main aspects;
    -   Whiteboard or paper;
-   As design:
    -   As a blueprint for developers;
    -   Completeness and unambiguousness are impotent, a lot of details;
    -   Use of specialized CASE tools;
-   As a programming language:
    -   Generate code from a CASE tool;
    -   MDA: Model Driven Architecture;

There are 2 kinds of UML diagrams:

-   Structural diagram: Structure only, time playes no role.
    -   Profile digram;
    -   Class diagram;
    -   Composite structure diagram;
    -   Component diagram;
    -   Deployment diagram;
    -   Object diagram;
    -   Package diagram;
-   Behavior diagram: Time plays a role.
    -   Activity diagram;
    -   Interaction diagram:
        -   Sequence diagram;
        -   Communication diagram;
        -   Interaction overview diagram;
        -   Timing diagram;
    -   Use case diagram: Exception, time playes no role here;
    -   State machine diagram;

These diagrams give answers to the following questions:

-   Which modules and interfaces does the application consist of?
-   What dependencies does component X have?
-   Are there layers within the modules?
-   Are there threads or processes that need to be synchronized?
-   How are the data-entities related?
-   How are the modules and interfaces implemented, by what means?
-   On what hardware is the application deployed and what does the deployment environmentlook like?

### 8.2 C4 model

A viewpoint can be described as any of the 4 abstraction levels:

-   Context (level 1):
    -   Describes the context of the application: Web app, mobile app, database, file system;
    -   Typically by using a context diagram (so not UML);
    -   Explains interactions between different actors;
-   Container (level 2):
    -   An independent runnable/deployable part of the application.
    -   Documents the major technologies used and how the containers communicate;
-   Component (level 3):
    -   Describes the components inside a container and what each of those components are, their responsibilities and the technology/implementation details;
-   Code (level 4):
    -   Describes the code structure inside a component.
    -   Typically using class, sequence or activity diagrams;

Keyword: **C4**

### 8.3 RUP/Kruchten 4+1 viewpoint set

|                   |                        |                          |
| ----------------- | ---------------------- | ------------------------ |
| Logical Viewpoint |                        | Implementation Viewpoint |
|                   | **Use-Case Viewpoint** |                          |
| Process Viewpoint |                        | Deployment Viewpoint     |

RUP 4+1 consists of 4 viewpoints + the **Use-Case Viewpoint**. The Use-Case Viewpoint is the base view and describes the use cases. These use cases are also known as functional scenario's and should cover all functional requirements using:

-   Use Case Diagram(s);
-   Use Case Descriptions;

With the Use-Case Viewpoint as the base we can build upon this using the other 4 viewpoints. The first being the Logical Viewpoint.

Keyword: **LPDIU**

#### 8.3.1 Use-Case Viewpoint

Describes key functional scenarios, use cases, that drive the discovery, design and valdiation of the architecture using:

-   Use Case diagrams;
-   Use Case descriptions;

#### 8.3.2 Logical Viewpoint

The Logical Viewpoint:

-   Describes the functional structure and behavior of the system;
-   Shows how the system will perform the functional scenario's;
-   Fundamental pieces: Subsystems, components, dependencies and interfaces:
    -   Component Diagram (UML);
    -   Boxes-and-lines Diagram (informal);
-   Use case realizations: Describe behavior by using sequence diagrams;
-   More details:
    -   Class Digram;
    -   ERD;

An example of a Logical Component Diagram would look like:

![](https://c4model.com/img/bigbankplc-Components.png)

Logical differs from physical architecture:

-   Logical architecture: Abstract representation of components and their relations, without further specifying implementation, technology or enviroment;
-   Physical architecture: Gives enough detail to decide what's the best technology (software, hardware, network) and may refer to implementation as well as deployment;

#### 8.3.3 Implementation Viewpoint

The Implementation Viewpoint describes the organization of the software modules and implementation details:

-   Concerns of developers and testers;
-   Organization of source code, package diagrams;
-   Development environment;
-   Frameworks, libraries, programming languages;
-   Database engine, file structure;
-   Middleware;

#### 8.3.4 Process Viewpoint

The Process Viewpoint is one of the least used viewpoints. It describes:

-   The concurrent structure of the system;
-   How concurrent execution is coordinated and controlled:
    -   Processes & threads and their communication;
    -   Shared resources and synchronization;
    -   Scheduling aspects;

The Process Viewpoint is visualized using any of the following diagrams:

-   Activity diagram;
-   Sequence diagram;
-   State diagram;

#### 8.3.5 Deployment Viewpoint

The Deployment Viewpoint shows how the run-time entities are mapped on the execution platform. It maps the deployable components onto machines/processors. These deployable components can be any of the following:

-   Hosting environment;
-   Hardware configuration;
-   Network configuration/protocols;
-   Disk storage;
-   ...

### 8.4 Rozanski & Woods (R&W) viewpoint set

The Rozanski & Woods viewpoint set is an expansion of the RUP 4+1 viewpoint set.

First, we map our previously discussed jargon:

| RUP 4+1                  | R&W                         |
| ------------------------ | --------------------------- |
| Use Case Viewpoint       | Context Viewpoint           |
| Process Viewpoint        | Concurrency Viewpoint       |
| Implementation Viewpoint | Development Viewpoint       |
| Deployment Viewpoint     | Deployment Viewpoint        |
|                          | (NEW) Information Viewpoint |
|                          | (NEW) Operational Viewpoint |

#### 8.4.1 Context Viewpoint

The Context Viewpoint maps relationships, dependencies and interactions between the system and its environment. It does so using any of the following diagrams:

-   Context diagram;
-   Swimlane diagram (process model);
-   Use case diagram;
-   User stories;

#### 8.4.2 Information Viewpoint

The Information Viewpoint maps the way that the architecture stores, manipulates, manages and distributes information. It should answer questions around content, structure, ownership, transcation, latency, references and data migration. It also answers the following questions pertaining to data:

-   How to keep data stored in different parts of the system consistent?;
-   Distribution/replication: How to keep information synchronized in multiple places?;
-   How to maintain relations? (partitioning);

It does all of this using an Information Flow Diagram, Entity Relation Diagram or a DFD.

#### 8.4.3 Operational Viewpoint

The Operational Viewpoint maps how the system will be operated, administered and supported in its production environment. It maps how to:

-   Install, upgrade, migrate and back-out;
-   Backup and restore data;
-   Monitor and control:
    -   Error notifications and logging;
    -   Performance monitoring;
-   Respond to problems using a support model;
-   Install configuration and management;

## 9. Architectural perspectives/quality properties

Rozansky & Woods studied many architectures & project cases leading to a systematic approach for defining an architecture: A set of structures (views) and quality properties (perspectives). With this definition a set of guidelines and best practices was created.

Views explain what the system has to do (**functional requirements**). Perspectives define how the system has to do it (**non-functional requirements**). These quality properties are standardized:

-   Functional suitability;
-   Performance efficiency;
-   Compatibility;
-   Usability;
-   Reliability;
-   Security;
-   Maintainability;
-   Portability;

Non-functional requirements are difficult to test. They often have little attention but are crucial to stakeholders:

-   Slow functions don't get used;
-   Unavailable systems cause business interruption;
-   Security problems cause headlines;
-   Unmaintainable systems become irrelevant;

Perspectives are a collection of patterns, templates and guidelines to ensure the system has the right quality properties:

-   A framework based on knowledge and experience;
-   A guide to the architect;

The Rozansky & Woods core set are the most important quality qualities:

-   Performance and scalability;
-   Security;
-   Availability and Resilience;
-   Evolution;

Perspectives are described as followed:

-   **Desired quality**: Definition;
-   **Applicability** to views: Which of your views are most likely to be impacted by applying the perspective;
-   **Concerns**: Thtat the perspective addresses;
-   **Activities**: How to apply the perspective to your architecture;
-   **Problems and pitfalls**: To be aware of;

You apply perspectives to the architecture to ensure quality properties are acceptable and guide its development.

### 9.1 Tactics

An architectural tactic is an established approach or solution you can use to achieve a particular quality property:

-   Redundancy increases availability;
-   Asynchronous processing increases performance;
-   Granting the least amount of privilige increases security;

How to apply tactics:

-   Identify the relevant risks;
-   Evaluate pros and cons for implementing the key drivers;
-   Evaluate their co-operation (contradiction?);
-   Make design decisions;

### 9.2 The Rozansky & Woods Core perspectives

This chapter is about the core perspectives/quality properties mentioned above.

-   Performance and scalability:
    -   Concerns: Response time, throughput, scalability, predictability, hardware resource requirements and peak load behaviour;
    -   Activities:
        -   Capture the performance requirements: For example, response times, throughput and scalability;
        -   Create performance models:
            -   What are the key performance metrics?
            -   What are the performance bottlenecks?
            -   Models: Calculations, statistics, simulations;
        -   Analyze these models: Collect performance data;
        -   Conduct practical testing;
        -   Assess against the requirements;
        -   Rework architecture;
-   Security:
    -   Concerns: Resources, principals, policies, threats, confidentiality, integrity, availability, accountability, detection, recovery and security mechanisms;
    -   Activities:
        -   Identify sensitive resources: For example, data in the database;
        -   Define the security policy (ACP: Access Plan): Who will be trusted, with what access to the system resources;
        -   Identify security threats:
            -   Operators stealing backups;
            -   Admins querying data, seeing names;
            -   Bribing investigating officers;
            -   Internal attack on the database via network;
        -   Design the security implementation:
            -   Backups: Encrypt data in the database;
            -   Bribery: Add audit trail for data access;
            -   Network attacks: Harden database, firewall, IDS;
            -   Consequences: More complexity, bad for performance and more operational costs;
        -   Assess the security risks;
-   Availability and Resilience:
    -   Concerns: Classes of service, planned unplanned downtime, MTBF (Mean Time Between Failure), MTTR (Mean Time To Repair), disaster recovery;
    -   Activities:
        -   Capture the availability requirements;
        -   Produce the availability schedule;
        -   Estimate platform and functional availability;
        -   Assess against the requirements;
        -   Rework architecture;
-   Evolution:
    -   Concerns: Product management, maginitude of change, dimensions of change, likelihood of change, timescale for change, development of complexity, preservation of knowledge, reliability of change;
    -   Activities:
        -   Characterize the evolution needs;
        -   Assess the current ease of evolution;
        -   Consider evolution tradeoffs;
        -   Rework the architecture;

### 9.3 Applying perspectives to views

Which perspectives would help you to achieve your quality properties?

**Architectural tactic**: An established approach or solution you can use to achieve a particular quality property;

**Architectural pattern (or style)**: Often implements multiple architectural tactics, usually related to different qualities in a coherent way. Think of design patterns such as MVC;

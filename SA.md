# Software Architecture

## 1. Types of architecture

There are numerous types of architecture:

-   Infrastructure;
-   Security;
-   CPU;
-   Technical;
-   Solution;
-   Etc.

In this document we'll mostly focus on the architecture of applications. A few architects in application architecture are:

-   Enterprise architect (**organizational scope**):

    -   Business/IT alignment;
    -   Enterprise IT planning;
    -   People processes and information to realize business goals;
    -   Is structured by 4 layers:
        -   **Business**: Processes and activities use...;
        -   **Data**: Data that must be collected, organized, safeguarded and distributed using...;
        -   **Application**: Applications such as custom or off-the-shelf software tools that run on ...;
        -   **Technology**: Technology such as computer system and telephone networks;

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
> b
> Martin Fowler has a broader vision of software architecture:

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

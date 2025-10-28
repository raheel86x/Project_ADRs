# Architectural Style Decision for Complaint Management System

## Context and Problem Statement

ABC Limited requires a scalable yet maintainable architecture for their Complaint Management System (CMS), which will serve large banking and telecom clients. The challenge is to choose an architectural style that can be developed quickly for the proof of concept while still being able to provide a structure that supports future scalability and feature expansions, such as a chatbot integration.

## Considered Options

* Layered / Three-tier Architecture
* Modular Monolithic Architecture
* Microservices Architecture

## Decision Outcome

Chosen option: "Modular Monolithic Architecture", because it provides a balanced approcach between simplicity and scalability. It allows the CMS to be developed as a single deployable application while keeping modules such as complaints, users, and notifications logically seperated. Modular Monolothic Architecture makes it easier to build the proof of concept while leaving room for future growth to a style which is better suited to large-scale systems like microservices architectural style if needed.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

Good, because:
* Encapsulate Business Logic - Business logic is encapuslated within individual modules. Enables high reusability, while data remains consistent and communication patterns simple.
* Reusable Code, easy to refactor - Modular components can be reused. This leads to faster and more consistent development. Also changing a module has no effect on other modules.
* Easier to build and deploy compared to a high-scale structure such as Microservice - Modular monolith is managed as a single application, which means there's no need to maintain multiple services or containers. This makes development and deployment faster and less error-prone.
* Can evolve into a Microservice structure later - Since modules are already seperated, each can be extracted and deployed independently in the future if higher scalability is required.

Bad, because:
* Still a single deployed unit - The entire system would have to be redeployed when any part changes. If a module fails or causes an error, it can affect the availability of the whole application.
* Can't scale and deploy independently - Since the application is a single unit (monolithic), the application as a whole can be scaled but individual modules can't. This could cause issues if certain parts of the system experience higher traffic than others.

## References

Template - https://github.com/adr/madr/blob/4.0.0/template/adr-template-minimal.md

Modular Monolothic Architecture - https://medium.com/design-microservices-architecture-with-patterns/microservices-killer-modular-monolithic-architecture-ac83814f6862

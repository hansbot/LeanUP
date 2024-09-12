# Architecture Plan

```text
> First post : 26 June 2024
> Last edit : 13 August 2024
```

The Architecture Plan defines the essential guardrails for design and development of API Platforms and Products. The plan drives the synergy across a portfolio of products.

## 1. Scope and Viewpoints

The Architecture Plan has a clearly defined scope along the lines of organisation (value chains, departments, market), business processes (horizontal and vertical) and technology (systems and services, clouds and platforms, development and operations).

Key Viewpoints include

- Governance
- Design
- Engineering
- Service Management
- Security

## 2. Architecture Principles

Architecture Principles represent meaningful choices that shape the decisions during product design and engineering. Having an unbounded decision space is generally paralysing decision making. It tends to lead to disparate outcomes, which may prove difficult to integrate. Architecture principles constrain the design space, act as guardrails in decision making. It’s not a cookbook, however, different architects will still come to different designs, which is okay.

Contrast principles to best practices. There can be only one ‘best’ practice for everyone. Principles, however, may be adopted selectively. It’s self-evident.

Architectural principles, once successfully adopted across an enterprise, are difficult to change. It is engrained in the culture of the organization. For instance, if you adopt an event-driven architecture style –which in itself represents a coherent set of architecture principles– because real-time data synchronisation is important in a certain domain, it's quite common to adopt it also where it is not technically required, but doesn't hurt either. Harmonization creates strong architectures.

These are the 5 criteria for an Architecture Principle.

| # | Property | Explanation | Example |
|-|-|-|-|
| 1. | An imperative statement | Stated as a directive, the architecture principle leaves no room for doubt. | All service interfaces, without exception, must be designed from the ground up to be externalizable. \[i\] |
| 2. | Debatable | A stated architecture principle is valuable if only it represents a deliberate choice. It doesn't state the obvious. Typically, the opposite statement could also be a useful principle. | Data must always be consistent</BR>versus</BR>Data must be consistent eventually |
| 3. | Represents an important choice | If a choice is not meaningful, it does not qualify as an architectural principle. | We respect Laws of Nature only. |
| 4. | Relevance | Architectural principles are 'so what?' proof | ~~Integration middleware must be used only when needed~~ \[ii\] |
| 5. | Actionable | An architecture principle helps decide the trade-offs during design and engineering. | Move fast and break things |

## 3. Target Architecture & Domain Model

There are many ways to design a target architecture. The [Novius framework](/LeanUP/References/novius.md) is a useful reference for structuring your target architecture.

[Domain Drive Design](https://en.wikipedia.org/wiki/Domain-driven_design) gives useful guidance on how to design a Domain Model, for instance using "Event Storming".

## 4. Architectural Standards and Guidelines

Unlike Architecture Principles, Architectural Standards and Guidelines typically have a limited scope and are subject to frequent changes. Where the Architecture Principle may be enforcing an Event-Driven Architecture, [CloudEvents v1.0.2](https://github.com/cloudevents/spec) may be a standard to embrace, while a UUID may be the guideline for the ID of the event. Principles are mostly defined top-down, whereas standards and guidelines are more a bottom-up process by and for practitioners.

There should be a community process to adopt and revise a standard.

Standards and guidelines are typically enforced through social pressure among developers, mostly during peer review.

## 5. Architecture Roadmap

Whether you believe in emergent design or not, having some form of shared application infrastructure is always part of the deal. Think of an Identity Provider, an API Developer Portal, an Event Broker, and a Collaboration Suite. Sometimes those are thought of as addressing cross-cutting concerns, other times those are thought of as the supporting Digital Assets. Rarely, those are recognized as separate Product Domains, having their own dedicated teams. Mostly, organizations use off-the-shelf systems for implementation, or procure those systems as a service.

The Architecture Roadmap ensures the sustained fitness of these components to suit the needs of the (other) Product teams.

| *License* | Navigate |
| - | - |
|Common Criteria</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/LeanUP/Images/leanupLogo-s.png)](/LeanUP/Artefacts/overview.md) |

i: From [the API Mandate](/LeanUP/References/api-mandate.md)

ii: From [Reference Architecture](https://www.referentiearchitectuur.nl/index.php/Id-bddb73b5-1e16-55ec-6769-881acf7e4b78) \(in Dutch\)

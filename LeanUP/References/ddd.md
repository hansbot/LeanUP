# Domain-Driven Design

Domain-driven Design (DDD) is a structure method, developed by Eric Evans and popularized by Vaughn Vernon, to separate a diverse problem domain into coherent solution domains. DDD defines a couple of key concepts.

## Concept 1: Bounded Contexts

Today, many organizations have organized their digital efforts around product teams, famously nourished by a limited number of pizza's. Perhaps you've wondered how these teams got defined in this way. Domain-driven Design gives a structured approach to design the product domains, and by than, scope the responsibilities of the product teams.

One of the core ideas is that, when contexts are well-bounded, teams can be pretty independent in the way they work, what technology they use, and when they deploy their updates. Each domain runs its own, independent domain model.

![Integration in Domain-Driven Design](/LeanUP/Images/ddd.png)

## Concept 2: Ubuquitous Language

Speaking your own language is part of being independent. In DDD, the ubiquitous language is the well-defined, common lingo inside the domain. There is no effort into standardizing the language across domains.

## Concept 3: Anti-Corruption Layer

Having your own language comes at the cost of translation. In DDD, these translations are isolated from the domain core in something called the anti-corruption layer. This layer helps to keep the domain pure. It serves to translate both inbound and outbound interactions. It also serves to sanitize and neutralize invalid requests, be it malicious or otherwise.

## Concept 4: Context Mapping

A context map represents a translation between two different *ubiquitous languages*. DDD distinguishes different kinds of mapping.

- A *Partnership* gets created to align two teams with a dependent set of goals (collaboration).
- A *Shared Kernel* represents the intersection of two Bounded Contexts - effectively creating a joint responsibility and an associated joint ubiquitous language. Difficult to maintain.
- A *Customer-Supplier* describes a relationship where the Supplier is upstream. The supplier holds sway because it must provide what the Customer needs.
- A *Conformist* relationship is used when the Supplier has no motivation to support the Customer. Often with SaaS-providers.
- An *Anti-Corruption Layer* is the most defensive Context Mapping relationship. This layer isolates the downstream model from the upstream model.
- An *Open Host Service* defines a protocol or interface that gives access to your Bounded Context as a set of services. The services offered by the API  are well documented and a pleasure to use.
- A *Published Language* is a well-documented information exchange language (XML Schema, JSON Schema) enabling simple consumption and translation by any number of consuming Bounded Contexts.
- *Separate Ways* describes a situation where integration with another Bounded Context will not produce significant payoff.

## Concept 5: Aggregates

An aggregate is composed of one or more Entities. One entity is the Aggregate Root.

The Root Entity of each Aggregate owns all the other elements clustered inside it. As a general rule: modify and commit no more than one Aggregate instance in one transaction.

### Rules of thumb

- Protect business invariants inside Aggregate boundaries
- Design small Aggregates (Single Responsibility Principle (SRP))
- Reference other Aggregates by identity only
- Update other Aggregates using eventual consistency

### Anti-pattern

One big, nasty hook is the Anemic Domain Model, where Aggregates only have setters and getters, and no business behavior whatsoever. This flies in the face of object-oriented design. In other words, an aggregate should add value, albeit just specific validations, calculations, filters, harmonization, or restrictive access control.

In the API Design world, the BFF, or Backend-for-Frontend pattern, sees to create aggregates tuned to the needs for a single frontend, thus hiding internal complexities. Alternatively, a GraphQL service offers an all-you-can-eat menu, where every frontend is allowed to pick and choose exactly what it needs.

# Design Capability

```text
> First post : 24 June 2024
> Last edit : 1 July 2024
```

## Core Responsibilities

- Standards & Architecture Management
- Stakeholder Alignment
- Interaction Design
- API Specification
- Database Design

## API Design Process

API Design is the core of the LeanUP. After all, having the right APIs at the levels at the right quality not only gives you control over your entire digital product lifecycle, it also empowers your digital value chain. Since an API is at the pivot point between the data in the backend and the user experience in the frontend, good API Design must be aligned with database design and user interaction design.

Furthermore, API Design must be firmly rooted in the overal Architecture. At the same time, API Design is an excellent opportunity to validate and potentially update the overal Architecture, in order to fit changing needs, or put newer technologies to good use.

In the [ADDR process model](/References/addr.md), API Design is a 4-stage process, which maps nicely on [LeanUP][nav].  

## Contribution to LeanUP

| Artefact | Contribution | [Exploration Stage](/Stages/exploration.md) |[Discovery Stage](/Stages/discovery.md) | [Elaboration Stage](/Stages/elaboration.md) | [Delivery Stage](/Stages/delivery.md) |
| ----- | ------------ | - | - | - | - |
| [Architecture Plan](/Artefacts/arch-plan.md) | Manage |  | Optional Update | Optional Update | Optional Update |
| [Information Security Plan](/Artefacts/sec-plan) | Advice |  | Optional Update Recommendation | Optional Update Recommendation | Optional Update Recommendation |
| [Value Opportunity](/Artefacts/val-oppo.md) | Review | Assessment |  |  |  |
| [Value Case](/Artefacts/val-case.md) | Advice |  | Review Initial Version | Review Updated Version |  |
| [API Design](/Artefacts/api-design.md) | Manage | API Style, Boundaries | API Skeleton | API Design | Refined API Design |
| [Development Case](/Artefacts/dev-case.md) | Manage |  | Author Initial Version | Update Initial Version | Maintain |
| [Release Plan](/Artefacts/rel-plan.md) | Advice |  |  | Influence | Influence |
| [Prototype](/Artefacts/pro-review.md) | Advice |  |  |  | Assessment |
| [Product Release](/Artefacts/rel-review.md) | Review |  |  |  | Assessment |
| [Risk List](/Artefacts/risklist.md) | Collaborate | joint effort | joint effort | joint effort | joint effort |
| [Daily compliance](/Artefacts/dailyCompliance.md) | none |  |  |  |  |
| [Monthly compliance](/Artefacts/monthlyCompliance.md) | none |  |  |  |  |
| [Post Mortem][pm] | Review |  |  |  | Assessment |

## Resource Modeling Practice

While creating a resource model for your APIs, you face bridging the worlds of API Engineers with the world of API Consumers. For many different kinds of reasons, there is an inherent impedence mismatch. Engineers think object or data oriented, while interaction designers think from a user perspective. More often than not, at least over time, an API has to serve multiple audiences, requiring subtle changes to the schema. Often, clients require an API, sometimes dubbed as 'experience API', or 'Engagement API', composed out of different microservices, each exposing their own 'System API'.

It is the responsibility of the API Designer to come up with a smart interface design.

There are multiple ways to go about this. Here are three commonly used ones, with some pros and cons.
| # | Approach | Explanation | Pros | Cons |
|- |- |- | -|-|
| 1. | Backend-for-Frontend | Engineering a separate layer of integration microservices as glueware between the system services and the frontends. | Versatile, No additional technology required | At scale, integration can become a bottleneck. Difficult to govern |
| 2. | GraphQL | Engineering a virtual database, trusting clients to use it wisely. | Flexible to use, Complex to build | Additional technology, Hard to change, Difficult to secure |
| 3. | API Virtualization | Running your customization logic on an API Gateway | Single point of Access, Flexible, Easy to manage, Transparent | Additional technology |

To quote Werner Vogels,
> Being conservative and minimalistic in your API design helps you build fundamental tools on which you may be able to add more functionality, or which partners can build layers on top of.

Having a generic base, with a layer of differentiation on top, makes common sense. The API Design Language, be it OpenAPI, or AsyncAPI, facilitates capturing a significant part of this differentation right in the API Specification. This also works for 3rd-party APIs.

Having principles laid down in the [architecture plan](/Artefacts/arch-plan.md), and having technology in place, will help designers make the right choice quickly. Consider having different principles for intra-domain integration and inter-domain integration, but remember that every API must be [exposable to the outside world](/References/api-mandate.md).

| | |
| - | - |
| *License*:</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/images/leanupLogo-s.png)][nav] |

[nav]: /Capabilities/overview.md
[pm]: /Artefacts/post-mortem.md

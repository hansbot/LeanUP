# The LeanUP Model

```text
> First post : 20 June 2024
> Last edit : 12 August 2024
```

Unlike the original [Unified Process][leanup], which is project oriented, the Lean Unified Process, or [LeanUP][leanup], is product oriented. Thereby, it is closer aligned to modern agile frameworks.

LeanUP also aligns with the widespread belief that APIs should be managed as a product throughout their entire lifecycle. Offering an API as an interface to your product assumes you need to arrange for support and interaction with consumers of the interface – both developers, service managers and owners of the client application.

Similar to the original [Unified Process][up], the [LeanUP][leanup] defines 4 distinct increments. known as *stages*. These stages are designed to rapidly drive down risks, and fail early when necessary. Every stage transition is marked by a [milestone](/LeanUP/Overview/milestones.md).

| # | Stage | Purpose | Trigger |
| ----------- | ----------- | ----------- | ----------- |
| 1 | [Exploration](/LeanUP/Stages/exploration.md) | Alignment | [Value Opportunity](/LeanUP/Artefacts/val-oppo.md) |
| 2 | [Discovery](/LeanUP/Stages/discovery.md) | Scoping | [Value Case][valcase] |
| 3 | [Elaboration](/LeanUP/Stages/elaboration.md) | Design | [Development Case][devcase] |
| 4 | [Delivery](/LeanUP/Stages/delivery.md) | Working Software | [Accepted Prototype](/LeanUP/Artefacts/pro-review.md) |

Notice that the [Discovery](/LeanUP/Stages/discovery.md) stage is preceeded by an [Exploration](/LeanUP/Stages/exploration.md) phase. This is an essential addition to the process. It is where the product gets shaped. The Construction and Transition phases have been merged into a single [Delivery](/LeanUP/Stages/delivery.md) phase. This aligns with the Agile way of working, sometimes summarized in the principle "You build it, you run it". It allows for a highly iterative devops approach, resulting in "continuous delivery". It also recognizes that an API is never finished unless the last consumer is retired.

![Model of the LeanUP](/LeanUP/Images/leanup.png)

The "disciplines" in the original are replaced with 6 Core Capabilities.

- [Governance](/LeanUP/Capabilities/governance.md)
- [Product Management](/LeanUP/Capabilities/product-mgt.md)
- [API Design][design]
- [Digital Engineering](/LeanUP/Capabilities/engineering.md)
- [Service Management](/LeanUP/Capabilities/service-mgt.md)
- [Information Security](/LeanUP/Capabilities/security.md)

Notice that the prefix [API](/LeanUP/api.md) in [API Design][design] articulates Leanness of the [LeanUP][leanup] Process. Rather than having a big design upfront, [LeanUP][leanup] focusses on Interfaces, leaving the design of the insides of a bounded context to the engineering discipline. This opens the door for a more informal way of working during the delivery stage. The [LeanUP][leanup] [API Design][design] just sets the guardrails and controls the boundaries – regardless of the API.

Furthermore, the waste of the [LeanUP][leanup] Process is minimized by following the milestone decisioning. The [Value Case][valcase] helps to prioritze the best product development efforts. The [Development Case][devcase] drives the product development risk down, and helps to fail early when needed.

*License*:</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en)

[leanup]: /LeanUP/Overview/leanup.md
[up]: https://en.wikipedia.org/wiki/Unified_process
[design]: /LeanUP/Capabilities/design.md
[valcase]: /LeanUP/Artefacts/val-case.md
[devcase]: /LeanUP/Artefacts/dev-case.md

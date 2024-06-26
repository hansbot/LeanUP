# The LeanUP Model

> First post : 20 June 2024

> Last edit :

Unlike the original [Unified Process][leanup], which is project oriented, the [Lean Unified Process][leanup], or LeanUP, is product oriented. Thereby, it is closer aligned to modern agile frameworks. It also aligns with the widespread belief that APIs should be managed as a product. 

Similar to the original [Unified Process][up], the [LeanUP][leanup] defines 4 distinct increments. known as *stages*. These stages are designed to rapidly drive down risks, and fail early when necessary.

| # | Phase | Purpose | Trigger |
| ----------- | ----------- | ----------- | ----------- |
| 1 | [Exploration](/Stages/exploration.md) | Alignment | [Business Opportunity](/Artefacts/bus-oppo.md) |
| 2 | [Discovery](/Stages/discovery.md) | Scoping | [Business Case](/Artefacts/bus-case.md) |
| 3 | [Elaboration](/Stages/elaboration.md) | Design | [Development Case](/Artefacts/dev-case.md) |
| 4 | [Delivery](/Stages/delivery.md) | Working Software | [Accepted Prototype](/Artefacts/pro-review.md) |

Notice that the [Discovery](/Stages/discovery.md) stage is preceeded by an [Exploration](/Stages/exploration.md) phase. This is an essential addition to the process. It is where the product gets shaped. The Construction and Transition phases have been merged into a single [Delivery](/Stages/delivery.md) phase. This aligns with the Agile way of working, sometimes summarized in the principle "You build it, you run it". It allows for a highly iterative devops approach, resulting in "continuous delivery". It also recognizes that an API is never finished unless the last consumer is retired. 

![Model of the LeanUP](/images/leanup.png)

The "disciplines" in the original are replaced with 6 Core Capabilities. 
- [API Governance](/Capabilities/governance.md)
- [API Ownership](/Capabilities/ownership.md)
- [API Design](/Capabilities/design.md)
- [API Engineering](/Capabilities/engineering.md)
- [API Management](/Capabilities/management.md)
- [API Security](/Capabilities/security.md)

Notice that the prefix [API](/api.md) here defines what makes the process Lean, by focussing on Interfaces rather than the insides of a bounded context. This opens the door for a more informal way of working during the delivery phase. The [LeanUP][leanup] just sets the guardrails and controls the boundaries.

*License*: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en)

[leanup]: /Overview/leanup.md
[up]: https://en.wikipedia.org/wiki/Unified_process
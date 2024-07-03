# The LeanUP Model

```text
> First post : 20 June 2024
> Last edit : 3 July 2024
```

Unlike the original [Unified Process][leanup], which is project oriented, the Lean Unified Process, or [LeanUP][leanup], is product oriented. Thereby, it is closer aligned to modern agile frameworks. It also aligns with the widespread belief that APIs should be managed as a product.

Similar to the original [Unified Process][up], the [LeanUP][leanup] defines 4 distinct increments. known as *stages*. These stages are designed to rapidly drive down risks, and fail early when necessary.

| # | Stage | Purpose | Trigger |
| ----------- | ----------- | ----------- | ----------- |
| 1 | [Exploration](/LeanUP/Stages/exploration.md) | Alignment | [Value Opportunity](/LeanUP/Artefacts/val-oppo.md) |
| 2 | [Discovery](/LeanUP/Stages/discovery.md) | Scoping | [Value Case](/LeanUP/Artefacts/val-case.md) |
| 3 | [Elaboration](/LeanUP/Stages/elaboration.md) | Design | [Development Case](/LeanUP/Artefacts/dev-case.md) |
| 4 | [Delivery](/LeanUP/Stages/delivery.md) | Working Software | [Accepted Prototype](/LeanUP/Artefacts/pro-review.md) |

Notice that the [Discovery](/LeanUP/Stages/discovery.md) stage is preceeded by an [Exploration](/LeanUP/Stages/exploration.md) phase. This is an essential addition to the process. It is where the product gets shaped. The Construction and Transition phases have been merged into a single [Delivery](/LeanUP/Stages/delivery.md) phase. This aligns with the Agile way of working, sometimes summarized in the principle "You build it, you run it". It allows for a highly iterative devops approach, resulting in "continuous delivery". It also recognizes that an API is never finished unless the last consumer is retired.

![Model of the LeanUP](/LeanUP/Images/leanup.png)

The "disciplines" in the original are replaced with 6 Core Capabilities.

- [Governance](/LeanUP/Capabilities/governance.md)
- [Product Management](/LeanUP/Capabilities/product-mgt.md)
- [API Design](/LeanUP/Capabilities/design.md)
- [Digital Engineering](/LeanUP/Capabilities/engineering.md)
- [Service Management](/LeanUP/Capabilities/service-mgt.md)
- [Information Security](/LeanUP/Capabilities/security.md)

Notice that the prefix [API](api.md) here defines what makes the process Lean, by focussing on Interfaces rather than the insides of a bounded context. This opens the door for a more informal way of working during the delivery phase. The [LeanUP][leanup] just sets the guardrails and controls the boundaries.

*License*:</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en)

[leanup]: /LeanUP/Overview/leanup.md
[up]: https://en.wikipedia.org/wiki/Unified_process

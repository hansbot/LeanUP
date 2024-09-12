# Development Case Artefact

```text
> First post : 21 June 2024
> Last edit : 14 August 2024
```

A [Development Case][self] artefact is a milestone document. Acceptance of a baseline version marks the end of the [Discovery stage][disc] and the beginning of the [Elaboration Stage](/LeanUP/Stages/elaboration.md). The case outlines the development plan for the proposed product development, with a strong focus on the definition of the [interfaces](/LeanUP/api.md). It helps to develop things the right way. It compares to a [Solution Intent](https://v5.scaledagileframework.com/solution-intent/), but with a firm focus on [APIs](/LeanUP/api.md).

## Questions to Answer

Every [Value Opportunity][oppo] is different. Hence, the questions that the Product Architect must answer might vary.

This is a list of typical questions that are discussed during the [Discovery Stage][disc]

1. What API(s) do we design for which audience? In what order?
2. How are we going to engage them?
3. What platform are we targeting?
4. What API Style(s) are we providing?
5. What are the interaction cases / events?
6. What information is flowing?
7. What are typical error conditions?
8. What standards do we comply to?
9. How to prove compliance?
10. Who’s contributing what?

Usually, the answers have a certain degree of uncertainty. A proof-of-concept may serve to drive down the risks to the feasibility of the product. It may also serve to more reliably plan the elaboration stage.

## Relation to other Artefacts

- The [Value Case](/LeanUP/Artefacts/val-case.md) sets the objectives for the product development and contains the assumptions for product viability. The [Development Case][self] challenges the assumptions made.
- The [Architecture Plan](/LeanUP/Artefacts/arch-plan.md) sets the guardrails for the [Development Case][self].
- The [Information Security Plan](/LeanUP/Artefacts/sec-plan) defines a standard list of information security controls to consider.
- The [initial API Design](/LeanUP/Artefacts/api-design.md) defines the resources, thereby scoping the APIs involved, and placing them in the resource model. The design of the API sketletons is necessary only when it captures major design decisions.
- The [API Prototype](/LeanUP/Artefacts/pro-review.md) is useful when the feasibility of the product is questionable.

The [Development Case][self] might be used as input for an RFP.

## Feasibility

Determining the feasibility of a [Value Case](/LeanUP/)

| *License* | Navigate |
| - | - |
|Common Criteria</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/LeanUP/Images/leanupLogo-s.png)](/LeanUP/Artefacts/overview.md) |

[oppo]: /LeanUP/Artefacts/val-oppo.md
[disc]: /LeanUP/Stages/discovery.md
[self]: /LeanUP/Artefacts/dev-case.md

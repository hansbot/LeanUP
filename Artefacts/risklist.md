# Risk List Artefact

```text
> First post : 21 June 2024
> Last edit : 21 June 2024
```

A [Risk List][self] is a tool to manage the product development risks. It must be updated at every stage change, at a minimum. Usually, it's a simple table, used to track the progress of risk mitigation. Do not confuse it with the information security risks. When well-managed, those don't turn up on the product development [Risk List][self].

Do refrain from nominating every issue as a risk. A risk is a threat to deliver a committed result that is in need of intervention of a principle to remediate. That's it. Once remediated, or simply accepted by the principle, the risks gets archived.

Anyone can raise a risk, but the risk is only managed when an owner is appointed. The owner will mostly require backing from a principle before accepting the risk.

| Nr | Title | Likelihood | Impact | Severity | Owner | Principle | State | Summary |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Unique Id | Short Description | Scale 1..5 | Scale 1..5 | L*I | The one who committed to the result | The one who is intervening | owned / accepted / remediated | Pinpoint the commitment, the impediment to deliver, the consequence for the product, and a potential mitigation |

As summary, the following template may be used.

```text
> As a risk owner, I am no longer confident to my commitment of ..., 
> because of ..., 
> which might impact budget/timelines/security/feasibility/..., 
> unless ...
```

| | |
| - | - |
| *License*:</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/images/leanupLogo-s.png)][nav] |

[nav]: /Artefacts/overview.md
[self]: /Artefacts/risklist.md

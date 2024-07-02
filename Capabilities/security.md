# Information Security Capability

```text
> First post : 24 June 2024
> Last edit : 26 June 2024
```

## Core Responsibilities

- Risk Assessment
- Security Controls
- Compliance
- Security checking and reporting

## Security Process

A typical security process is a pdca-like continuous improvement cycle. The 4 phases [LeanUP](/Overview/leanup.md) distinguishes are Prevention, Detection, Respons, and Improvement.

| Phase | Activity | Description |
| --- | --- | --- |
| 1. | Prevent | Assessing Risks, Defining Controls and Implementing Information Security Measures is mainly done in the early stages of the LeanUP process. Obviously, the focus is on API Security. This includes, by the way, the security of APIs the Digital Product is only consuming. It also includes implementing a process to implement security patches. |
| 2. | Detect | When you have proper monitoring in place, much of the detection and counter-measures can, and probably should be automated. Nevertheless, it is important to check at least daily if the automated detection is working as expected. Unknown threats may occur at any point in time. Submitting daily and monthly compliance reports is a proven method to build a security routine. |
| 3. | Respond | Having an Incident Respons Plan is one thing, Frequently testing and updating is yet another. The Respons Plan should at least address how to Minimize Loss & Damage, how to Collect and Secure Evidence, how to Safely Recover your Service, how to Communicate Progress and how to Perform a [Post Mortem][pm]. For inspiration, have a look at this [NIST Guide](https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-61r2.pdf). |
| 4. | Improve | Improvements start at analyzing what's going on. Be it legislation, be it cyber threats reports, or simply (near-) informationsecurity events and incidents you've experienced yourself. Improvement potential is captured on a cyber defence backlog, and entered in the regular product release planning |

## Contribution to LeanUP

| Artefact | Contribution | [Exploration Stage](/Stages/exploration.md) |[Discovery Stage](/Stages/discovery.md) | [Elaboration Stage](/Stages/elaboration.md) | [Delivery Stage](/Stages/delivery.md) |
| ----- | ------------ | - | - | - | - |
| [Architecture Plan](/Artefacts/arch-plan.md) | Advice |  | assess update  | assess update  | assess update |
| [Information Security Plan](/Artefacts/sec-plan) | Manage | Optional Plan update | Optional Plan update |  Optional Plan update | Optional Plan update |
| [Value Opportunity](/Artefacts/val-oppo.md) | Define information security risks | Initial risk assessment | Update risk assessment | | |
| [Value Case](/Artefacts/val-case.md) | Define information security controls | | Initial set of controls | Updated set of controls | |
| [API Design](/Artefacts/api-design.md) | Assess | | | Initial API Security Audit | API Security Audit |
| [Development Case](/Artefacts/dev-case.md) | Review | | Initial Set of Security Measures | Updated Set of Security Measures | |
| [Release Plan](/Artefacts/rel-plan.md) | Advice |  |  | assess update | assess update  |
| [Prototype](/Artefacts/pro-review.md) | Review | | | Initial Vulnerability Scan | |
| [Product Release](/Artefacts/rel-review.md) | Advice | | | | API Conformance Scan, Vulnerability Scan |
| [Risk List](/Artefacts/risklist.md) | Collaborate | joint effort | joint effort | joint effort | joint effort |
| [Daily compliance](/Artefacts/dailyCompliance.md) | Manage | | | Specify Daily Security Checks | Daily Compliance Report |
| [Monthly compliance](/Artefacts/monthlyCompliance.md) | Manage |  | | Specify Monthyl Security Checks | Monthly Compliance Report |
| [Post Mortem][pm] | Author report | | | | After major incident |

| | |
| - | - |
| *License*:</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/images/leanupLogo-s.png)][nav] |

[nav]: /Capabilities/overview.md
[pm]: /Artefacts/post-mortem.md

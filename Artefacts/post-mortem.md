# Post-Mortem Artefact

```text
> First post : 26 June 2024
> Last edit : 
```

## Summary

A [Post Mortem][pm] contains an extensive report on the incident or disaster that happened. It also draws lessons and sets recommendations. Importantly, a well-written [Post Mortem][pm] captures the good and the bad. When drawing lessons, the good must be cherished, whereas the bad must be improved.

## Contents

| # | Title | Description |
| - | - | - |
| 1. | Summarize Facts | Capture the bare factuals of what has happened, when it happened, how it was responded to, who contributed, and how and when de service was restored.</BR>Adopt a classification system such as [this](/References/sec-incident.md). |
| 2. | What led up | Often, something triggered the event, such as a change, or an outside event. |
| 3. | Failure details | What caused the failure, and how was it captured in logging and alerting. |
| 4. | Degradation | Who was affected how and for how long? How grave was it? Can we quantify the loss? |
| 5. | Notification | Who got notified first, who set the priority, what was the lead time to respond as prescribed |
| 6. | Follow-up | From first responder an their analysis, a 3rd line support call, to convening the incident respons team, to escalation to a disaster, a respons process can be quite a journey. Was the incident respons plan followed as intended? Typically, this is the area where the improvement potential is the largest. |
| 7. | Recovery | There can be a number of mitigating actions, ranging from replacing failing hardware, restarting a machine, a quick configuration change |
| 8. | Timeline | A list of events over time. Do include the communications that were issued |
| 9. | Root Cause Analysis | Knowing the root cause helps to assess the likelihood of recurrence,  feeds future preventative measures, and helps set their priorities |
| 10. | Recommendations | First, give credit to what went well. Next, define concrete improvements to consider. This includes improvements to the [Incident Recovery Plan](/Artefacts/sec-plan) itself. Substantial improvements should be defined as a [Value Opportunity](/Artefacts/val-oppo.md), and enter the regular improvement process. When urgency is high, however, an emergency fix should be considered. |

| | |
| - | - |
| *License*:</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/images/leanupLogo-s.png)][nav] |

[nav]: /Artefacts/overview.md
[pm]: /Artefacts/post-mortem.md

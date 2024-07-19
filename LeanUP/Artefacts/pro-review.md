# API Prototype

```text
> First post : 24 June 2024
> Last edit : 25 June 2024
```

An [API Prototype Review][self] is a milestone document, marking the end of the [Elaboration Stage](/LeanUP/Stages/elaboration.md) and the beginning of the [Delivery Stage](/LeanUP/Stages/delivery.md). It answers the last remaining feasibility questions. It should be a result of a collaboration by the API Development Team(s) and the (representation of) the API consumer team.

## Questions to Answer

1. What is our API taxonomy?
2. Do we have dependencies?
3. What design patterns do we adopt?
4. What methods to support?
5. What responses to supply?
6. How are these methods scoped?
7. What code samples do we provide?
8. What security schemes do we enforce?
9. How do we define the JSON objects?
10. What feed-back did we get. Any remaining issues?

## API Review

To get an API [Prototype][self] approved, an API Review helps structure the decision process. An API Audit helps to find weaknesses, but the detailed design decisions required to pass such a review, such as regexes and array bounds, are yet te be taken. Here is the LeanUP checklist for such a review.

* **Structure**<br>A well-structured document is easier to understand and to manage. Getting the structure right from the beginning accellerates the development. Doing it at the end is wasteful.<br>If the API Style and Version you've selected supports it, do reference your library of reusable specification fragments.
* **Security Schemes**<br>The Security Scheme defines the required authentication, such as HTTP Basic Authentication, API-Key, TLS-MA, or OAuth Authorization Code Grant flow with PKCE. It must suit the security requirements for the API.
* **Pathnames**<br>Clear and consistent naming is of the utmost importance for the long-term success of an API. The start of the [Delivery Stage](/LeanUP/Stages/delivery.md) is probably the last point in time that a change of naming has a low impact.
  * Operations<br>The operations on the resource collections and resource items should follow the guidelines as set in the [Architecture Plan](/LeanUP/Artefacts/arch-plan.md#4-architectural-standards-and-guidelines).
  * Messages<br>In RESTful APIs, the URI identifies a single message. In AsyncAPIs, however, the URI identifies a channel, and multiple types of message may be transfered over a single channel.
  * Headers<br>Header parameters, such as HTTP Conditions with Entity Tags, should follow the guidelines as set in the [Architecture Plan](/LeanUP/Artefacts/arch-plan#4-architectural-standards-and-guidelines).
* **Components**
  * Schema<br>JSON Schema is a comprehensive vocabulary allowing you to structure, validate, annotate, and manipulate human-readable JSON documents as message bodies. Depending on the API Style, different schema vocabularies may be in use. Importantly, parties on both side of the interface need to agree on the schema design.
  * Responses<br>Response codes capture the failure scenarios being considered. With the API Prototype, typical failure conditions must be agreed in compliance to the guidelines as set in the [Architecture Plan](/LeanUP/Artefacts/arch-plan#4-architectural-standards-and-guidelines).
  * Response Headers<br>Header use, such as HTTP Conditions with Entity Tags, should follow the guidelines as set in the [Architecture Plan](/LeanUP/Artefacts/arch-plan#4-architectural-standards-and-guidelines).
  * Security Definitions<br>The Security Scheme defines the required authentication, such as HTTP Basic Authentication, API-Key, TLS-MA, or OAuth Authorization Code Grant flow with PKCE. It must suit the security requirements for the API. Different schemes may be used for different parts of the API.
  * Webhooks & Callbacks<br>The option for out-of band callbacks and webhooks define requests initiated by the API rather than its client.
  * Links<br>Links indicate a logical flow of messages, and may help to discuss the appropriateness of the considered usage scenarios for the prototype.

## Relation to other Artefacts

- The [Development Case](/LeanUP/Artefacts/dev-case.md) defines the starting point for the product development and contains the assumptions for product feasibility. The [API Prototype Review][self] challenges the assumptions made.

| *License* | Navigate |
| - | - |
|Common Criteria</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/LeanUP/Images/leanupLogo-s.png)](/LeanUP/Artefacts/overview.md) |

[self]: /LeanUP/Artefacts/pro-review.md

# Information Security Plan

```text
> First post : 24 June 2024
> Last edit : 26 June 2024
```

Information Security and CyberSecurity have become recurring topics on the business planning calendar. In part, driven by government regulation, but also because 'the digital' is more and more of strategic value. CIA is the common acronym embodying the entire scope of digital security: Fully Protect Confidentiality and Data Integrity, and Guarantee Availability whenever you need your digital asset.

Although a L E A N way of governing information security is a bit of a conundrum, I believe there is a decent way to bring it about. This is some guidance to that.

## Risks

Risks are mostly not product-specific. Therefore, it makes sense to keep a list of general risks to assess with any product. This is an important accellerator for a security assessement of a [value case](/LeanUP/Artefacts/val-case.md). There are excellent lists available you can use as a starting point. OWASP, for instance, regularly publishes their [Top-10 for Web Application Security](https://owasp.org/Top10/) and seperately for [API Security](https://owasp.org/API-Security/). A more comprehensive [framework](https://www.enisa.europa.eu/publications/interoperable-eu-risk-management-framework) is available from the European Union.

## Controls

To translate risks into action, keep a list of standard controls. Organize your controls in categories, such as:

- people
- physical objects
- organization
- process, and
- technology.

A single risk will often require controls in multiple categories. Where possibly, define for each control the required proof.

## Information Security Policy

Every organization sets its own information security policy, tuned to its own position in the market and its perceived risk profile. There is a worldwide trend of regulators urging organizations to treat information security as a strategic topic, requiring serious attention and investment. The NIS2 dircetive, for example, puts rules in place that ensure that all public and private entities across the internal market, which fulfil important functions for the economy and society as a whole, are required to take adequate cybersecurity measures.

An independent audit of the effectiveness of the policy is often required, sometimes by clients, but increasingly also by regulators. Privacy protection has become a mandatory part of an information security policy. There are a number of audit frameworks organization can comply to, such as

- SOC 1/ISAE 3402, SOC 2, SOC 3
- FISMA, DIACAP, and FedRAMP
- PCI DSS
- HIPAA
- ISO 9001, ISO 27001, ISO 27017, ISO 27018

## Incident Respons Plan

Preventing any information security incident from ever happening would be a Herculean task. It is also wasteful, by spending lost of energy, resources and time in preventing imaginary events. In a pragmatic approach, the prevention focus is on proven risks. This should be augmented by a zero-repeat strategy, making sure that once an incident has occurred in practice, the same can never again happen. This increases the need for proper incident respons planning.

An Incident Respons Plan is an essential tool to effectively handle security incidents and crises when they occur. It handles internal and external communication and decisioning. It also includes disaster recovery planning.
A typical respons has these steps.

| Step | Description |
| - | - |
| Containment | It is essential to minimize loss and damage through early, decive action, such as blocking network traffic from suspicious IP ranges, revoking certificates / tokens, and invalidating compromised keys. |
| Trace Collection | Collecting and securing forensic information to help analyze the incident, help prove the crime, and to prevent information gets lost |
| Recovery | A tried and tested process to quickly provision a clean instance of the compromised product |
| [Post Mortem][pm] | Taking lessons from a major incident is valuable. A [Post Mortem][pm] not only analyzes what went wrong – and should be improved, but also what went right – and should be cherished |

### The Donts

#### 1. Classification of APIs

Many believe that a solid classification of information assets and categories is the cornerstone to information security policies and controls. I beg to differ. When it comes to API security, there's typically no way to predict the future audience or accessibility. In the words of the [API Mandate](/LeanUP/References/api-mandate.md), an API must be designed for developers in the outside world. Whenever a [value opportunity](/Artefacts/val-oppo.md) is spotted to bring an API to good use, it should be fit for the new purpose by design.

Few things are more disappointing then losing a good [Value Opportunity](/Artefacts/val-oppo.md) over insufficient security clearance. Moreover, contrary to common belief, there is little to gain by lowering your security standards for a subset of your APIs. Leaving aside the question how you can make something only a little bit secure, there are in practice little or no downsides to design for security. It's become trivial to encrypt data in transit. Similarly, encryption or your data at rest is no longer rocket science. Observability features facilitate a solid security incident and event monitoring practice. Consequently, I highly recommend creating a single list of controls and apply them to all your APIs.

> As soon as Information Security has become an integral part of your way of working, a set routine, it doesn't hold you back, rather it accellerates your delivery journey.

This is not to say that all APIs should be made public. On the contrary. Managing access control is an essential part of the [Service Management capability](/LeanUP/Capabilities/service-mgt.md). That's the proper place to manage access. When your API has no presumed audience engineered in, it is generally usable, so it brings a high potential value.

#### 2. Centralization of Security Controls

One of the lessens we've learned as an industry is that, while separation of concerns is important,  delegating resonsibilities into a separated digital domain, remoted from the domain where the knowledge about the actual digital asset is bundled, is an anti-pattern.

### The Do's

#### 1. Shared Responsibiliy

Whether or not you target cloud-native deployment of your API, a clean separation of responsibilities is the foundation of your [Information Security Plan](/LeanUP/Artefacts/sec-plan). Obviously, larger IT ventures implement a more fine-grained approach than smaller ones. However, this is a good starting point.

![Layered Responsibilities](/Images/sharedResponsibilityCapabilities.png)

*I. Infrastructure-level security*.

Securing your tangible digital assets is hard. It is also pretty generic. No wonder the hyperscalers have a competitive adventage. If you can share the cost of security over a large amount of organizations, everyone can profit from the best infrastructure security at a decent price. If you're doing it on your own, consider these capabilities.

- Datacenter security is foundational. 24x7 surveillance, fire proofing, guaranteed power supply, etc
- Network security is essential. The digital world has become ever more intensely networked. Guaranteed internet access, firewalling, intrusion prevention, detection and mitigation, quite a lot to manage here. And then there's DDoS protection.  
- System security. Protection your systems starts with hardening. This is a continual effort. Freqeuntly updating and provisioning your images is a must.
- Continuity. Everything is failing all the time. To optimize continuity at every level, from operations, power, network, and storage to virtualization, carefully consider every potential point of failure. Typically, multiple availability zones are in use to minimize the chance of failure of an entire digital infrastructure.

For each capability, convert the applicable security controls into measures and verifiably implement those.

Next, consider the infrastructure services you need to provide to help secure the platform layer. Anythingy ou can push down as a generic service into the infrastructure, gets automatically standardized, for instance privileged access control, observability, key management, infrastructure as code, object storage, auditing.

> Virtualization decouples the infrastructure from the platform. Having a robust and secure infrastructure virtualization in place will enable your security responsibility separation strategy.

*II. Platform-level security*.

When thinking about platform-level security, the first thing that must be considered is the utilization of infrastructural security services in the platform provisioning scripts. Secondly, it helps to separate different viewpoints.

| Viewpoint | Aspects |
| --- | --- |
| Control Plane Protection | Kubernetes Security is a topic in itself. Secure configuration of your cloud is obviously vital to the security of your platform. It is a recommended practice to utilize Kubernetes namespaces (aka 'Cells') to put security guardrails around the workloads Domain teams manage.|
| Inspection Plane | Having the capabilities in place to observe what's going on, detect suspicious traffic, and automatically counteract when needed, is another recommended practice. |
| Continuous Delivery Funnel | Offering the CI/CD services necessary to deploy workload services in a controled manner is another vital part of the platform. |
| Data Management Services | It is often diffucult to separate the data storage services, such as object stores and backups, from the data mangement services both the platform and the workload management teams use. That's one of the reasons database management systems are difficult to provide in a private cloud. Through a security lens, however, securing storage is a typical infrastucture responsibility, while securing the database management system is a typical platform responsibility, and securing the data is a workload-level responsibility. |
| Access Control Services | Typically, workload management teams require a series of enterprise services to help control access to their workloads. Think of Identity Management, Access Management, Security Token Service, API Gateway, Service Mesh and API Management. |

> Platform APIs decouple the platform from the Workload running on the platform.

*III. Workload-level security*
There are many security practices for workload management teams to master. Identity Management, Authorization, Access Control, API Security, Data Privacy, and many more. Additionally, teams must think about availability and observability. Clustering of multiple instances of your services is a good start. Rate limitation is another recommended practice. Having monitoring in place to generate an operational picture in real-time is also helpful.

It goes without saying that implementing CI/CD pipelines to automatically build and deliver digital assets at high quality is a must, nowadays.

#### 2. Shift Left

Tackling security early in the development process is a well-known accellerator. Sadly, it is easier said than done. It requires smart security toll-gates at every stage [milestone](/LeanUP/Overview/milestones.md). Setting security controls early in the process, while uncertainties still run high, is especially challenging. Fortunately, when the platform and the underlying infrastructure offer a high standard as a starting point, and additional controls are standardized as much as possible, shifting left becomes actually doable.

#### 3. Govern through Principles

LEAN Information Security Governance starts with setting and advocating clear security principles. Security Principles provide clear direction to everyone. As much as possible, Governance is engineered into the digital platform, facilitating frictionless compliance. API Governance must include a mechanism to gently handle the inevitable exceptions. Otherwise, most of the enforcement gets shifted right, towards the Inspection Plane.

Here's a list of security principles for inspiration.

| # | Principle | Rationale | Consequences |
| --- | --- | --- | --- |
| 1. | Least Privilege | People accessing digital assets are a security risk. No one should be able to access anything they are not authorized to. Keeping the list of authorizations to the minimum set of privilleges necessary to fulfil their job provides an additional control to limit security risks. | Micromanaging access can easily become a bit of a burden. Think of attribute-level authorization in a table, or even chapter-level authorization in a document. Especially when flux is high, a pragmatic implementation may be required. |
| 2. | Hands-off Computing | People, be it engineers, administrators, or auditors, must not be able to acccess your runtime workloads. Containers must be immutable to keep data secure and operations reliable | A significant investment in Deployment Automation, Observability, and Security Incident and Event Management is required to help inspect and analyze workloads. Representative pre-production environments with less strict controls also may aid in analysis. Careful incident respons planning required |
| 3. | Automated Deployments | Predictable and reproducable securite measures built in. No human intervention with automatically generated keys and certificates. | Additional effort upfront.  |
| 4. | Data Encryption | There's simply no excuse not to encrypt your data, either in transit or at rest. Period. | Protecting access to your keys is a vital part of your data encryption strategy. Losing a key means losing access to your own data. Mature Key Management Technologies to help prevent both have become common. Whenever possible, generate, store an use your keys without any human access |
| 5. | Security as Code | Security must be a key ingredient in your platform development and software development life cycles. Having security built into the provisioning, delivery and configuration scripts unleashes the power of version and quality control to your security implementation. | Building security controls in the scripts. Investment in security auditing tooling. Training your devops engineers to master platform and software security practices. |
| 6. | Container Orchestration | Containers bring isolation of workloads running on shared compute infrastructure. Container orchestration adds simple clustering, access control, and self-healing capabilities to your digital products. | Building a platform engineering team or adopting a Platform-as-a-service |
| 7. | Full Auditability | Much has been written about an Information Security Management System. This is a –mostly distributed– system designed to capture all the information necessary to prove that you are continuously in control of your information security. This includes information from your Continuous Delivery Funnel, your Control Plane and your Data Plane. | Investing in a Robust Information Security Management System with suitable retention policies and controled access. Adding a great auditor experience is a bonus. Remember that the data must be demonstrably persistent – no loss of security data is permitted, let alone alterations. |

| *License* | Navigate |
| - | - |
|Common Criteria</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/LeanUP/Images/leanupLogo-s.png)](/LeanUP/Artefacts/overview.md) |

[pm]: /LeanUP/Artefacts/post-mortem.md

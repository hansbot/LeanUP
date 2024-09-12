# API Release

```text
> First post : 24 June 2024
> Last edit : 19 July 2024
```

Every security officer needs a structured approach to reviewing releases, defining recommendations and issuing their advice. To start with the latter, there are three types of advice you can bring to a release authority.

1. No objection<br>The release review has not revealed any serious concern. Some recommended improvements may be issued.
2. Under Condition(s)<br>There are serious omissions or issues that must be resolved before the release is justifyable. Sometimes, there's a further difference made between a 'no, unless' and 'yes, if" advice. It's the responsibility of the release authority to validate the conditions. When in doubt, they may request a further advice.
3. Objection<br>Recommending against the release of a product can be terribly frustrating and wasteful, so it is best used sparingly and it better be well-grounded in serious risks. LeanUP is designed to avoid late failures. Any late-stage objection should be analyzed thoroughly, so proper process improvements can be initiated.

The practice of issuing recommendations benefits from the use of common checklists. Typically, the security of every release builds on generic measures an organization has in place. Besides, a checklist to release a platform funcamentally differs from releasing an API. There may obviously be more variants, or conditional modules, that are relevant in your case. In the end, it's all interlinked, a shared responsibility.

Typically, those checklists are derived from the controls, which are in turn the result of a security [risk assesment](/LeanUP/Artefacts/risklist.md). Nowadays, there's a lot of excellent frameworks to base a risk assessment on, such as these [listed by NIST](https://www.nist.gov/cyberframework/assessment-auditing-resources), the COBIT 2019 Framework, and of course the [OWASP Top-10s](https://owasp.org/API-Security/). There are certification bodies using their own approach, such as [ISO](https://en.wikipedia.org/wiki/ISO/IEC_27001), and the [International Standard on Assurance Engagements](https://en.wikipedia.org/wiki/ISAE_3402). The [NIS2 directive](https://www.enisa.europa.eu/topics/cybersecurity-policy/nis-directive-new/minimum-security-measures-for-operators-of-essentials-services) has an interesting comparison.

Don't forget to take a good look at the security recommendations your suppliers are providing. The [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html) has an excellent security pillar to refer to.

```text
** TIP **

Some API Management Products have an API Governance module, allowing you to integrate your API Security Checklist into the API Lifecycle Management process.

As a bonus, you can also implement security controls during other events in the lifecycle of an API, including a subscription event.
```

## Example Security Checklist API Release

|#|Title|Description|Rationale|
|-|-|-|-|
|1|CI/CD only|Confirm that the APIs are managed from the CI/CD pipeline only|With manual deployments, unintentional differences between stages can be introduced. Consequently, test environments may be less representative than assumed. E.g. a conformance scan may yield different results in different stages, hence give a false impression if not performed in every stage (including production).|
|2|Firm Validation|Confirm that the JSON restrictions in the API Definition are enforced (e.g. through the API MicroFirewall)|Format rules must be enforced to be effective. Both the micro gateway and the micro firewall may be used for enforcement.<br>Alternatively, the conformance scan may be used to ascertain the level of enforcement at the backend. Note, however, that the implementation may be changed without an update of the API, hence outside the scope of API Governance.|
|3|Securable API|Confirm that the API definition has a 42C security audit score of at least 80/100|Securable API Definitions are vital for in-transit validation to be effective, avoiding false positives.|
|4|Input sanitation|Confirm that no machine executable code can be entered through an API, e.g. using SQL, LDAP, or XPath expressions, nor executable files and scripts|Malicious users can get unmanaged access to systems and data when input to an API request gets executed directly|
|5|Specification Conformance|Confirm that the API implementation has a 42C security scanner score of at least 80/100|The API definition must reflect the behaviour of its implementation to avoid false positives and false negatives during in-transit request validation. For instance, an undocumented return code may get blocked.|
|6|Limited rates|Confirm that the API has sensible throttling policies, including at least burst protection|Bulk API usage is often an indication of malicious use (DDOS, Mass data scraping)|
|7|Privacy|Confirm that there is no Personal Identifiable information in the URL (i.e. resource path or query parameters).|The URL may end up in server / firewall / proxy / router log files before and after tls termination point (PoT) (potential data leakage)|
|8|Secrecy|Confirm that there is no credential or access token in the URL (i.e. resource path or query parameters).|The URL path may captured before and after tls termination point (PoT), or by a man in the middle.|
|9|Object-level authentication|Confirm that any resource identifiers are not easy to guess (e.g. publicly available OIN, email address, sequences). Recommended use of GUIDs.|Avoid targeted attacks and mass-retrievals|
|10|Input protection|Confirm that the API does not accept an archive file (such as zip) as input|Archive files are being used to mask malicious content such as trojans and zip-bombs. Unpacking and scanning must be done in a safe zone.|
|11|Secure authentication|Confirm that the API security scheme requires the right grant type. Recommended for most use case is Authorization Code Grant flow with PKCE|OAuth grant types are designed to provide reliable authentication on top of an unreliable network|
|12|Identity Masking|Confirm that the right authorization policy gets enforced. Recommended is identity masking as 'my'Resource|Fine-grained authorization is often challenging to enforce during transit. However, making smart use of the capabilities of an Identity Provider, this can often be circumvented. In essence, rather than the untrusted client application, the IdP (and its Policy Information Points) becomes the trusted source for identifiable information.|
|13|Scope-based Authorization|Confirm that authorization levels, when in use, are captured in OAuth/OIDC scopes in the API specification and bound to relevant User Roles|Scopes are permission levels on specific parts of an API and are enforced at the API Gateway. They are useful if different users of a client application consuming the API each have different levels of access, or if different parts of an API are relevant for different client applications (audiences).|
|14|No APIkey|Confirm that API keys (ApiKeyAuth) are not permitted. Instead, require an access token with limited life span|API keys with a lengthy or unlimited lifetime, while convenient for developers, are considered insecure. They are sent with every request, and thereby, over time, even a tiny risk of capturing gets significant.<br>If used at all, make sure they are used in a secure network (e.g. in a Kubernetes cluster or over an m-TLS channel) and always bound to a specific HTTP Referrer (subdomain).<br>WSO2 API Gateway will accept API Keys as query parameter.|
|15|Need-to-know|Confirm that all the resource objects, incoming as well as outgoing, are properly defined in a schema and only include the least possible amount of information|Information that’s transferred but not being used by the receiver may easily leak (e.g. in a web inspector or through a test tool such as Postman)|
|16|Same Origin Unless|Confirm that the CORS configuration is set to minimum necessary access|A Same Origin Policy offers a level of protection against Cross-Site Request Forgery. CORS makes a deliberate exception to the Same Origin Policy, and should be used sparingly.|
|17|Non-repudiation|If a sensitive resource object is received in an API, a digital signature SHOULD be used to verify its origin|Although Digikoppeling/Rest does not yet include a standard for digital signatures (such as JOSE), it is highly recommended to verify the integrity of an incoming message. This is especially relevant when the sender uses an intermediary to transport the object.|

| *License* | Navigate |
| - | - |
|Common Criteria</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/LeanUP/Images/leanupLogo-s.png)](/LeanUP/Artefacts/overview.md) |

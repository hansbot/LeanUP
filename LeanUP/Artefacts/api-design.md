# API Design

```text
> First post : 2 July 2024
> Last edit : 11 July 2024
```

An API Design is the contract between the supplier and the consumer. Just like a legal contract, the more explicit the contract is, the more valuable it is. Whenever you leave room for interpretation, you plant a seed for misunderstanding, broken expectations, and such. It is easy to underestimate the time and care it takes to finalize an API contract.

```text
“Show me your APIs, and I'll tell you what company you are”
```

> *Hans "the human" Bot*

## Resources

Defining your resources is an early step in API Design. It effectively captures the scope of the API and positions the API in your overall Resource Model. Make the resources you expose make sense to the audience you target. In other words, think outside-in when defining a resource model.

```text
“Great API designs avoid leaking internal details, including database design choices, by shifting from data design to message design.”
```

> *James Higginbotham*

Remember that a resource model acts as the web. There may be multiple routes to a single resource. For different routes, you can define subtle difference in the contract. This is to tune the API to the specific needs of, and constraints for an audience. Also, a virtual resource may be a single representation from different sources. You can even design your API from a mix of custom built, off-the-self, as-a-service, and public resources.

Adding a new API to your resource model can be as simple as designing a specification, mapping it to underlying resources, and deploying it to an API Gateway.

## Naming

Naming your APIs, resources, and their properties is much more important than it may seem. As an API represents a product, its name is a trademark, be it a registered one or not. It qualifies as a *"word, phrase, symbol, design, or a combination of these things that identifies your goods or services"*.

Even if you ignore the marketing value, having a clear name will help people find and remember you API more easily. It helps to communicatie the potential value your API has on offer.

Being consistent in your naming, inside an API and across your APIs, will –consiously or not– contribute to a solid image of your business. Conversely, being sloppy at naming will reflect negatively in your image. Defining your [ubiqitous language](/LeanUP/References/ddd.md) will contribute to clarity and consistency.

By the way, consistency is also about the constitution of your names. Think of prefixes and suffixes. You can use «dateOfBirth» or «birthdate» or «dob», but it will confuse your users if you haphazardly mix them up. Don't call something a date when it includes a time. Also think of casing, dashing, and other forms of concatenation. Finally, think about your formats and precision. Use international standards, such as ISO-8601, for dates, units, and geolocation. Refrain from abberations such as the Islamic Calendar, Fahrenheit, and mm-dd-yyyy, or at least give users the option to interact using a widely used standard.

Despite the push for using local languages, I recommend using English names whenever possible. The reason is simple. Developers write there code in a computer language derived from English. Forcing them to use a different language in their code will slow development, increase the rate of errors, and contribute to stress, especially when your local language is not their native language. There will be exceptions, such as product names and legal concepts, that would be awkward in translation. But other than that, language switching is a burden better avoided.

Otherwise, think of logical operations many APIs will need, such as a paging mechnism, a sorting mechanism, a filtering mechnism, conditional requests, and design those consistently. Developers will love you for it.

Don't reinvent the wheel. There are excellent naming guidelines to be found.

## Validity

As an API Designer, make sure you are very precise about defining the type and the validity of your message parameters and message bodies. This includes

- regular expressions for strings
- minimum and maximum lengths for strings and arrays
- minimum and maximum values for numbers
- an enumeration of valid values
- optionality / nullify
- default values

Add typical example values as an additional hint. Example values must comply to the valitiy requirements as defined. Example values can be used to automate testing of APIs.

Reuse of component definitions is highly recommended for consistency.

Since changing validity requirements presents a potential [breaking change](/LeanUP/References/hyrums-law.md), don't think too lightly about those definitions.

## Security

When you define the validity of your input and output, a thorough validation of your traffic already innoculates a lot of threats. But a secure API is more than just blocking invalid messages.

Access control starts with authentication of your identities – be it human or digital in nature. Strong authentiation requires multiple factors (e.g. TLS-MA in combination with an API Key), and a limited lifespan of credentials such as passwords, tokens and certificates.

Eventhough you already require strong authentication of human users, you should always identify the client application someone is using as well. This opens the opportunity to block client applications that, for whatever reason, are misbehaving. Having a fine-grained identiciation mechanism in place enables you to revoke access more targeted. Concretely, every release of an app should get its own identification, every variant (think IOS v. Android) should be independently identified as well.

Authorization is the next step. Different users of the same application may have a different level of access. In APIs, OIDC Scopes are a powerful mechanism to define permission levels. Using these scopes, the Identity Provider can establish the authorization of an identity, and an API Gateway can restrict access to authorized identities only.

## Miscellaneous

To improve searchability, consider adding tags to your definitions. Make sure that you use the labels consistently. Avoid homonyms and synonyms.

Also make use of Descriptions to provide clarity regarding the promises of the contract. Consider adding code snippets as a quick-start for developers.

Finally, a well-documented API includes information regarding interdependencies of resources, for instance a typical flow. Adding links to a resource action in your API specification helps developers to understand what next steps are possbile.

| *License* | Navigate |
| - | - |
|Common Criteria</BR>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en) | [![LeanUP Logo](/LeanUP/Images/leanupLogo-s.png)](/LeanUP/Artefacts/overview.md) |

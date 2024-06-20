# What's in an API

Over the years, APIs have become a catch-all phrase for any kind of interaction with a digital service. The interaction may be synchronous or asynchronous in nature, it may be message based or event oriented, it may be batch processeing or real-time, it may be textual or binary, loosely coupled or tightly coupled, anything goes.

Jeff Bezos got it right, when he drafted his [API Mandate](/References/api-mandate.md):
> It doesn’t matter what technology they use. HTTP, Corba, Pubsub, custom protocols — doesn’t matter
Today I would add ReST, GraphQL, WebSocket, OData, AsyncAPI, Webhook, gRPC/Protobuf, AVRO, SSE, SOAP. Tomorrow, the list may have changed.

In the context of the [Lean Unified Process](/Overview/lup.md), interfaces are simply points of interaction. Simple as they may be, they are of strategic importance. Having strong governance over these interfaces equals strong governance over the overall architecture. APIs are the language of any digital business. Moreover, they define the very structure of a digital business. If you don't govern these interfaces closely, you cannot be in control.

Now, if you can make sure that there are no interdependencies across components in your architecture but APIs, you are in full control. Again, Bezos pointed it out back in 2002:
> There will be no other form of interprocess communication allowed: no direct linking, no direct reads of another team’s data store, no shared-memory model, no back-doors whatsoever. The only communication allowed is via service interface calls over the network.
There you have it. Teams can have full autonomy within the bounds set by the interface contracts. 

APIs done right, in other words, allow you full control over your digital business. That's the core thesis behind the [Lean Unified Process](/Overview/lup.md). And thats why API Design is the core competence in the process.
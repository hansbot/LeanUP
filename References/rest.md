# Evolvable Web-APIs

Roy Fielding layed the groundwork for the ReST API Style in his seminal dissertation.

Here are the core principles he proposed.

| Principle | Statement |
| --- | --- |
| Client/server	| The client and the server act independently, and the interaction between them is only in the form of requests and responses |
| Stateless	| The server does not remember anything about the user who uses the API, so all necessary information to process the request must be provided by the client on each request. |
| Layered system |	The client is agnostic as to how many layers, if any, there are between the client and the actual server responding to the request. This is a key principle of HTTP, allowing for client-side caching, caching servers, reverse proxies, and authorization layering—all transparent to the client sending the request |
| Cacheable	| The server response must contain information about whether or not the data is cacheable, allowing the client and any middleware servers to cache data outside of the API server |
| Code on demand |	The client can request code from the server, usually in the form of a script or binary package, for client-side execution. This is performed today by browsers requesting JavaScript files to extend the behavior of a Web page |
| Uniform interface |	Encourages independent evolvability by leaning on resource-based identification, interaction using representations, self-descriptive messages, and hypermedia controls |

The moniker 'Hypertext as the Engine of Application State', or its acronym HATEOAS, is sometimes used as an overarching principle.

[<img src="/images/lup logo s.png" alt="drawing" class="center" width="150"/>](/Overview/leanup.md)

*License*: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.en)

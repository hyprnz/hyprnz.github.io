---
title: The constraints of REST
description: REST based architecture is still poorly understood. Gareth Evans talks about Roy Fielding's constraints of REST.
layout: post
author: Gareth Evans
twitter: gareth__evans
genre: Software Architecture
keywords: Digital architecture, REST based architecture, distributed architecture, Representational State Transfer
---

> A distributed system is one where a machine I’ve never heard of can cause my program to fail. - [Leslie Lamport](http://research.microsoft.com/en-us/um/people/lamport/pubs/distributed-system.txt)

Nearly every modern business system built is a distributed system. A REST based architectural style helps simplify distributed systems. This is especially important when the system must support multiple digital channels, scale at low cost and remain easy to change over time.

REST (Representational State Transfer) is about building software systems the way the web works, with [longevity](https://global.oup.com/academic/product/the-timeless-way-of-building-9780195024029?cc=nz&lang=en&) in mind.

> An architectural style is a coordinated set of architectural constraints that restricts the roles/features of architectural elements and the allowed relationships among those elements within any architecture that conforms to that style. - [Roy Fielding](https://www.ics.uci.edu/~fielding/pubs/dissertation/software_arch.htm)

The REST style is best understood through its constraints, which are a series of tradeoffs between performance, scalability, simplicity, modifiability, visibility, portability and reliability.

### Client–server

A uniform interface separates clients from servers. This separation means clients are not concerned with tasks such as database communication, cache management etc.

* Improves the portability of client code as clients are thinner and client code can be reused i.e. hypermedia can result in more functionality on the client while reducing the amount of API-specific code on the client
* Servers are simpler and more scalable as they are concerned about representations not the user interface or user state
* Servers and clients may be replaced and developed independently, as long as the interface between them is not altered
* Enables multiple organisational domains through separation of concerns

### Stateless

No client context is stored on the server between requests. Each request from any client contains all the information necessary to service the request. Session state can be held in the client.

* Simplifies the server as each request is independent, this is especially beneficial for monitoring
* Improves scalability as the server does not need to store session state or manage resources between requests
* Improves reliability as it is easier to recover from partial failures
* Degrades efficiency as more network traffic is sent unless caching is used

### Cacheable

Responses can be cached at the client or within the network. Responses must implicitly or explicitly define themselves as cacheable, to prevent clients from reusing stale or inappropriate data.

* Reduces latency
* Improves efficiency as caching partially or completely eliminates some client–server interactions
* Improves scalability as caching can be distributed throughout the network in a layered system
* Degrades reliability if cached data is significantly different from data that would have been retrieved from the server

### Layered system
A client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way.

* Allows for shared caching throughout the network
* Simplifies clients by hiding unwanted information
* Encapsulating legacy systems protects clients from changes and prevents load on legacy systems
* Improves scalability through caching and load balancing
* Simplifies security by specialising it in layers and securing resources
* Adds latency as more layers are added

#### Code on demand (optional)

Servers can temporarily extend or customize the functionality of a client by the transfer of executable code. Examples of this may include client-side scripts such as JavaScript. "Code on demand" is the only optional constraint of the REST architecture.

* Web browser becomes a distributed computing node which reduces server load
* Code can be shared between clients
* Improves extensibility as code on demand can be deployed easily
* Reduces visibility of code executing on the client

#### Uniform interface

The uniform interface simplifies and decouples the architecture, which enables each part to evolve independently. The four uniform interface constraints are:

#### Identification of resources

Individual resources are identified in requests, for example using URLs in web-based REST systems. The resources themselves are conceptually separate from the representations that are returned to the client. For example, the server may send data from its persistence store as HTML, XML or JSON, none of which are the server's internal representation. This can be particularly valuable when evolving a system over time.

#### Manipulation of resources through these representations

When a client holds a representation of a resource, including any metadata attached, it has enough information to modify or delete the resource. This is advantageous when considering many small resources being composed in different ways by different clients over time. It also prevents the need to duplicate logic.

#### Self-descriptive messages

Each message includes enough information to describe how to process the message. For example, which parser to invoke may be specified by an Internet media type (previously known as a MIME type). Responses also explicitly indicate their cacheability.

#### Hypermedia as the engine of application state (HATEOAS)

Clients make state transitions only through actions that are dynamically available within hypermedia by the server (e.g., by hyperlinks within hypertext). Except for simple fixed entry points to the application, a client does not assume that any particular action is available for any particular resources beyond those described in representations previously received from the server. This radically reduces the amount of logic held in clients and allows for one API to support many different digital channels at lower cost. The client need not be aware of internal implementation details.

### Conclusion

It’s been fifteen years since Roy Fielding wrote his [dissertation](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm) on network based architectures. REST, when applied with all the constraints, is still the future for many distributed digital business applications. That says a lot.


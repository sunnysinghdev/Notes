# REST Principle

## RESTful architecture properties
1. Performance
2. Scalability
3. Simplicity
4. Interoperability
5. Communication Visibility
6. Component Portability
7. Reliability

## RESTful Principles encapsulates above properties 
* Client server seperatoin of concerns
* Layered System
* Stateless
* Uniform Interface
* Cache
* Code on demand

## Client Server
The `Client-Server constraint` enforces the proper **separation of concerns between
the UI/consumer and the back-end**, which mostly contains the business-logic and
data-storage implementations. We can observe this constraint in typical network-based
systems like websites. In this style, the client initiates requests to the server, which
reacts with triggering responses. Enforcing separation between the client and the server
promotes the ability to have them evolve entirely independently from each other given
that the interface between them doesn’t change.

## Layered System
Often combined with the `Client-Server constraint`, the `Layered System constraint`
dictates that **layers should be organized hierarchically**, restricting the use of a service to
the layers directly beneath and above it. `Orchestrating` components in layers drastically
improves reusability, making them more modular.

## Stateless

Building on the Client-Server style is the `Stateless` constraint. Communication
between the client and the server needs to be stateless, meaning that **a request should
contain all the information necessary for the server** to understand and to create context.
The client is ultimately responsible for managing session state and cannot rely on the
server for directly storing any state data. Does this mean that the actual contents of the
state need to be transferred back and forth all the time? The short answer is no—it is
entirely acceptable for the state to be persisted elsewhere and for the client to include an
identifier for retrieving it.

## Uniform Interface

The key feature that associates a system with REST is a `Uniform Interface`. This
constraint consists of four essential parts, which are resource **identification, resource
manipulation, self-describing responses, and state management**. These architectural
elements are implemented directly through URIs, HTTP verbs, media types, and
Hypermedia as the Engine of Application State (HATEOAS), respectively.

>Note: `HATEOAS` is also part of the `Uniform Interface` as well as a constraint of the
REST stateless application, which allows a client to have no prior knowledge of
how to interact with the server beyond a general understanding of the hypermedia
provided by the server.

## Cache

The Cache constraint derives from the `Stateless constraint` and requires that
responses coming from the server are **explicitly labeled as cacheable or non-cacheable**,
regardless if they are explicitly or implicitly defined. Responses that are cached allow
clients to reuse them later when making similar requests, thus improving speed and
latency. Caching can be applied to both the client and the server side.

## Code On Demand
The final and optional constraint is `Code on Demand`, which allows a client to
**access specific resources from the server without knowledge of how to process them**.
This style is typically implemented by web-based applications that have clients using a
client-side scripting language, like JavaScript. Having the ability to add functionality to a
deployed client not only promotes extensibility but can also help to offload some server-side
tasks onto the client, making it more responsive.
# ApiGateway (*Reverse proxy on Steroids*)

## Conerns for Apis	
1. `Authorisation / Authentication`
2. `Client (web/ mobile /server)`
3. `caching`
4. `reporting , analytics`
5. `network latency considertations`
6. `composition, aggregation`
7. `versioning`
8. `protocols / protocol translation`
9. `security`
10. `quotas`
	


## Define API Gateway
An API gateway is a server that acts as a “front-end” for an API. It receives requests, enforces policies and forwards appropriate requests to the service. By virtue of being a proxy it can provide functionality to support authentication, authorisation, security, audit and regularity compliance. It helps insulate the client from the implementation details, deal with versioning and reduce the number of requests / round-trips by aggregating queries. There’s a great description of the pattern here.https://microservices.io/patterns/apigateway.html

![alt text](https://microservices.io/i/apigateway.jpg  "logo1")
 ![alt text](https://microservices.io/i/bffe.png  "logo1")
 
 
 ## Context
 Using an API gateway has the following benefits:
### Pros
>` 
** Insulates the clients from how the application is partitioned into microservices.
Insulates the clients from the problem of determining the locations of service instances.
Provides the optimal API for each client
Reduces the number of requests/roundtrips. For example, the API gateway enables clients to retrieve data from multiple services with a single round-trip. Fewer requests also means less overhead and improves the user experience. An API gateway is essential for mobile applications.
Simplifies the client by moving logic for calling multiple services from the client to API gateway
Translates from a “standard” public web-friendly API protocol to whatever protocols are used internally
The API gateway pattern has some drawbacks:`
### Cons
>Increased complexity - the API gateway is yet another moving part that must be developed, deployed and managed
Increased response time due to the additional network hop through the API gateway - however, for most applications the cost of an extra roundtrip is insignificant.
One anti-pattern around API Gateways (as noted by Thoughtworks) is a tendency for the API gateway to grow in functionality to the point that its complexity outweighs the benefits. It’s still a SPOF and requires specialist skills to maintain.

Issues:
How implement the API gateway? An event-driven/reactive approach is best if it must scale to scale to handle high loads. On the JVM, NIO-based libraries such as Netty, Spring Reactor, etc. make sense. NodeJS is another option.


# Service Mesh
A service-mesh offers consistent discovery, security, tracing, monitoring and failure handling without the need for a shared asset like an API gateway or message bus.
[Medium Link Article](https://medium.com/ingeniouslysimple/how-did-we-get-to-service-meshes-682e1e3d6327 "https://medium.com/ingeniouslysimple/how-did-we-get-to-service-meshes-682e1e3d6327")


· North/South communication refers to traffic flowing in and out of the data centre/network.
· East/West communication refers to traffic flowing between devices within your data centre/ network.


API Management tools (such as API Gateways) really comes into the fore for North/South communication — when I’m bridging between the great big scary outside world and my internal software.
Service mesh technology excels for East/West communication where I can use technology like mutual TLS to establish trust between components I own.


# Links
**Service Mesh**
1. https://medium.com/ingeniouslysimple/how-did-we-get-to-service-meshes-682e1e3d6327

**API Gateway **
1. https://medium.com/ingeniouslysimple/what-is-an-api-gateway-8f0c4a1a1d39

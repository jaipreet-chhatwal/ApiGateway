# ApiGateway

## Conerns for Apis	
1. `Authorisation / Authentication`
2. `Client (web/ mobile /server)`
3. `caching`
4. `reporting , analytics`
5. `network latency considertations`
6. `composition`
7. `versioning`
8. `protocols / protocol translation`
	


## Define API Gateway
An API gateway is a server that acts as a “front-end” for an API. It receives requests, enforces policies and forwards appropriate requests to the service. By virtue of being a proxy it can provide functionality to support authentication, authorisation, security, audit and regularity compliance. It helps insulate the client from the implementation details, deal with versioning and reduce the number of requests / round-trips by aggregating queries. There’s a great description of the pattern here.https://microservices.io/patterns/apigateway.html

![alt text](https://microservices.io/i/apigateway.jpg  "logo1")
 ![alt text](https://microservices.io/i/bffe.png  "logo1")
 
 
 ## Context
 Using an API gateway has the following benefits:
### Pros
>` ...Insulates the clients from how the application is partitioned into microservices..
...Insulates the clients from the problem of determining the locations of service instances..
Provides the optimal API for each client
Reduces the number of requests/roundtrips. For example, the API gateway enables clients to retrieve data from multiple services with a single round-trip. Fewer requests also means less overhead and improves the user experience. An API gateway is essential for mobile applications.
Simplifies the client by moving logic for calling multiple services from the client to API gateway
Translates from a “standard” public web-friendly API protocol to whatever protocols are used internally
The API gateway pattern has some drawbacks:`
### Cons
>Increased complexity - the API gateway is yet another moving part that must be developed, deployed and managed
Increased response time due to the additional network hop through the API gateway - however, for most applications the cost of an extra roundtrip is insignificant.
Issues:


How implement the API gateway? An event-driven/reactive approach is best if it must scale to scale to handle high loads. On the JVM, NIO-based libraries such as Netty, Spring Reactor, etc. make sense. NodeJS is another option.

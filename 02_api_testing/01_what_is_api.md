# What is API

***Application Programming Interface (API)*** is a SW interface that allows two or more applications to interact with each other without any user intervention. API is a collection of SW functions and procedures. In simple terms, API means a SW code that can be accessed or executed. API is defined as a code that helps two different software's to communicate and exchange data with each other.

https://blog.postman.com/intro-to-apis-what-is-an-api/

Digging deeper, as easy way to understand the definition of an API is to think about the applications that you use every day. In an internet-connected world, web and mobile applications are designed for humans to use, while APIs are designed for other digital systems and applications to use. Websites and APIs both do the same thing, like return data, content, images, video, and other information. But APIs don't return all the details that are needed to make things look pretty for human eye - you only get the raw data and other machine-readable information needed behind the scenes to put the resources being delivered to work, with very little assistance from human.


## What are APIs used for?
- APIs power desktop applications.
- APIs are behind most web applications.
- APIs make mobile applications possible.
- APIs are the integrations for no code solutions.
- APIs connect devices to the internet.
- APIs define the network - or the information passed between applications, systems, and devices.
- APIs even connect everyday things like automobiles, doorbells, dishwashers, and etc.


## Why should you care about APIs?
- APIs help you access the data you need to get your work done and do daily tasks - whether you're a business user, a student, or using an application for fun.
- APIs make it possible to integrate different systems together, like CRMs, DBs, or even school learning management systems.
- APIs help different departments, teams, and groups become more agile.
- APIs help organizations, schools, government agencies, and nonprofits strengthen relationships with other organizations, research institutes, and agencies.


## Why use APIs? Reasons to use APIs
- Integration with internal and external systems.
- Adding or enhancing functionality of internal and external systems.
- Adding or enhancing functionality for customers.
- Speeding up SW and system development. APIs allow developers to code and deliver functinality as microservices, instead of big, monolithic apps.
- Reducing operating costs. 
- Reducing SW development costs.
- Improving software and system testing. This can be done by allowing QAs to separate tests from frontend components, the parts of SW that users see, from tests for backend components, the parts of SW that don't see.
- Improving organizational security and governance.
- Enabling mobile applications. 


## API architectural styles
- **REST API.** REST is an acronym for **RE**presentational **S**tate **T**ransfer. REST APIs rely on a few guiding principles such as a client-server structure, simple, uniform interfaces to communicate across systems, stateless operations, and more.
- **Webhooks** are event-based, and simply put, are automated messages sent from one system to another anytime an event occurs. Webhooks are even referred to 'reverce APIs' as a concept to check for changes in data.
- **SOAP API** - **S**imple **O**bject **A**ccess **P**rotocol. SOAP APIs are more structured and formalized than other APIs, they are reliable and trusted, but can be slower that other APIs. SOAP APIs use and XML-based messaging protocol which includes the Envelope, Header, and Body tags as required by the endpoint.
- **GraphQL** - **Graph Q**uery **L**anguage. The GraphQL defines how one API asks another API for information and instead of relying on how the server defines the endpoint, a GraphQL query can ask for a specific piece of information.
- **WebSocket API**s rely on the WebSocket computer communications protocol, which is a full-duplex communication channel over a single TCP connection. WebSocket APIs provide a standard way for server to send information and data to clients, even when the client is not requesting data. WebSocket APIs also allow data to be communicated between clients and servers, while keeping connection open.
- **gRPC API.** RPC stands for **R**emote **P**rocedure **C**all; gRPC APIs were originated by Google. in gRPC, a client can call on a server just like it is a local object, making it easier for distributed apps and systems to communicate with one another.
- **Server-sent even API,** also known as SSE, is a technology that relies on data being pushed from the server. This allows a client to receive updates automatically via HTTP connection.
- **AMQP APIs** - **A**dvanced **M**essage **Q**ueuing **P**rotocol. AMQP is a protocol that follows open standards, and works at the application layer. AMQP is best suited for message-oriented middleware, and like othe protocols, AMQP dictates how messaging providers and clients communicate with each other.
- **MQTR APIs** - **M**essage **Q**ueuing **T**elemetry **T**ransport. The MQTT messaging protocol is defined by Organization for Advancement of Structured Information Standards, better known  as OASIS. MQTT is well-suited for Internet of Things (IoT), in part because it is extremely lightweight. MQTT allows devices to publish and/or subscribe to messages.
- **EDI** - **E**lectronic **D**ata **I**nterchange, and it's been around for a long time since the '70s! The idea behind EDI is to allow business to communicate electronically with each, typically transmitting information that was written on paper, like receipts or invoices that an accounts payable might send out, or order information such as purchase orders.


## What is an API endpoint?
An API endpoint is a point at which an API - the code that allows two software programs to communicate with each other - connects with the SW program. APIs work by sending requests for information from a web application or web server and receiving a response.
In other words, API endpoints are the specific digital location where requests for information are sent by one program to retrieve the digital resource that exists there. Endpoints specify where APIs can access resources and help guarantee the proper functioning of the incorporated SW. An API's performance depends on its capacity to successfully communicate with API endpoints.
SW programs typically have multiple API endpoints. For example, Instagram's endpoints include one that allows businesses and creators to measure media and profile interactions; one that allows them to moderate comments and their replies; and a third that allows them to discover hashtagged media.

### How API endpoints work
Systems that communicate through APIs are integrated systems. One side sends the information to the API and is called the server. The other side, the client, makes the requests and manipulates the API. The server side that provides the requested information, or resources, is the API endpoint.
For an effective request to be processed by the endpoint, the client must provide a uniform resource locator (URL), a method, a list of headers and a body.
The headers provide metadata about a request and the body holds the data sent by the client to the server.
Endpoints work in tandem with API methods. Methods are permitted requests that can be made, such as GET, DELETE, PATCH or POST. Methods - ofen called verbs in communications syntax - after often placed just before the specified endpoint in a full URL.

### Examples of API endpoints
The code used in placing a request for a specific statistics page on the NBA's web site might read:
> GET https://stats.nba.com/stats/allstarballotpredictor

In this example GET is the method while the endpoint is the specific portion of the web address noted as **/stats/allstarballotpredictor**. 
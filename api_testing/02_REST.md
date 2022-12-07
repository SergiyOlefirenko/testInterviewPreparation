https://restfulapi.net/


# What is REST
REST is an acronym for REpresentational State Transfer and an architectural style for distributed hypermedia systems.
A Web API (or Web Service) conforming to the REST architectural style is a REST API.
<br>

##1. Guiding Principles of REST
###1.1. Uniform Interface
By applying the priciple of generality to the components interface, we can simplify the overall system architecture and improve the visibility of interactions.
The following four constraints can achieve a uniform REST interface:
- **Indentification of resources** - the interface must uniquely identify each resource involved in the interaction between the client and the server.
- **Manipulation of resources through representations** - the resources should have uniform representations in the server response. API consumers should use these representations to modify the resources state in the server.
- **Self-descriptive messages** - each resource representation should carry enough information to describe how to process the message. It should also provide information of the additional actions that the client can perform on the resource.
- **Hypermedia as the engine of application state** - the client should have only the initial URI of the application. The client application should dynamically drive all onther resources and interactions with the use of hyperlinks.
###1.2. Client-Server
The client-server design pattern enforces the separation of concerns, which helps the client and the server components evolve independently.
By separating the user interface concerns (client) from data storage concerns (server), we improve the portability of the user interface across multiple platforms and improve scalability by simplifying the server components.
While the client and the server evolve, we have to make sure that the interface/contact between them does not break.
###1.3. Stateless
Statelessness mandates that each request from the client to the server must contain all of the information necessary to understand and complete the request. The server cannot take advantage of any previously stored context information on the server. For this reason, the client application must entirely keep the session state.
###1.4. Cacheable
The cacheable constraint requires that a resource should implicity or explicity label itself as cacheable or non-cacheable. If the response is cacheable, the client app gets the right to reuse the response data later for equivalent requests and a specified period.
###1.5. Layered System
The layered system style allows an architecture to be composed of hierarchical layers by constraining component behavior. For example, in a layered system, each component cannot see beyond the immediate layer they are interacting with.
###1.6. Code on Demand (Optional)
REST also allows client functionality to extend by downloading and executing code in the form of applets or scripts. The downloaded code simplifies clients by reducing the number of features required to be pre-implemented. Servers can provide part of features delivered to the client in the form of code, and the client only needs to execute the code.
<br>

##2. What is a Resource?
The key **abstraction of information** in REST is a resource. Any information that we can name can be a resource. For example, a REST resource can be a document or image, a temporal service, a collection of other resources, or a non-virtual object (e.g., a person).
The state of the resource, at any particular time, is know as the **resource representation**. The resource representation are consist of:
- the **data**.
- the **metadata** describing the data.
- and the **hypermedia links** that can help the client in transition to the next desired state.
###2.1. Resource Identifiers
REST uses resource identifiers to identify each resource involved in the interactions between the client and the server components.
###2.2. Hypermedia
The data format of a representation is known as a media type. The media type identifies a specification that defines how a representation is to be processed. **A RESTful API looks like hypertext.** Every addressable unit of information carries and address, either explicitly (e.g., link and id attribute) or implicitly (e.g., derived from the media type definition and representation structure).
###2.3. Self-Descriptive
Futher, **resource representations shall be self-descriptive**: the client does not need to know if a resource is an employee or a device. It should act based on the media type associated with the resource. So in practice, we will create lots of **custom media types** - usually one media type associated with one resource. Every media type defines a default processing model. For example, HTML defines a rendering process for hypertext and the browser behavior around each element.
<br>

##3. Resource Methods
These resource methods are used to perfom the desired transition between two states of any resource. A large number of people wrongly relate resource methods to HTTP methods (i.e., GET/PUT/POST/DELETE). Roy Fielding has never mentioned any recomendation around which method to be used in which condition. All he emphasizes is that it should be a **uniform interface**. For example, if we decide that the application APIs will use HTTP POST for updating a resource - rather than most people recommend HTTP PUT - it's all right. Still, the application interface will be RESTful. Ideally, everything needed to transition the resource state shall be part of the resource representation - including all the supported methods and what form the will leave the representation.
<br>

##4. REST and HTTP are Not the Same
Though REST also intends to make the web (internet) more streamlined and standard, Roy Fielding advocates using REST principles more strictly. And that’s from where people try to start comparing REST with the web.Roy Fielding, in his dissertation, has nowhere mentioned any implementation direction – including any protocol preference or even HTTP. Till the time, we are honoring the six guiding principles of REST, which we can call our interface – RESTful.

https://www.geeksforgeeks.org/client-server-model/
https://www.knowledgehut.com/blog/cloud-computing/client-server-architecture


# Client-Server Model

The client-server model is a distributed application structure that partitions task or workload between the providers of a resource or service, called servers, and service requesters called clients. In the client-server architecture, when the client computer sends a request for data to the server through the internet, the server accepts the requested process and deliver the data packets requested back to the client. Clients do not share any of their resources. 

##### How the Client-Server Model works?
- ***Client:*** when we talk the word Client, it mean a computer (Host) i.e capable of receiving information or using a particular service from the service providers (Servers).
- ***Servers:*** are remote computers which provide information (data) or access to particular services.
![Client-server](../00_resources/01_img/client_server_01.png)

##### How the browser intercats with the servers?
There are a few steps to follow to interact with the servers for a client.
- User enters the URL (Uniform Resource Locator) of the website or file. The Browser then requests the DNS (Domain Name System) Server.
- DNS Server lookup for the address of the WEB Server.
- DNS Server responds with the IP address of the WEB Server.
- Browser sends over an HTTP/HTTPS reqeust to WEB Server's IP (provided by DNS server).
- Server sends over the necessary files of the website.
- Browser then renders the files and the website is displayed. This rendering is done with the help of DOM (Document Object Model) interpreter, CSS interpreter and JS Engine collectively known as the JIT (Just in Time) or Compilers.
![Client-server](../00_resources/01_img/client_server_02.png)

##### Types of Client Server Architecture
***1-tier architecture***
In a 1-tier design, every user interface environment, client/server installation setting, data logic system, and marketing logic system are present on the same system. These services are trustworthy, but handling the jobs they assign for replication of the full operation is highly challenging because they contain all the data in multiple variances.
For example, one software package can be used for presentation, business, and data access layers. The local machine stores all of the data. There are certain programs that control all three tiers, such as the MP3 palyer and Microsoft Office, but these programs are categorized as 1-tier apps.

***2-tier architecture***
The optimum client/server environment is provided by a two-tier design, which enables the user interface to be stored on the client system and all databases to be saved on the server computer. It is necessary to preserve database logic and business logic regardless of whether they are kept on the server or the user's end. The architecture is known as "fat client thin server" when these logics are stored on the client side, but we refer to it as "thin client fat server" when these logic are handled by the server.
The quickest rate is reached because client-server devices are in direct communication with one another when the client fires the order. This strategy has a few advantages, such as the best performance, simplicity in 2-tier application design, user satisfaction with the response from this architecture, and a homogeneous environment.

***3-tier architecture***
Middleware is required in this three-tiered design because if the client machine makes the request to the server machine, the middle layer will first receive it before passing it on to the server. Therefore, the middle layer first receives the server's response before passing it on to the client machine. Both business and data logic is kept on the middleware. Middleware is used to increase flexibility and provide top perofrmance.
A three-tier architecture is separated into three layers: the presentation layer (Client Tier), the application layer (Business Tier), and the database layer (Data Tier). Presentation layer management is handled by the client machine, Application layer management is handled by the server machine, and Database layer management is handled by the database layer.

***N-tier architecture***
The approach is a scaled version with three levels. The strategy is often referred to as "Multi-tier architecture". Each function, including display, application processing, and data management functionalities, can be placed in this design as a separate layer.
Additionally, client-server systems are more expensive to develop than peer-to-peer systems and require a central file server. While peer-to-peer systems rely on end users to manage security, the client-server model gives clients access to a dedicated file server, which offers stronger protection. Peer-to-peer networks also perform worse as the number of nodes rises, but client-server systems are more reliable and scalable to any size. As a result, which one you choose depends on the environment in which you must implement it.

##### Characteristics of Client-server Architecture
- A mechanism of requests and responses powers the architecture. The client sends a request to the server, and the server returns data in the response to the information requested.
- The architecture uses a common contact protocol so that devices can simply communicate with  one another. Every data transport protocol is available at the application layer.
- A server may only be able to handle a limited number of client requests at once. It uses a method targeting priority to respond to each and every query.
- By assaulting the server with duplicate requests, denial of service attacks makes it difficult for it to respond to legitimate client requests.
- Scalability is a crucial feature of client-server systems. They can be resized either horizontally of vertically. Adding or removing client workstations while barely affecting performance is known as horizontal scaling. Vertical scaling refers to upgrading to a more powerul server.
- The environment is frequently multivendor and haterogeneous. Client and server operating systems and hardware platforms typically differ from one another. A well-defined set of common application programming interfaces (APIs) and remote procedure calls (RPCs) is used by client and server processes to communicate with one another.

##### Difference Between System Architecture and Server Architecture
System architecture is a conceptual model that specifies the structure and behavior of a system, which is the primary distinction between system architecure and software architecture. Server architecture, in contrast, is a high-level structure that specifies the responses to meet technical and business goals while maximizing the software's quality.
System archicture incorporates both software and hardware parts and is utilized to enable the diesigning of such a composite system. Server architecture, on the other hand, takes into account a variety of aspects, including human dynamic, business strategy, quality aspects, design, and IT architecture, among others.


##### Advantages of Client-Server model:
- Centralized system with all data in a single place.
- Cost efficient requires less maintenance cost and Data recovery is possible.
- The capacity of the Client and Servers can be changed separately.

##### Disadvantages of Client-Server model:
- Clients are prone to viruses, Trojans and worms if present in the Server or uploaded into the Server.
- Server are prone to Denial of Service (DOS) attacks.
- Data packets may be spoofed or modified during transmission.
- Phishing or capturing login credentials or other useful information of the user are common and MITM (Man in the Middle) attacks are common.
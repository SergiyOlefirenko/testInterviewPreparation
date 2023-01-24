https://restfulapi.net/http-methods/


# What is HTTP?
**HTTP** stands for **H**yper **T**ext **T**ransfer **P**rotocol.
**WWW** is about communication between we clients and servers.
Communication between client computer and web servers is done sending HTTP Requests and receiving HTTP Responses.


## HTTP Methods
REST APIs enable you to develop all kinds of web apps having all possible CRUD operations. REST guidelines suggest using a specific HTTP method on a particular type of call made to the server. 

---

### 1. HTTP Get

Use GET requests **to retrieve resource representation/information only** - and not modify it in any way. As GET requests do not change the resource's state, these are said to be **sage methods**.
Additionally, **GET APIs should be idempotent**. Making multiple identical requests must produce the same result every time until another API (POST or PUT) has changed the sate of the resource on the server.

#### 1.1. GET API Response Codes
- For any given HTTP GET API, if the resource if found on the server, then it must return HTTP response code **200 (OK)** - along with the response body, which is usually either XML or JSON content.
- In case the resource is NOT found on the server then API must return HTTP response code **404 (NOT FOUND)**.
- Similarly, if it is determined that the GET request itself is not correctly formed then the server will return the HTTP response code **400 (BAD REQUEST)**.

#### 1.2. Example URIs
>HTTP GET http://www.appdomain.com/users
>HTTP GET http://www.appdomain.com/users?size=20&page=5
>HTTP GET http://www.appdomain.com/users/123
>HTTP GET http://www.appdomain.com/users/123/address

---

### 2. HTTP POST

Use POST APIs **to create new subordinate resources**, e.g., a file is subordinate to a directory containing it or a row is subordinate to a DB table. When talking strictly about REST, POST methods are used to **create a new resource** into the collection of resources.
Responses to this method are **not cacheable** unless the response includes appropriate Cache-Control or Expires header fields. POST is **neither safe nor idempotent**, and invoking two identical POST requests will result in two different resources containing the same information (except resource ids).

#### 2.1. POST API Response Codes
- Ideally, if a resource has been created on the origin server, the response SHOULD be HTTP response code **201 (Created)** and contain an entity that describes the status of the request and refers to the new resource, and a Location header.
- Many times, the action performed by the POST method not result in a resource that can be identified by a URI. In this case, either HTTP response code **200 (OK)** or **204 (No Content)** is the appropriate response status.

#### 2.2. Example URIs
>HTTP POST http://www.appdomain.com/users
>HTTP POST http://www.appdomain.com/users/123/accounts

---

### 3. HTTP PUT

Use PUT APIs primary **to update and existing resource (if the resource does not exist, the API may decide to create a new resource or not)**. If the request passes through a cache and the Request-URI identifies one or more currently cached entites, those entries SHOULD be treated as stale. Responses to PUT method are **not cacheable**.

#### 3.1. PUT API Response Codes
- If a new resource has been created by the PUT API, the origin server MUST inform the user agent via HTTP response code **201 (Created)** response.
- If an existing resource is modified, either the **200 (OK)** or **204 (No Content)** response codes SHOULD be sent to indicate successful completion of the request.

#### 3.2. Example URIs
>HTTP PUT http://www.appdomain.com/users/123
>HTTP PUT http://www.appdomain.com/users/123/accounts/456

==The difference between the POST and PUT APIs can be observed in request URIs. POST requests are made on resource collections, whereas PUT requests are made on a single resource.==

---

### 4. HTTP DELETE

DELETE APIs **delete the resources** (identified by the Request-URI). If you DELETE a resource, it's removed from the collection of resources. If the request passes through a cache and the Request-URI identifies one or more currently cached entities, those entries SHOULD be treated as stale. Response to this method are **not cacheable**.

#### 4.1. DELETE API Response Codes
- A successful response of DELETE request SHOULD be an HTTP response code **200 (OK)** if the response includes an entity describing the status.
- The status should be **202 (Accepted)** if the action has been queued.
- The status should be **204 (No Content)** if the action has been perfromed but the response does not include an entity.
- Repeatedly calling DELETE API on that resource will not change the outcome - howere, calling DELETE on a resource a second time will return a **404 (NOT FOUND)** since it was already removed.

#### 4.2. Example URIs
>HTTP DELETE http://www.appdomain.com/users/123
>HTTP DELETE http://www.appdomain.com/users/123/accounts/456

---

### 5. HTTP PATCH

HTTP PATCH requests are **to make partial update** on a resource. If you see PUT requests modify a resource entity too. So to make it more precise - the PATCH method is the correct choise for partially updating an existing resource, and you should only use PUT if you're replacing a resource in its entirety.
Support for PATCH in browsers, servers, and web application frameworks is not universal. IE8, PHP, Tomcat, Django, and lots of other software have missing or broken support for it.

Request payload of a PATCH request is not straightforward as it is for a PUT request. e.g.
>HTTP GET /users/1

produces below response:
>{ "id": 1, "username": "admin", "email": "email@example.org"}

A sample patch request to update the email will be like this:
>HTTP PATCH /users/1
[{ "op": "replace", "path": "/email", "value": "new.email@example.org" }]

==The PATCH method is not a replacement for the POST or PUT methods. It applies a delta (diff) rather than replacing the entire resource.==

---

### 6. Summary of HTTP Methods

| HTTP Method | CRUD | Collection Resource (e.g. /users) | Single Resource (e.g. /users/123) |
| ----- | ----- | ----------- | ----------- |
| POST | Create | 201 (Created), 'Location' header with link to /user/{id} containing new ID | Avoid using POST on a single resource |
| GET | Read | 200 (OK), list of users. Use pagination, sorting, and filtering to navigate big lists. | 200 (OK), single user. 404 (Not Found), if ID not found or invalid. |
| PUT | Update/Replace | 405 (Method not allowed), unless you want to update every resource in the entire collection of resources. | 200 (OK) or 204 (No Content). Use 404 (Not Found), id ID is not found or invalid. |
| PATCH | Partial Update/Modify | 405 (Method not allowed), unless you want to modify the collection itself. | 200 (OK) or 204 (No Content). Use 404 (Not Found), id ID is not found or invalid. |
| DELETE | Delete | 405 (Method not allowed), unless you want to delete the whole collection - use with caution. | 200 (OK). 404 (Not Found), if ID not found or invalid. |

---

### 7. Clossary

#### 7.1 Safe Methods

Request methods are considered safe if their defined semantics are essentially read-only. The client does not request, and does not expect, any state change on the origin server as a result of applying a safe method to a target resource.
**The GET, HEAD, OPTIONS, and TRACE methods are considered safe methods.**
The purpose of distinguishing between safe and unsafe methods is to allow automated retrieval processes (spiders) and cache performance optimization (pre-fetching) to work without fear of causing harm.

#### 7.2. Idempotent Methods

The term idempotent is used more comprehensively to describe **an operation that will produce the same results if executed once or multiple times**.
In HTTP specification, the **PUT, DELETE and safe methods (GET, HEAD, OPTIONS, TRACE) are idempotent methods**.
Idempotence is a handy property in many situations, as it means that an operation can be repeated or retried as often as necessary without causing unintended effects.
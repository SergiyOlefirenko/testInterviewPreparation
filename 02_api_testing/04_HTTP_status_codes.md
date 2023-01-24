https://restfulapi.net/http-status-codes/

# HTTP Status Codes

HTTP defines these standard status codes that can be used to convey the results of a client's request. The status codes are divided into five categories.
- ***1xx: Informational*** - communicates transfer protocol-level information.
- ***2xx: Success*** - indicates that the client's request was accepted successfully.
- ***3xx: Redirection*** - indicates that the client must take some additional action in order to complete their request.
- ***4xx: Client Error*** - this category of erro status codes points the finger at clients.
- ***5xx: Server Error*** - the server takes responsibility for these error status codes.


## REST Specific HTTP Status Codes

---
### 200 (OK)
It indicates that the REST API successfully carried out whatever action the client requested and that no more specific code in the 2xx series is appropriate.
Unlike 204 status code, a 200 response should include a response body. The information returned with the response is dependent on the method used in the request, for example:
- GET an entity corresponding to the requested resource is sent in the response;
- HEAD the entity-header fields corresponding to the requested resource are sent in the response without any message-body;
- POST an entity describing or containing the result of the action;
- TRACE an entity containing the request message as received by the end server.

---
### 201 (Created)
A REST API responds with the 201 status code whenever a resource is created inside collection. There may also be times when a new resource is created as a result of some controller action, in which case 201 whould also be an approptiate response.
The newly create resource can be referenced by the URI(s) returned in the entity of the response, with the most specific URI for the resouce given by a Location header field.
The origin server MUST create the resource before returning the 201 satus code. If the action cannot be carried out immediately, the server SHOULD respond with 202 (Accepted) response instead.

---
### 202 (Accepted)
A 202 response is typically used for actions that take a long while to process. It indicates that the request has been accepted for processing, but the processing has not been completed. The request might or might not be eventually acted upon, or even maybe disallowed when processing occurs.
The entity returned with this response SHOULD include an indication of the request's current status and either a pointer to a status monitor (job queue location) or some estimate of when the user can expect the request to be fulfilled.

---
### 204 (No Content)
The 204 status code is usually sent out in response to a **PUT, POST, or DELETE** request when the REST API declines to send back any status message or representation in the response message’s body.
An API may also send 204 in conjunction with a GET request to indicate that the requested resource exists, but has no state representation to include in the body.
This response is primarily intended to allow input for actions to take place without causing a change to the user agent’s active document view. However, any new or updated metainformation SHOULD be applied to the document currently in the user agent’s dynamic view.
The 204 response MUST NOT include a message-body and thus is always terminated by the first empty line after the header fields.

---
### 301 (Moved Permanently)
The 301 status code indicates that the REST API’s resource model has been significantly redesigned, and a new permanent URI has been assigned to the client’s requested resource. The REST API should specify the new URI in the response’s Location header, and all future requests should be directed to the given URI.
You will hardly use this response code in your API as you can always use the API versioning for the new API while retaining the old one.

---
### 302 (Found)
The HTTP response status code 302 Found is a common way of performing URL redirection. An HTTP response with this status code will additionally provide a URL in the Location header field. The user agent (e.g., a web browser) is invited by a response with this code to make a second. Otherwise identical, request to the new URL specified in the location field.
Many web browsers implemented this code in a manner that violated this standard, changing the request type of the new request to GET, regardless of the type employed in the original request (e.g., POST). RFC 1945 and RFC 2068 specify that the client is not allowed to change the method on the redirected request. The status codes 303 and 307 have been added for servers that wish to make unambiguously clear which kind of reaction is expected of the client.

---
### 303 (See Other)
A 303 response indicates that a controller resource has finished its work, but instead of sending a potentially unwanted response body, it sends the client the URI of a response resource. The response can be the URI of the temporary status message, or the URI to some already existing, more permanent, resource.
Generally speaking, the 303 status code allows a REST API to send a reference to a resource without forcing the client to download its state. Instead, the client may send a GET request to the value of the Location header.
The 303 response MUST NOT be cached, but the response to the second (redirected) request might be cacheable.

---
### 304 (Not Modified)
This status code is similar to 204 (“No Content”) in that the response body must be empty. The critical distinction is that 204 is used when there is nothing to send in the body, whereas 304 is used when the resource has not been modified since the version specified by the request headers If-Modified-Since or If-None-Match.
In such a case, there is no need to retransmit the resource since the client still has a previously-downloaded copy.
Using this saves bandwidth and reprocessing on both the server and client, as only the header data must be sent and received in comparison to the entirety of the page being re-processed by the server, then sent again using more bandwidth of the server and client.

---
### 400 (Bad Request)
400 is the generic client-side error status, used when no other 4xx error code is appropriate. Errors can be like malformed request syntax, invalid request message parameters, or deceptive request routing etc.
The client SHOULD NOT repeat the request without modifications.

---
### 401 (Unauthorized)
A 401 error response indicates that the client tried to operate on a protected resource without providing the proper authorization. It may have provided the wrong credentials or none at all. The response must include a WWW-Authenticate header field containing a challenge applicable to the requested resource.
The client MAY repeat the request with a suitable Authorization header field. If the request already included Authorization credentials, then the 401 response indicates that authorization has been refused for those credentials. If the 401 response contains the same challenge as the prior response, and the user agent has already attempted authentication at least once, then the user SHOULD be presented the entity that was given in the response, since that entity might include relevant diagnostic information.

---
### 403 (Forbidden)
A 403 error response indicates that the client’s request is formed correctly, but the REST API refuses to honor it, i.e., the user does not have the necessary permissions for the resource. A 403 response is not a case of insufficient client credentials; that would be 401 (“Unauthorized”).
Authentication will not help, and the request SHOULD NOT be repeated. Unlike a 401 Unauthorized response, authenticating will make no difference.

---
### 404 (Not Found)
The 404 error status code indicates that the REST API can’t map the client’s URI to a resource but may be available in the future. Subsequent requests by the client are permissible.
No indication is given of whether the condition is temporary or permanent. The 410 (Gone) status code SHOULD be used if the server knows, through some internally configurable mechanism, that an old resource is permanently unavailable and has no forwarding address. This status code is commonly used when the server does not wish to reveal exactly why the request has been refused, or when no other response is applicable.

---
### 405 (Method Not Allowed)
The API responds with a 405 error to indicate that the client tried to use an HTTP method that the resource does not allow. For instance, a read-only resource could support only GET and HEAD, while a controller resource might allow GET and POST, but not PUT or DELETE.
A 405 response must include the Allow header, which lists the HTTP methods that the resource supports. For example:
>Allow: GET, POST

---
### 406 (Not Acceptable)
The 406 error response indicates that the API is not able to generate any of the client’s preferred media types, as indicated by the Accept request header. For example, a client request for data formatted as application/xml will receive a 406 response if the API is only willing to format data as application/json.
If the response could be unacceptable, a user agent SHOULD temporarily stop receipt of more data and query the user for a decision on further actions.

---
### 500 (Internal Server Error)
500 is the generic REST API error response. Most web frameworks automatically respond with this response status code whenever they execute some request handler code that raises an exception.
A 500 error is never the client’s fault, and therefore, it is reasonable for the client to retry the same request that triggered this response and hope to get a different resp

---
### 501 (Not Implemented)
The server either does not recognize the request method, or it cannot fulfill the request. Usually, this implies future availability (e.g., a new feature of a web-service API
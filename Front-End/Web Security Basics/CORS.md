
> [!info]
> **CORS (Cross-Origin Resource Sharing)** is a security feature implemented by web browsers to control how web pages can request resources from a different `origin` (domain, protocol, or port) than the one that served the web page. It is a mechanism that allows servers to specify who can access their resources and under what conditions, also CORS is a **mechanism to relax [[SOP]]**

---
## **How does it work?**

When a browser makes a **cross-origin request**, it adds an `Origin` header to the message. The server responds by adding an `Access-Control-Allow-Origin` to the response message. The value in the response header should match the value of the `Origin` header from the request. If it does match, everything is fine, but if it doesn't, browsers prevent the response data from being shared with the client, and the CORS error occurs.

![[understanding-cors-1.svg]]

![[understanding-cors-2.svg]]


Requests that use methods other than `GET`, `POST`, `HEAD`, or requests with non-standard headers, need to be pre-flighted. When making these requests, browsers will send a pre-flight request using the `OPTIONS` HTTP method, and servers will respond with the `Access-Control-Allow-Origin` and the `Access-Control-Allow-Methods` headers. If both headers match the request origin and method, the actual request can be made. Such cross-origin requests are pre-flighted because they may have implications for server data.

![[understanding-cors-3.svg]]

![[understanding-cors-4.svg]]


> [!attention]
> You may be asking why the `POST` method does not make a pre-flight request since it may also change server data. This is because browsers already allowed cross-origin `POST` requests with standard headers before CORS existed

---

## **Key CORS Headers**

1. **`Access-Control-Allow-Origin`**:
    
    - Specifies which origins are allowed to access the resource.
        
    - Example: `Access-Control-Allow-Origin: https://example.com` or `Access-Control-Allow-Origin: *` (allows all origins).
        
2. **`Access-Control-Allow-Methods`**:
    
    - Specifies which HTTP methods (e.g., GET, POST, PUT) are allowed.
        
    - Example: `Access-Control-Allow-Methods: GET, POST, PUT`.
        
3. **`Access-Control-Allow-Headers`**:
    
    - Specifies which HTTP headers can be used in the actual request.
        
    - Example: `Access-Control-Allow-Headers: Content-Type, Authorization`.
        
4. **`Access-Control-Allow-Credentials`**:
    
    - Indicates whether the request can include credentials (e.g., cookies, authorization headers).
        
    - Example: `Access-Control-Allow-Credentials: true`.
        
5. **`Access-Control-Max-Age`**:
    
    - Specifies how long (in seconds) the results of a preflight request can be cached.
        
    - Example: `Access-Control-Max-Age: 86400`.

---

## **Types of CORS Requests**

### 1- Simple Requests

These requests do not trigger a preflight check

**Conditions**:-
- The HTTP method is GET, POST, or HEAD.
- The request headers are limited to `Accept`, `Accept-Language`, `Content-Language`, `Content-Type` (with values `application/x-www-form-urlencoded`, `multipart/form-data`, or `text/plain`).

> [!example]
> A GET request to fetch data from an API.


### 2- Preflight Requests

These requests trigger a preflight check (OPTIONS request) before the actual request is sent.

**Conditions**:-
- The HTTP method is not GET, POST, or HEAD (e.g., PUT, DELETE).
- The request includes custom headers (e.g., `Authorization`).
- The `Content-Type` is not one of the allowed values for simple requests.

> [!example]
> A PUT request with a JSON payload.

---

### **Example of a CORS Request**

###  Frontend (Browser)

``` js
fetch('https://api.example.com/data', {
  method: 'GET',
  headers: {
    'Content-Type': 'application/json',
  },
  credentials: 'include', // Include cookies
})
.then(response => response.json())
.then(data => console.log(data))
.catch(error => console.error(error));
```

#### **Backend (Server)**

*The server must include the appropriate CORS headers in its response:*

``` php
Access-Control-Allow-Origin: https://your-frontend.com
Access-Control-Allow-Methods: GET, POST, PUT
Access-Control-Allow-Headers: Content-Type, Authorization
Access-Control-Allow-Credentials: true
```


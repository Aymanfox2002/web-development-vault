

> [!info]
> **Same-Origin Policy (SOP):** Protects users by preventing web pages from accessing resources (e.g., data, cookies, or scripts) from a different origin (domain, protocol, or port) than the one that served the web page.


---
## **SOP VS CORS**

*The **Same-Origin Policy (SOP)** and **Cross-Origin Resource Sharing (CORS)** are closely related but serve different purposes, **Example to Clarify***:

> [!example]
> Imagine you have:
> 
> - A front-end application hosted at `https://example.com`.
>     
> - An API hosted at `https://api.example.com`.
>     
> 
> #### **Without CORS**:
> 
> - The browser blocks requests from `https://example.com` to `https://api.example.com` due to SOP.
>     
> 
> #### **With CORS**:
> 
> - The server at `https://api.example.com` includes the header:
> ```HTTP
> Access-Control-Allow-Origin: https://example.com
> ```
> 
> - The browser allows requests from `https://example.com` to `https://api.example.com`.


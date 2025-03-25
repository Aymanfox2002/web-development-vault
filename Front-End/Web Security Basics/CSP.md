
> [!info]
> **Content Security Policy (CSP):** Content Security Policy (CSP) is a security feature that helps prevent **cross-site scripting (XSS), data injection, and other attacks** by controlling which resources a web page can load. It acts as a **whitelist** of trusted sources for scripts, styles, and other content.


---

## Why is CSP Important?

- **Prevents XSS Attacks** – Blocks malicious scripts injected into your site.
- **Mitigates Data Injection Attacks** – Restricts unauthorized data loading.
- **Enhances Website Security** – Ensures only trusted resources are executed

---

## How to Implement CSP?

*CSP is enforced through the **`Content-Security-Policy` HTTP header** or a **meta tag** in the HTML document, so, we will take meta tag method in this lesson*

> [!warning]
> consider **meta tag** method is less secure than **HTTP header** method

Instead of setting CSP rules in the HTTP headers (which requires server-side configuration), you can add them directly in your HTML `<head>` section like this:

``` html
<meta http-equiv="Content-Security-Policy" content="default-src 'self';">
```

This table defines CSP directives:

| **<mark class="hltr-g">Directive</mark>** | **<mark class="hltr-b">What It Controls</mark>** | **<mark class="hltr-p">Example Usage</mark>**   |
| ----------------------------------------- | ------------------------------------------------ | ----------------------------------------------- |
| `default-src`                             | Default for all resources                        | `default-src 'self';`                           |
| `script-src`                              | JavaScript sources                               | `script-src 'self' https://apis.google.com;`    |
| `style-src`                               | CSS sources                                      | `style-src 'self' 'unsafe-inline';`             |
| `img-src`                                 | Image sources                                    | `img-src 'self' https://cdn.example.com;`       |
| `font-src`                                | Font sources                                     | `font-src 'self' https://fonts.googleapis.com;` |
| `connect-src`                             | API & WebSocket                                  | `connect-src 'self' https://api.example.com;`   |
| `frame-src`                               | Allowed iframes                                  | `frame-src 'self' https://www.youtube.com;`     |

***Example of a Secure CSP Meta Tag***

> [!example]
> ```html
> <meta http-equiv="Content-Security-Policy" 
>       content="default-src 'self'; 
>                script-src 'self' https://apis.google.com; 
>                style-src 'self' 'unsafe-inline'; 
>                img-src 'self' data: https://cdn.example.com;">
> 
> ```
> 

---
## Blocking Inline JavaScript for More Security

To prevent inline `<script>` tags and `onclick=""` events, you can use:

``` html
<meta http-equiv="Content-Security-Policy"
      content="default-src 'self'; script-src 'self';">
```

🚨 This will **block** any inline scripts. To fix it, you can use **nonce-based** scripts:

``` html
<meta http-equiv="Content-Security-Policy" 
      content="script-src 'self' 'nonce-random123';">

```

Then, use the same nonce (`random123`) inside your script tag:

```html
<script nonce="random123">
  console.log('This script is allowed!');
</script>
```

The browser will now **only** execute scripts with the correct `nonce`.
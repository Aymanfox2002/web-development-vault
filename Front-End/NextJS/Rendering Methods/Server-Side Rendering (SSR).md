## **What is it?**

*SSR means the page is generated on the **server** for each request. The server fetches data, renders the page, and sends the fully built HTML to the client.*

---

## **How it works?**

1. **User Requests a Page** → A user visits a page in their browser.  
2. **Next.js Server Receives Request** → The server detects that the page uses SSR (`getServerSideProps`).  
3. **Data Fetching & Processing** → The server fetches necessary data (e.g., from a database or API).  
4. **HTML Generation** → The server renders the page into an HTML response with the fetched data.  
5. **Send Response to Browser** → The fully rendered HTML page is sent to the client.  
6. **Hydration (Optional)** → React hydrates the page to add interactivity if needed.

![[Capture.PNG|816x459]]

> [!warning] Note
> Faster first load, always fresh data, but **slightly slower response time** compared to static pages

---
## **How to use SSR?**

*To enable SSR in Next.js 15, we use the **`getServerSideProps()`** function inside a page.*

```js
export async function getServerSideProps() {
  const res = await fetch("https://api.example.com/data");
  const data = await res.json();

  return {
    props: { data }, // This will be passed to the component as props
  };
}

export default function SSRPage({ data }) {
  return (
    <div>
      <h1>Server-Side Rendered Data</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}

```

### **What’s Happening Here?**

 1. **`getServerSideProps()` runs on the server before the page is sent to the browser.**  
 2. It fetches data from an API **every time the page is requested**.  
 3. The server **renders the page with the fresh data** and sends the HTML to the client.


---
## **When to use SSR?**

- Pages that require **up-to-date** data for every request (e.g., stock prices, weather data).
- Better **SEO** since the page is fully loaded before it reaches the browser.


> [!warning]
> **Drawback:** Slower response times because the server processes every request.

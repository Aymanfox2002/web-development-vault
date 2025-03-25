
> [!info] what is it?
> Next.js **Server Components** are a powerful feature introduced to optimize performance and reduce client-side JavaScript. They allow components to run on the server while dynamically rendering HTML and fetching data efficiently.

---

## **1️⃣ What Are Server Components?**

🔹 **Run on the server** → They don’t send JavaScript to the client.  
🔹 **Faster page loads** → Reduce bundle size since logic stays on the server.  
🔹 **Better security** → Sensitive logic like database access isn’t exposed.  
🔹 **Can fetch data directly** → No need for API endpoints in many cases.

---

## **2️⃣ How to Create a Server Component**

Server Components are **default** in the `app/` directory of Next.js. You simply use a normal React component **without `"use client"`**.

```js
async function ProductsList() {
  const res = await fetch("https://fakestoreapi.com/products");
  const products = await res.json();

  return (
    <ul>
      {products.map((product) => (
        <li key={product.id}>{product.title}</li>
      ))}
    </ul>
  );
}

export default ProductsList;
```


> [!example]- **📌 How it works:**  
> 
> ✔️ Runs on the server → No client-side JS needed.  
> ✔️ Fetches **products** directly → No need for API routes.  
> ✔️ Returns **HTML** → Sent to the client as pre-rendered content.

---

## **3️⃣ When to Use Server Components?**

✅ **Fetching data from a database or API**  
✅ **Rendering large lists of items**  
✅ **Hiding sensitive logic (authentication, database queries, etc.)**  
✅ **Reducing JavaScript bundle size for performance optimization**

---

## **4️⃣ Combining Server & Client Components**

You can **mix Server & Client Components** in Next.js.

### ✅ **Example: Using a Client Component Inside a Server Component**

#### **🔹 Server Component (Parent)**

```javascript
import ClientButton from "./ClientButton"; // Import client component

export default function Page() {
  return (
    <div>
      <h1>Server Component Page</h1>
      <ClientButton />
    </div>
  );
}
```

#### **🔹 Client Component (Child)**

```javascript
"use client"; // Must be a client component

export default function ClientButton() {
  return <button onClick={() => alert("Clicked!")}>Click Me</button>;
}
```


> [!example]- **📌 How it works:**
> - The **page and data** load **server-side**.
> - The button stays interactive **client-side**.
> - The **"use client"** directive tells Next.js it needs JavaScript.


>Try to know when to use **[[Client Components#5️⃣ Client Components vs. Server Components|Client or Server Components]]** 

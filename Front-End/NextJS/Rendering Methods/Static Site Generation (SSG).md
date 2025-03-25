
## **1️⃣ What is Static Site Generation (SSG)?**

**SSG (Static Site Generation)** is a rendering method where pages are **pre-built** at build time and served as static HTML. This results in **blazing-fast performance** since no backend processing is needed when a user requests the page.

**📌 Key Benefits:**  
✅ Extremely fast loading times.  
✅ Great for **SEO** (since pages are fully rendered before they reach the browser).  
✅ Reduced server load (because the page doesn’t need to be rebuilt for every request).  
✅ Can be combined with **Incremental Static Regeneration (ISR)** to update pages periodically.

---

## **2️⃣ When to Use SSG?**

🔹 **Ideal for pages that don’t change frequently**, such as:

- Blogs & articles 📝
- Product pages 🛍️
- Documentation 📄
- Marketing pages 📢

🔹 **Not suitable for pages that require real-time data updates**, such as:

- User dashboards
- Personalized content (e.g., “Hello, John”)

---

## **3️⃣ How to Use Static Site Generation (SSG) in Next.js 15?**

To generate static pages in **Next.js 15**, we use the function:

```javascript
export async function getStaticProps() {
  // Fetch data at build time
  const res = await fetch("https://api.example.com/data");
  const data = await res.json();

  return {
    props: { data }, // Pass data as props to the page
  };
}
```

📌 **Key Points:**

- This function **only runs at build time**.
- The page is pre-rendered and served **as a static HTML file**.
- The data is **not fetched on every request**, which makes it super fast!

---

## **4️⃣ Example: Creating an SSG Page in Next.js 15**

### **Step 1: Fetching Data at Build Time**

Create a new file in your Next.js **pages** directory:

📂 `/app/products/page.js`

```javascript
export async function getStaticProps() {
  const res = await fetch("https://fakestoreapi.com/products");
  const products = await res.json();

  return {
    props: { products },
  };
}

export default function ProductsPage({ products }) {
  return (
    <div>
      <h1>Product List</h1>
      <ul>
        {products.map((product) => (
          <li key={product.id}>{product.title}</li>
        ))}
      </ul>
    </div>
  );
}
```

**📝 What’s happening here?**  
1️⃣ `getStaticProps()` fetches product data **at build time**.  
2️⃣ The `products` data is **passed as props** to the component.  
3️⃣ The page is **statically generated** and ready to be served as a **pre-built HTML file**.

---

## **5️⃣ Dynamic SSG Pages with `getStaticPaths`**

Sometimes, you need **dynamic** pages that are still pre-generated (e.g., `/products/[id]`).  
For that, you use **`getStaticPaths()`**.

### **Example: Generating Static Product Pages**

📂 `/app/products/[id].js`

```javascript
export async function getStaticPaths() {
  const res = await fetch("https://fakestoreapi.com/products");
  const products = await res.json();

  // Create paths for each product
  const paths = products.map((product) => ({
    params: { id: product.id.toString() },
  }));

  return { paths, fallback: false };
}

export async function getStaticProps({ params }) {
  const res = await fetch(`https://fakestoreapi.com/products/${params.id}`);
  const product = await res.json();

  return { props: { product } };
}

export default function ProductDetail({ product }) {
  return (
    <div>
      <h1>{product.title}</h1>
      <p>{product.description}</p>
    </div>
  );
}
```

### **What’s Happening?**

1️⃣ **`getStaticPaths()`** generates paths for all products **at build time**.  
2️⃣ **`getStaticProps()`** fetches data for each product page.  
3️⃣ The pages are statically generated and served as **pre-built HTML files**.

📌 **Fallback Behavior in `getStaticPaths()`**

- `fallback: false` → Returns a **404 error** if the page doesn’t exist.
- `fallback: true` → Generates the page **on-demand** if it wasn’t built yet.

---

## **6️⃣ Handling Data Updates with [[Incremental Static Regeneration (ISR) | ISR]]**

Since SSG pages are **pre-built**, they don’t update unless you **rebuild the app**.  
To update them **without redeploying**, use **Incremental Static Regeneration (ISR)** with `revalidate`.

### **Example: Using `revalidate` to Refresh Static Content**

```javascript
export async function getStaticProps() {
  const res = await fetch("https://api.example.com/data");
  const data = await res.json();

  return {
    props: { data },
    revalidate: 60, // Regenerate page every 60 seconds
  };
}
```

🚀 **Now, the page updates every 60 seconds** without needing a full rebuild!

---

## **7️⃣ Key Takeaways**

|Feature|Description|
|---|---|
|**SSG (Static Site Generation)**|Pre-builds HTML at **build time**|
|**Best for**|Blog posts, product pages, docs|
|**Performance**|🚀 Super fast (served as static files)|
|**SEO**|✅ Excellent (fully rendered content)|
|**Updates**|❌ Needs manual rebuild (or use ISR)|
|**Dynamic Pages**|✅ Can use `getStaticPaths()`|

---

## **8️⃣ When Should You Use SSG?**

✅ **Use SSG when:**

- You have content that **doesn’t change frequently**.
- You need **fast page loads** and **good SEO**.
- You want **low server costs** (static files are easy to serve).

❌ **Avoid SSG when:**

- The data **changes frequently** (use [[Incremental Static Regeneration (ISR) | ISR]] instead).
- You need **personalized content** per user (use SSR or CSR).

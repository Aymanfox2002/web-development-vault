

Next.js 15 uses a **file-based routing system**, meaning the folder structure inside `app/` (for the App Router) or `pages/` (for the Pages Router) determines the routes of your application. Here, we will cover the four main types of routing in Next.js 15: **Dynamic Routing, Nested Routes, Layouts, and Middleware**.

---

## **1️⃣ Dynamic Routing**

Dynamic routes allow us to create pages with variable segments, such as `products/[id].js`, where `[id]` is a dynamic parameter.

### **Example: Creating a Dynamic Route**

📂 **Folder structure:**

```plaintext
app/
 ├── products/
 │   ├── [id]/
 │   │   ├── page.js
```

📜 ``

```javascript
export default async function ProductPage({ params }) {
  const { id } = await params;
  return <h1>Product ID: {id}</h1>;
}
```

👉 URL Example: `/products/123` → Displays `Product ID: 123`

---

## **2️⃣ Nested Routes**

Nested routes allow you to create hierarchical URL structures using folders.

### **Example: Blog with Nested Routes**

📂 **Folder structure:**

```plaintext
app/
 ├── blog/
 │   ├── page.js       (Main blog page → `/blog`)
 │   ├── posts/
 │   │   ├── [slug]/
 │   │   │   ├── page.js  (Single blog post → `/blog/posts/:slug`)
```

📜 

```javascript
export default function BlogPage() {
  return <h1>Welcome to the Blog</h1>;
}
```

📜

```js
export default async function BlogPost({ params }) {
    const { slug } = await params;
  return <h1>Post: {slug}</h1>;
}
```

👉 URL Example: `/blog/posts/nextjs-tips` → Displays `Post: nextjs-tips`

---

## **3️⃣ Layouts in Next.js 15**

Layouts allow you to **reuse UI elements** (like headers and footers) across multiple pages.

📂 **Folder structure:**

```plaintext
app/
 ├── layout.js        (Global Layout)
 ├── dashboard/
 │   ├── layout.js    (Dashboard Layout)
 │   ├── page.js      (Dashboard Home → `/dashboard`)
```

📜 ``** (Global Layout)**

```javascript
export default function RootLayout({ children }) {
  return (
    <html>
      <body>
        <nav>Global Navbar</nav>
        {children}
      </body>
    </html>
  );
}
```

📜 ``** (Dashboard-Specific Layout)**

```javascript
export default function DashboardLayout({ children }) {
  return (
    <div>
      <aside>Sidebar</aside>
      <main>{children}</main>
    </div>
  );
}
```

👉 URL Example: `/dashboard` → Includes both the **Global Navbar** and **Sidebar**.

---

## **4️⃣ Middleware in Next.js 15**

Middleware lets you run **code before a request is completed**, useful for authentication, redirects, and logging.

📜 **Creating ******************************************************************``****************************************************************** directory:**

```javascript
import { NextResponse } from "next/server";

export function middleware(request) {
  const loggedIn = request.cookies.get("token");
  if (!loggedIn) {
    return NextResponse.redirect("/login");
  }
  return NextResponse.next();
}

export const config = {
  matcher: "/dashboard/:path*", // Protects all `/dashboard` routes
};
```

👉 If a user visits `/dashboard` without a token, they are redirected to `/login`.

---

### **Conclusion**

✅ **Dynamic Routing**: Create flexible URLs using `[id]` or `[slug]`. ✅ **Nested Routes**: Organize routes using folders. ✅ **Layouts**: Share UI components across multiple pages. ✅ **Middleware**: Control request flow before rendering a page.

Would you like a hands-on example for these features? 🚀
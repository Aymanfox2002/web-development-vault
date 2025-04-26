

## **🔹 What Are HTTP Methods?** 

HTTP methods define **how** we interact with API routes. In Next.js 15, API routes are built inside the **App Router (`app/api/`)** and support multiple HTTP methods:

|**Method**|**Purpose**|**Example Use Case**|
|---|---|---|
|**GET**|Retrieve data|Fetching user details|
|**POST**|Send data|Creating a new user|
|**PUT**|Update data|Replacing an existing resource|
|**PATCH**|Modify data|Partially updating a resource|
|**DELETE**|Remove data|Deleting a user|

---

## **🔹 Creating an API Route in Next.js 15**

API routes are now written inside **`app/api/your-route/route.js`** instead of `pages/api/`.

📌 **Example:**

```bash
app/api/products/route.js
```

🔹 **Basic API Route Handling Different HTTP Methods**

```javascript
export async function GET() {
  return new Response(JSON.stringify({ message: "Fetching all products" }), {
    headers: { "Content-Type": "application/json" },
  });
}

export async function POST(req) {
  const data = await req.json(); // Read request body
  return new Response(JSON.stringify({ message: "Product created", data }), {
    headers: { "Content-Type": "application/json" },
  });
}

export async function PUT(req) {
  const data = await req.json();
  return new Response(JSON.stringify({ message: "Product updated", data }), {
    headers: { "Content-Type": "application/json" },
  });
}

export async function DELETE() {
  return new Response(JSON.stringify({ message: "Product deleted" }), {
    headers: { "Content-Type": "application/json" },
  });
}
```

---

## **🔹 Understanding Each HTTP Method and how to use them in client side**

### **1️⃣ GET - Fetching Data**

- Used to retrieve data from the server.
    
- No request body is required.
    

📌 **Example API Route: `app/api/products/route.js`**

```javascript
export async function GET() {
  return new Response(JSON.stringify({ products: ["Laptop", "Phone"] }), {
    headers: { "Content-Type": "application/json" },
  });
}
```

📌 **Client Request (Fetching Data)**

```javascript
fetch("/api/products")
  .then((res) => res.json())
  .then((data) => console.log(data));
```

---

### **2️⃣ POST - Creating Data**

- Sends new data to the server.
    
- Requires a request body.
    

📌 **Example API Route:**

```javascript
export async function POST(req) {
  const data = await req.json();
  return new Response(JSON.stringify({ message: "Product added", data }), {
    headers: { "Content-Type": "application/json" },
  });
}
```

📌 **Client Request (Sending Data)**

```javascript
fetch("/api/products", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ name: "Tablet", price: 299 }),
})
  .then((res) => res.json())
  .then((data) => console.log(data));
```

---

### **3️⃣ PUT - Updating Data (Full Replace)**

- Used to completely replace a resource.
    
- Requires a request body.
    

📌 **Example API Route:**

```javascript
export async function PUT(req) {
  const data = await req.json();
  return new Response(JSON.stringify({ message: "Product updated", data }), {
    headers: { "Content-Type": "application/json" },
  });
}
```

📌 **Client Request (Updating Data)**

```javascript
fetch("/api/products", {
  method: "PUT",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ id: 1, name: "Smartphone", price: 599 }),
})
  .then((res) => res.json())
  .then((data) => console.log(data));
```

---

### **4️⃣ PATCH - Modifying Part of a Resource**

- Used for partial updates.
    

📌 **Example API Route:**

```javascript
export async function PATCH(req) {
  const data = await req.json();
  return new Response(JSON.stringify({ message: "Product partially updated", data }), {
    headers: { "Content-Type": "application/json" },
  });
}
```

📌 **Client Request (Partial Update)**

```javascript
fetch("/api/products", {
  method: "PATCH",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ id: 1, price: 499 }),
})
  .then((res) => res.json())
  .then((data) => console.log(data));
```

---

### **5️⃣ DELETE - Removing Data**

- Deletes a resource.


📌 **Example API Route:**

```javascript
export async function DELETE() {
  return new Response(JSON.stringify({ message: "Product deleted" }), {
    headers: { "Content-Type": "application/json" },
  });
}
```

📌 **Client Request (Deleting Data)**

```javascript
fetch("/api/products", {
  method: "DELETE",
})
  .then((res) => res.json())
  .then((data) => console.log(data));
```

---

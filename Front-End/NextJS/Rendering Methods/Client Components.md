

> [!info] What is it?
> Client Components in Next.js allow you to create interactive UI elements that run in the browser. Unlike Server Components, they send JavaScript to the client, making them essential for dynamic interactions like handling user input, animations, and state management.

---

## **1️⃣ What Are Client Components?**

🔹 **Run in the browser** → They execute JavaScript on the client side.  
🔹 **Enable interactivity** → Used for forms, buttons, modals, etc.  
🔹 **Use hooks (`useState`, `useEffect`)** → Unlike Server Components.  
🔹 **Must include `"use client"`** → Tells Next.js it needs client-side execution.

---

## **2️⃣ How to Create a Client Component**

To define a Client Component, add `"use client"` at the top of the file.

### ✅ **Example: Counter Component (Client-Side)**

```javascript
"use client"; // Marks this as a Client Component

import { useState } from "react";

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

> [!example]- **📌 How it works:**  
> **📌 How it works:**  
> ✔️ Uses `useState` → Only possible in Client Components.  
> ✔️ Updates UI dynamically → Runs in the browser.  
> ✔️ `"use client"` is **required**, otherwise, Next.js treats it as a Server Component.

---

## **3️⃣ When to Use Client Components?**

✅ **Handling user input** (buttons, forms, dropdowns)  
✅ **Using state (`useState`, `useEffect`, `useContext`)**  
✅ **Animations and transitions**  
✅ **Integrating third-party libraries** (Charts, Maps, etc.)


---

## **5️⃣ Client Components vs. Server Components**

|Feature|Client Components 🎨|Server Components 🚀|
|---|---|---|
|**Runs on**|Client (browser)|Server|
|**Used for**|Interactivity (buttons, forms, etc.)|Data fetching, pre-rendered UI|
|**JavaScript sent?**|Yes (increases bundle size)|No (smaller bundle size)|
|**Can use hooks?**|Yes (`useState`, `useEffect`)|No|
|**Can fetch data?**|Yes, but not optimal|Yes, best for data fetching|

---

> [!important] Good to know
> learn how to use **[[Server Components#4️⃣ Combining Server & Client Components |  Combining Server & Client Components]]**

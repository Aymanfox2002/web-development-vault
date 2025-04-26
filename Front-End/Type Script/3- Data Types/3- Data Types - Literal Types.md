### 🔹 What Are Literal Types?

**Literal types** allow you to specify the **exact value** a variable or parameter can have — **not just the type**, but the **specific value**.

They are often used to **limit** what values can be assigned, and are great for **safety and validation**.

---

### 🧪 Example:

```ts
let direction = "left" | "right" | "up" | "down";

direction = "left";   // ✅ OK
direction = "up";     // ✅ OK
direction = "top";    // ❌ Error: not assignable
```

---

### 🔹 Why Use Literal Types?

✅ **Restrict values** to a fixed set  
✅ **Avoid bugs** from invalid inputs  
✅ Improve **code readability and autocomplete**  
✅ Combine well with `type` aliases and functions

---

### 🧩 Real-World Example:

```ts
type ButtonSize = "small" | "medium" | "large";

function createButton(size: ButtonSize) {
  console.log(`Button size is ${size}`);
}

createButton("medium");  // ✅
createButton("huge");    // ❌ Error
```

---

### 🔧 With Numbers & Booleans:

```ts
let statusCode: 200 | 404 | 500;
statusCode = 404;     // ✅
statusCode = 401;     // ❌
```

```ts
let isLive: true;
isLive = true;        // ✅
isLive = false;       // ❌
```

---

### **:LiChevronsRight: [[4- Data Types - Tuple|Next lesson]]** 
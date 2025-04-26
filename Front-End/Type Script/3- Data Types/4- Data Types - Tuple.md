## 📌 What is a Tuple?

A **tuple** is a special type of array in TypeScript where:

- **The number of elements is fixed**
    
- **Each element has a specific type and position**

It’s like an array, but more **structured and strict**.

---

## 🧪 Basic Example

```ts
let user: [number, string, boolean] = [1, "Ayman", true];
```

Here’s what each part means:

|Position|Type|Example Value|
|---|---|---|
|0|`number`|`1`|
|1|`string`|`"Ayman"`|
|2|`boolean`|`true`|

You **must respect the type and order**:

```ts
user = ["Ayman", 1, true]; // ❌ Wrong order
user = [2, "Alex"];        // ❌ Missing value
user = [2, "Alex", true];  // ✅ Correct
```

---

## 🧠 Why Use Tuples?

✅ Better control over array structure  
✅ Good for returning multiple, structured values from functions  
✅ Useful when the position has meaning (e.g., `[x, y]`, `[statusCode, message]`)

---

## 🛠 Real Example: Return Multiple Values

```ts
function getUserInfo(): [string, number] {
  return ["Ayman", 25];
}

const [name, age] = getUserInfo();
```

how this [[Data Types - Tuple Example | code work?]]

---
## Why this work and that not?

```ts
let article: [number, string, boolean] = [11, "Title One", true];

// ❌ Assignment
article = [12, "Title Two", false, 23]; // Error

// ✅ Mutation
article.push(100); // No Error
```

[[Data Types - Tuple Example 2 |the answer]]

---
## 🔄 Tuple vs Array

|Feature|Tuple|Regular Array|
|---|---|---|
|Fixed Length|✅ Yes|❌ No|
|Type Order|✅ Enforced|❌ Flexible|
|Push/Pop|✅ Allowed (but unsafe)|✅ Allowed|

---

## 🔐 Prevent Modifying Tuple Length

Use `readonly`:

```ts
let data: readonly [number, string] = [10, "done"];
data.push("extra"); // ❌ Error
```

---

## 🔥 Tuple with Optional Elements

```ts
let tuple: [number, string?, boolean?];
tuple = [1]; // ✅
tuple = [1, "Hi"]; // ✅
tuple = [1, "Hi", true]; // ✅
```

---

### **:LiChevronsRight: [[5- Data Types - Void And Never|Next lesson]]** 
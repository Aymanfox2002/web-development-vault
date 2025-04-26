### 🔹 What Is It?

`void` is used when a function **does not return a value**.

```ts
function logMessage(message: string): void {
  console.log(message);
}
```

### 🔹 When to Use It?

- For functions that **perform an action** but don’t return anything.
    
- Example: `console.log`, showing a message, updating UI, etc.
    

### 🔹 Key Points

- Can only return `undefined` or nothing.
    
- Common in event handlers, logging, etc.
    

```ts
function showAlert(): void {
  alert("This is an alert!");
}
```

---

## ❌ `never` Type

### 🔹 What Is It?

`never` represents **a value that will never occur**.

You use it when:

- A function **never finishes** (e.g., infinite loop).
    
- A function **always throws an error**.


```ts
function throwError(msg: string): never {
  throw new Error(msg);
}
```

```ts
function infiniteLoop(): never {
  while (true) {}
}
```

### 🔹 When to Use It?

- To indicate that the function **doesn’t return anything at all—not even `undefined`**.
    
- Usually for error handling or intentional never-ending processes.

---
## 🧠 Comparison Table

|Feature|`void`|`never`|
|---|---|---|
|Returns a value?|No|No|
|Can return `undefined`?|Yes|No|
|Use case|No return (but completes)|Throws error / never finishes|
|Example|`function sayHi(): void {}`|`function crash(): never {}`|

---
### **:LiChevronsRight: [[6- Data Types - Enums|Next lesson]]** 
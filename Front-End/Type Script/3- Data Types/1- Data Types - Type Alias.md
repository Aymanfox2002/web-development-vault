
### ✅ What is a Type Alias?

A **type alias** lets you create a custom name for a **type** (primitive, object, union, etc.).

```ts
type Username = string;
let user: Username = "Ayman";
```

---

### ✅ Why Use Type Aliases?

- Make complex types easier to read and reuse
    
- Improve code readability and structure

---

### ✅ Examples

#### 🔹 Primitive Alias

```ts
type num = number;
let myAge: num = 25;
```

#### 🔹 Union Type Alias

```ts
type ID = string | number;
let userId: ID = 101;
userId = "abc123";
```

---
### **:LiChevronsRight: [[2- Data Types - Type Alias Advanced|Next lesson]]** 



### ✅ **What Are Type Annotations?**

Type annotations are used to **explicitly tell TypeScript the type of a variable, function parameter, return type, or object.**

```ts
let age: number = 30;
function add(n1: number, n2: number): number {
  return n1 + n2;
}
```

> Think of them as **labels** that help TypeScript understand your code better.

---

### 💡 Why Use Type Annotations?

1. ✅ **Avoid bugs:** Catch errors before running your code.
    
2. ✅ **Better code hints:** Your IDE gives smarter autocompletion and warnings.
    
3. ✅ **Readable code:** Other developers understand your intentions more easily.
    

---

### ❓ Are Type Annotations Mandatory?

- **No**, they’re not always required.
    
- TypeScript has a feature called **type inference**, which means it can often figure out the type for you.
    

```ts
let name = "Ayman"; // inferred as string
```

But if you want to be clear or avoid mistakes, **add annotations** yourself.

---

### ⚠️ What Happens If You Don’t Use Them?

Without type annotations:

- TypeScript might **infer `any`** for your variables, allowing **any value**, which removes type safety.
    
- You may accidentally **combine wrong types** (e.g., number + string) without errors.
    

---

### 🧪 Example Breakdown from Your Code:

#### ✅ With Type Annotations

```ts
let theAge: number = 40;         // age must be a number
let hire: boolean = true;       // must be true/false
let all: any = "Elzero";        // can be anything
```

#### 🧠 Function with Type Annotations

```ts
function add(n1: number, n2: number) {
  return n1 + n2;
}
console.log(add(10, 20));       // ✅ 30
```

#### ❌ Without Type Annotations (Dynamic)

```ts
function add(n1, n2) {
  return n1 + n2;
}
console.log(add(10, "20"));     // ❗ "1020" (string)
```

> 🧠 This happens because JavaScript treats `10 + "20"` as string concatenation. TypeScript didn’t warn you because no types were specified.

---
### 🧪 Mixed Data Type

In TypeScript, you can create a **union type**, which allows a variable to hold **multiple types**. The syntax for this is `(type1 | type2)`, meaning the variable can hold either `type1` or `type2`.

#### **Example:** Variable Declaration

```ts
let value: number | string;

value = 100;         // valid, it's a number
value = "Hello";     // valid, it's a string

```


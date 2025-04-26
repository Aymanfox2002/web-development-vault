
## 🧠 The Code:

```ts
let article: [number, string, boolean] = [11, "Title One", true];

// ❌ Assignment
article = [12, "Title Two", false, 23]; // Error

// ✅ Mutation
article.push(100); // No Error
```

---

## 🔍 Why is the assignment ❌ _not allowed_?

This is because:

- `article` is defined as a **tuple** with exactly:
    
    ```ts
    [number, string, boolean] // Length = 3
    ```
    
- Trying to assign **4 elements** like:
    
    ```ts
    [number, string, boolean, number] // Length = 4
    ```
    
    doesn't match the original type. TypeScript throws an error because you're **replacing the whole tuple with a different structure**.
    

---

## 🔓 Why is `.push(100)` ✅ _allowed_?

- Tuples are based on **arrays**.
    
- And arrays in JavaScript are **mutable** — they allow `.push()`, `.pop()`, etc.
    
- TypeScript’s default behavior **doesn’t restrict** those methods, even for tuples.
    
- So `.push(100)` succeeds — but the added value is **not type-safe**.
    

> TypeScript won’t stop you unless you use `readonly` or `as const`.

---

## 🧪 TL;DR

|Operation|Type Checked Strictly?|Behavior in TS|
|---|---|---|
|Assignment|✅ Yes (based on tuple length and types)|❌ Error if length/type mismatch|
|`.push()` / Mutation|❌ No (not strictly checked)|✅ Allowed, but unsafe|

---

### ✅ How to make `.push()` throw error?

```ts
let article: readonly [number, string, boolean] = [11, "Title One", true];
article.push(100); // ❌ Error now
```

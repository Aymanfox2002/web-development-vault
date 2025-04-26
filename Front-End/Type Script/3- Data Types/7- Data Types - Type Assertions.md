### 📌 What Are Type Assertions?

Type Assertions in TypeScript are a way to **tell the compiler** the exact type of a value — even when the compiler **isn’t sure**.

> Think of it like a way to say:  
> “Hey TypeScript, I know better than you what type this value actually is!”

---

### 🔎 Why Use Type Assertions?

- The **TypeScript compiler** doesn't always know the exact type (especially with DOM elements or `any` values).
    
- You may want to **override the inferred type** to access specific properties or methods.
    

---

### ✳️ Syntax

There are **two ways** to use type assertions:

```ts
let value = <Type>someValue;
```

OR

```ts
let value = someValue as Type;
```

> ✅ Both are equivalent.  
> ⛔ Use `as` syntax in `.tsx` (React) files, because `<Type>` is reserved for JSX.

---

### 📘 Example 1: Asserting a DOM Element

```ts
// Without assertion, TypeScript thinks `myImg` is just HTMLElement | null
let myImg = <HTMLImageElement>document.getElementById("my-img");

console.log(myImg.src); // We can now access `.src` property!
```

- The compiler **normally wouldn’t allow `.src`** because it doesn't know if `myImg` is actually an `HTMLImageElement`.
    
- Type Assertion tells TypeScript:
    
    > “Trust me — this is an HTMLImageElement.”
    

---

### 📘 Example 2: Asserting from `any`

```ts
let data: any = 1000;
console.log((data as string).repeat(3));
```

- We declared `data` as `any`, but then told TypeScript:

> “Pretend `data` is a string, so I can use `.repeat()`.”


> [!warning] Note
>  TypeScript will **not validate** if `data` really is a string.  
> If it's not, it will fail **at runtime**.

---

### ⚠️ Important Notes

- **Type Assertions do NOT change the runtime type** — they’re only used by TypeScript at **compile-time**.
    
- It’s your responsibility to **ensure that the assertion is correct**.
    
- Wrong assertions can cause **runtime errors**.
    

---

### ✅ When to Use

- Working with DOM elements
    
- Working with 3rd-party libraries that return `any`
    
- Parsing JSON where you know the structure
    
- When you have better knowledge of the type than TypeScript
---

### **:LiChevronsRight: [[8- Data Types - Union And Intersection Types|Next lesson]]** 
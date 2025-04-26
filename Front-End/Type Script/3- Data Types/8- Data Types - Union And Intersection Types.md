
### 🔹 Union Types (`|`)

- Union types allow a variable to **hold multiple possible types**.
    
- Think of it like "**either this or that**".
    

```ts
let all: number | string = 100;
all = "Hello"; // ✅ Also valid
```

💡 This is useful when a variable or parameter can accept more than one type.

---

### 🔸 Intersection Types (`&`)

- Intersection types are used to **combine multiple types into one**.
    
- Think of it like "**this and that**".
    
- The resulting type must satisfy **all combined types**.
    

---

### 🧪 Code Explanation

```ts
type A = {
  one: string,
  two: number,
  three: boolean
}

type C = {
  five: boolean
}

type mix = A & C; // Intersection of A and C
```

Now the `mix` type has **all** properties from both `A` and `C`:

```ts
{
  one: string,
  two: number,
  three: boolean,
  five: boolean
}
```

### ✅ Example Usage

```ts
function getActions(btns: mix) {
  console.log(`Hello ${btns.one}`);
  console.log(`Hello ${btns.two}`);
  console.log(`Hello ${btns.three}`);
  console.log(`Hello ${btns.five}`);
}
```

> When calling `getActions(...)`, the object **must include all 4 properties** from both `A` and `C`.

```ts
getActions({ one: "String", two: 100, three: true, five: true }); // ✅
```

---

### **:LiChevronsRight: [[9- Data Types - Type Annotations With Object|Next lesson]]** 
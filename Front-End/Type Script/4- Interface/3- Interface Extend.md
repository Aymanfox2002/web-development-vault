### ✅ Definition

In TypeScript, the `extends` keyword allows **one interface to inherit** properties from **another interface**.  
This means you can **reuse code**, keep it **organized**, and **build complex structures** from smaller ones.

---

## 🧩 1. Simple Example – Extend One Interface

```ts
interface Person {
  name: string;
  age: number;
}

interface Employee extends Person {
  jobTitle: string;
}

const emp: Employee = {
  name: "Sara",
  age: 28,
  jobTitle: "Frontend Developer"
};
```

### 🔍 Explanation:

- `Employee` gets all properties from `Person` (`name`, `age`)
    
- We add a new property `jobTitle` in `Employee`


---

## 🧩 2. Simple Example – Extend Two Interfaces

```ts
interface Person {
  name: string;
  age: number;
}

interface Location {
  city: string;
}

interface Employee extends Person, Location {
  jobTitle: string;
}

const emp: Employee = {
  name: "John",
  age: 35,
  city: "Cairo",
  jobTitle: "Backend Developer"
};
```

### 🔍 Explanation:

- `Employee` now has:
    
    - `name` and `age` from `Person`
        
    - `city` from `Location`
        
    - `jobTitle` added directly
        

---

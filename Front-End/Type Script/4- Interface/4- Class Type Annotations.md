### ✅ What Are Class Type Annotations?

In TypeScript, **class type annotations** help you **explicitly define** the data types of:

- Class properties (like variables inside the class)
    
- Method parameters
    
- Return values of methods
    

This improves:

- **Code clarity**
    
- **Developer understanding**
    
- **Compile-time error checking**
    

---

### 🔧 Example Breakdown

```ts
class User {
  u: string;
  s: number;
  msg: () => string;

  constructor(username: string, salary: number) {
    this.u = username;
    this.s = salary;
    this.msg = function () {
      return `Hello ${this.u} Your Salary Is ${this.s}`;
    }
  }

  sayMsg() {
    return `Hello ${this.u} Your Salary Is ${this.s}`;
  }
}
```

### 🧩 What’s Happening Here?

|Code Line|Explanation|
|---|---|
|`u: string;`|Property `u` must hold a string (username)|
|`s: number;`|Property `s` must hold a number (salary)|
|`msg: () => string;`|Property `msg` is a function that returns a string|
|`constructor(username: string, salary: number)`|Enforces types for incoming parameters|
|`sayMsg()`|A method that returns a string (no need to annotate unless you want to be explicit)|

---

### 💡 Usage

```ts
let userOne = new User("Elzero", 6000);

console.log(userOne.u);         // "Elzero"
console.log(userOne.s);         // 6000
console.log(userOne.msg());     // "Hello Elzero Your Salary Is 6000"
console.log(userOne.sayMsg());  // "Hello Elzero Your Salary Is 6000"
```

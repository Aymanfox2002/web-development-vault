### 🟩 What is Type Annotation for Objects?

Type annotations let you **explicitly define the structure** of an object in TypeScript, specifying:

- **Property names**
    
- **Property types**
    
- Whether a property is **optional** or **read-only**


This helps:

- Avoid mistakes
    
- Make your code **predictable and safer**
    
- Improve code auto-completion and documentation


---

### 🧱 Basic Syntax

```ts
let obj: {
  name: string;
  age: number;
  isActive?: boolean; // optional
  readonly id: number; // cannot be changed
} = {
  name: "Ayman",
  age: 25,
  id: 101
};
```

---

## 🧪 Your Code Explained

```ts
let myObject: {
  readonly username: string,
  id: number,
  hire?: boolean,
  skills: {
    one: string,
    two: string
  }
} = {
  username: "Elzero",
  id: 100,
  hire: true,
  skills: {
    one: "HTML",
    two: "CSS"
  }
};
```

### ✅ Key Points:

|Property|Type|Description|
|---|---|---|
|`username`|`string`|`readonly`: cannot be changed after initialization|
|`id`|`number`|mutable, can be updated|
|`hire?`|`boolean`|optional, may or may not be present|
|`skills`|object|nested object with `one` and `two` as strings|

---

### 🔒 Readonly

```ts
// myObject.username = "Osama"; ❌ Error: Cannot assign to 'username' because it is a read-only property
```

---

### 🔄 Updating Other Values

```ts
myObject.id = 101;      // ✅ Allowed
myObject.hire = false;  // ✅ Optional, now explicitly set
```

---

### 🖨️ Output

```ts
console.log(myObject.username); // Elzero
console.log(myObject.id);       // 101
console.log(myObject.hire);     // false
console.log(myObject.skills.one); // HTML
```

---

### **:LiChevronsRight: [[1- Interface Declaration|Next lesson]]** 

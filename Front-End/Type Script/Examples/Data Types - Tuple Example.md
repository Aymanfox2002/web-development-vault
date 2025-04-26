### ✅ Goal:

We want a function that gives us:

- A user's **name** (string)
    
- A user's **age** (number)


Instead of returning just one value, we return **both in a tuple**.

---

### 🧱 Step-by-Step

#### 1. Define the function:

```ts
function getUserInfo(): [string, number] {
  return ["Ayman", 25];
}
```

**Explanation:**

- `(): [string, number]` → The function will return a tuple.
    
- Inside the tuple:
    
    - First value is a `string` (the name)
        
    - Second value is a `number` (the age)
        

---

#### 2. Call the function:

```ts
const result = getUserInfo(); // ["Ayman", 25]
```

Now `result` is a tuple:

```ts
// result: [string, number]
```

---

#### 3. Use **destructuring** to extract values:

```ts
const [name, age] = getUserInfo();

console.log(name); // "Ayman"
console.log(age);  // 25
```

This is a **clean way** to pull values from a tuple into variables.

---

### 🔁 Without Tuple:

If you returned an object instead:

```ts
function getUserInfoObj() {
  return { name: "Ayman", age: 25 };
}
```

You'd write:

```ts
const { name, age } = getUserInfoObj();
```

But using a **tuple** is **shorter and more strict** — good when the positions are always the same and meaningful.

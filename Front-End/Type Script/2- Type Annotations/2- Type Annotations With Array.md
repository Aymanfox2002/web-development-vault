
### ✅ Syntax Options

```ts
let names: string[] = ["Ali", "Sara", "Nora"];
let numbers: number[] = [1, 2, 3];
let flags: boolean[] = [true, false];

let mixed: (number | string)[] = [1, "two", 3];
```

### 🧠 Explanation

- `string[]` → Array of strings only
    
- `number[]` → Array of numbers only
    
- `(number | string)[]` → Array with numbers **or** strings
    
- `any[]` → Array with any type (not recommended)
    

---

### ❌ Wrong Usage Example

```ts
let names: string[] = ["Ali", 2]; // ❌ Error: number is not assignable to string
```

---

### 🛠 Use Case in Functions

```ts
function logNames(arr: string[]) {
  arr.forEach(name => console.log(name));
}

logNames(["Ayman", "Laila", "Omar"]);
```

---

## 📘 Multi-Dimensional Arrays

---

### 🔹 1. **Two-Dimensional Arrays (2D Arrays)**

#### ➤ Pattern: `number[][]` or `Array<number[]>`

- Each element is an array of numbers.
    

```ts
let matrix: number[][] = [
  [1, 2],
  [3, 4],
  [5, 6]
];
```



---

### 🔹 2. **Three-Dimensional Arrays (3D Arrays)**

#### ➤ Pattern: `number[][][]`

- Each element is an array of 2D arrays.
    

```ts
let cube: number[][][] = [
  [ [1, 2], [3, 4] ],
  [ [5, 6], [7, 8] ]
];
```



---

### 🔹 3. **Mixed-Type Arrays Inside 2D Array**

#### ➤ Pattern: `(number | string)[][]`

- Each row can have strings or numbers.
    

```ts
let mixed: (number | string)[][] = [
  [1, "A"],
  [2, "B"]
];
```


---

### 🔹 4. **Array with Nested Arrays and Other Types**

#### ➤ Pattern: `(number | string[] | boolean)[]`

- An array that includes nested arrays and other types.
    

```ts
let complex: (number | string[] | boolean)[] = [
  10,
  ["Hello", "World"],
  true,
  42
];
```



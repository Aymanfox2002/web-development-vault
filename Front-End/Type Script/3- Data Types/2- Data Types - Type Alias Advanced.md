 
### 🔷 What is a Type Alias?

A **Type Alias** lets you define a custom name for a type structure, especially useful for objects, functions, arrays, etc.

---
### 🧪 Basic Example

```ts
type Buttons = {
  up: string,
  right: string,
  down: string,
  left: string
};

function getActions(btns: Buttons) {
  console.log(`Action For Button Up Is ${btns.up}`);
  console.log(`Action For Button Right Is ${btns.right}`);
  console.log(`Action For Button Down Is ${btns.down}`);
  console.log(`Action For Button Left Is ${btns.left}`);
}

getActions({
  up: "Jump",
  right: "Go Right",
  down: "Go Down",
  left: "Go Left"
});
```

#### Explanation What is [[Type Alias Advanced Example | happen]]❓:

---

## 💡 Extra Info: Extending a Type (Using `&`)

If you want to **add more properties** to an existing type, use the **intersection (`&`)** operator.

### 🧩 Example:

```ts
type Last = Buttons & {
  x: boolean;
};
```

Now, `Last` includes everything from `Buttons` **plus** the new `x: boolean` field.

#### 🔧 Updated Function:

```ts
function getActions(btns: Last) {
  console.log(`Action For Button Up Is ${btns.up}`);
  console.log(`Action For Button Right Is ${btns.right}`);
  console.log(`Action For Button Down Is ${btns.down}`);
  console.log(`Action For Button Left Is ${btns.left}`);
  console.log(`Extra Button X is Active? ${btns.x}`);
}

getActions({
  up: "Jump",
  right: "Go Right",
  down: "Go Down",
  left: "Go Left",
  x: true
});
```

---
### **:LiChevronsRight: [[3- Data Types - Literal Types|Next lesson]]** 
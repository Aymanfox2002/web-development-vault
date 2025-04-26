## ✅ The Confusion in [[2- Data Types - Type Alias Advanced#🧪 Basic Example|this example]]

Maybe you said :

> `btns` is a parameter and should be followed by `:` and a **type**...  
> But what's happening here looks like we're writing more **parameters** instead of a **type**.

Here’s what’s really going on:

```ts
function getActions(btns: {
  up: string,
  right: string,
  down: string,
  left: string,
  x: boolean
}) {
  console.log(btns.up);
}
```

---

## 💡 The Truth

### This part:

```ts
btns: {
  up: string,
  right: string,
  down: string,
  left: string,
  x: boolean
}
```

Is actually saying:

> "The parameter `btns` must be an **object** that has exactly those properties."

So yes — it **looks like we're defining parameters again**, but we're not.

We're defining a **type shape** for the single parameter `btns`.

---

## 🧠 Think of it like this:

It's the same as doing:

```ts
type Last = {
  up: string,
  right: string,
  down: string,
  left: string,
  x: boolean
};

function getActions(btns: Last) {
  // ...
}
```

But instead of using the `Last` type alias, we're **writing the object type directly** inline.

---

### ✅ Summary Table

|Code|Meaning|
|---|---|
|`btns`|Parameter name|
|`:`|Assigning a type to `btns`|
|`{ up: string, ... }`|The **type** of the `btns` object|

---

### Would an analogy help?

It’s like filling out a form:

- `btns` is the box on the form.
    
- The shape (`{ up: string, ... }`) is what’s allowed to go into the box.
    
- We're not writing parameters again — we're describing what the box must contain.




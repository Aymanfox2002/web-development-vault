
## 🟦 1. What is an Enum?

**Enum (short for Enumeration)** is a special data type that lets you define a set of **named constants**.

### ✅ Why Use It?

- ![[Handshake.png|34x34]]Groups related values together.
    
- ![[Comet.png|36x36]]Makes code easier to read and maintain.
    
- ![[Milky Way.png|31x31]]Replaces "magic numbers" or hardcoded strings.



---

## 🟦 2. Basic Numeric Enum (Default)

By default, **enum values are numeric**, starting from `0`.

```ts
enum Direction {
  Up,     // 0
  Down,   // 1
  Left,   // 2
  Right   // 3
}

console.log(Direction.Up);    // 0
console.log(Direction.Right); // 3
```

---

## 🟦 3. String-Based Enum

You can assign **string values** to enum members manually.

```ts
enum Size {
  Small = "S",
  Medium = "M",
  Large = "L"
}

console.log(Size.Small);  // "S"
```

---

## 🟦 4. Heterogeneous Enum

You can **mix strings and numbers** in the same enum, but it’s **not recommended** unless necessary.

```ts
enum Mixed {
  No = 0,
  Yes = "YES"
}
```

---

## 🟦 5. Enum Referencing Itself

An enum can refer to its own members.

```ts
enum Repeat {
  Once = 1,
  Twice = Once * 2
}

console.log(Repeat.Twice); // 2
```


> [!warning]
> you can't refer any value to value positioned after it, like:
> 
> ```ts
> enum Repeat {
>   Once = Twice - 1,
>   Twice =  2
> }
> ```
> 

---

## 🟦 6. Enum Referencing Another Enum

You can build one enum using values from another.

```ts
enum Base {
  One = 1,
  Two = 2
}

enum Extended {
  Three = Base.Two + 1
}

console.log(Extended.Three); // 3
```

---

## 🟦 7. Enum with Calculations

You can perform **math operations** inside enums.

```ts
enum MathEnum {
  A = 10,
  B = A * 2
}

console.log(MathEnum.B); // 20
```

---

## 🟦 8. Enum with Functions (Computed Values)

Enums can call functions for computed values — but only in some cases (usually at declaration time).

```ts
function getCode() {
  return 100;
}

enum Result {
  Code = getCode()
}

console.log(Result.Code); // 100
```

---

### **:LiChevronsRight: [[7- Data Types - Type Assertions|Next lesson]]** 
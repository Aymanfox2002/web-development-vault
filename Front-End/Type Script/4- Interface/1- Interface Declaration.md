> [!info] What is it?
> **The Interface** looks like [[9- Data Types - Type Annotations With Object|types]] with, it's describes the shape of an object.

---
## 🔶 Syntax

We set structure of object's shape in [[9- Data Types - Type Annotations With Object|last lesson]] like this way:
```ts
let obj: {
  name: string;
  age: number;
  isActive?: boolean; 
  readonly id: number; 
} = {
  name: "Ayman",
  age: 25,
  id: 101
};
```

with Interface we can do it like that:

```ts
interface User {
  name: string;
  age: number;
}

let obj: User = {
  name: "Ayman",
  age: 25,
};
```

---
## 🔶 Use With Function

```ts
interface User {
  name: string;
  age: number;
  isActive?: boolean;
  readonly id: number;
}

let obj: User = {
  name: "Ayman",
  age: 25,
  id: 101,
};
		
function getData(data: User){
  console.log(`${data.name} - ${data.age} - ${data.id}`)
}
```

### Another Example "important ❗"

```ts
interface User {
 id: number,
 username: string,
 country: string,
 sayHello(): string,
 sayWelcome: () => string,
 getDouble(num: number): number;
}

let user: User = {
  id: 231,
 username: "Ayman",
 country: "Sudan",
 sayHello() {
  return `Hello ${this.username}`
 },

 sayWelcome: () => { //❗note: put ':' after function's name
  return `Welcome ${user.username}` //❌ ${this.username}
 },

 getDouble(n) {
  return n * 2
 }
};
```

---
### **:LiChevronsRight: [[2- Interface ReOpen|Next lesson]]** 
> [!info] What is it?
> Interface Reopen it's simple idea which let you to use same Interface more than one time.

---
## **🔶 Example**

```ts
//Homepage
interface Setting {
  theme: boolean;
  font: string;
}

//Articles page

interface Setting {
  sidebar: boolean;
}

//Contact page
interface Setting {
  external: boolean;
}
  
//Usage
let userSetting: Setting = {
  theme: true,
  font: "Open Sans",
  sidebar: false,
  external: true,
};
```

---

### **:LiChevronsRight: [[3- Interface Extend|Next lesson]]** 

## ✅ `tsc --init`

This command creates a **TypeScript configuration file** named `tsconfig.json` in your project.

### 🧠 Why use it?

Instead of manually passing options to the compiler every time, `tsconfig.json` tells the TypeScript compiler:

- What files to include or exclude
    
- What ECMAScript version to compile to (like ES5 or ES6)
    
- Whether to allow JSX, strict mode, etc.
    


---

## ✅ `tsc -w`

This runs the **TypeScript compiler in watch mode**.

### 📌 What does it do?

```bash
tsc -w
```

It **watches your `.ts` files for changes**, and every time you save a file, it **automatically recompiles** it into JavaScript.

>Press `Ctrl + C`  to stop watch mode.
---

### 🧪 Example Workflow

You run:

```bash
tsc -w
```

Now every time you edit and save a TypeScript file in your project, the `.js` version updates automatically in the output folder (like `dist/`).

---

### 🛠️ Pro Tip:

If you organize your files like this:

```
/src/index.ts
/tsconfig.json
```

Make sure your `tsconfig.json` includes:

```json
{
  "compilerOptions": {
    "outDir": "./dist",
    "rootDir": "./src"
  },
  "include": ["src"]
}
```

Then TypeScript will compile everything in `/src` and output `.js` files to `/dist`.

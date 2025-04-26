
## 1. Function Type Annotations & `noImplicitAny`

```typescript
// With noImplicitAny enabled (recommended)
function showDetails(name: string, age: number, salary: number): string {
  // All parameters are explicitly typed
  // Return type is explicitly declared
  let test = 10; // Local variable
  if (showMsg) {
    return `Hello ${name}, Age Is ${age}, Salary Is ${salary}, Test Variable ${test}`;
  }
  return `No Data To Show`;
}
```

Key points:
- All parameters must have type annotations
- Return type should be explicitly declared
- Without these, TypeScript would error with `noImplicitAny`

## 2. `noImplicitReturns` Control Path Checking

```typescript
// This would cause an error with noImplicitReturns
function badExample(showMsg: boolean): string {
  if (showMsg) {
    return "Message shown";
  }
  // Error: Not all code paths return a value
}

// Correct version (like your example)
function showDetails(name: string, age: number, salary: number): string {
  let test = 10;
  if (showMsg) {
    return `Hello ${name}, Age Is ${age}, Salary Is ${salary}, Test Variable ${test}`;
  }
  return `No Data To Show`; // All paths covered
}
```

## 3. `noUnusedLocals` - Unused Variable Detection

```typescript
function exampleWithUnusedVars() {
  const usedVar = "I'm used";
  const unusedVar = "I'm not used"; // Error with noUnusedLocals
  
  console.log(usedVar);
}

// Your example is clean - 'test' is used in the return value
```

## 4. `noUnusedParameters` - Parameter Usage Enforcement

```typescript
// This would trigger an error
function withUnusedParam(name: string, unusedParam: number) {
  return `Hello ${name}`; // unusedParam not used
}

// Your example is correct - all parameters are used
function showDetails(name: string, age: number, salary: number): string {
  // All parameters are used in the return statement
  return showMsg 
    ? `Hello ${name}, Age Is ${age}, Salary Is ${salary}`
    : `No Data To Show`;
}
```

## Complete Example with All Checks

```typescript
let showMsg = true;

// Fully type-annotated function that passes all strict checks
function showDetails(
  name: string, 
  age: number, 
  salary: number
): string {
  // Using all parameters
  // Using all local variables
  const test = 10;
  
  // All code paths return
  if (showMsg) {
    return `Hello ${name}, Age Is ${age}, Salary Is ${salary}, Test Variable ${test}`;
  }
  return `No Data To Show`;
}

console.log(showDetails("Osama", 40, 5000));
```

## Key Benefits of These Checks

1. **Type Safety**: `noImplicitAny` ensures no untyped parameters
2. **Code Reliability**: `noImplicitReturns` prevents missing return cases
3. **Clean Code**: `noUnusedLocals` and `noUnusedParameters` eliminate dead code

To enable these in your `tsconfig.json`:
```json
{
  "compilerOptions": {
    "noImplicitAny": true,
    "noImplicitReturns": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true
  }
}
```

These strict checks help catch errors during development rather than at runtime, making your functions more reliable and maintainable.
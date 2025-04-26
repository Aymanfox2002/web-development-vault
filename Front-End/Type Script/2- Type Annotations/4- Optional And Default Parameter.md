
# Content:

1. [[#Understanding Optional Parameters]]
2. [[#Default Parameters]]
3. [[#Combining Optional and Default Parameters]]
4. [[#Type Safety Considerations]]
5. [[#Best Practices]]

---

## Understanding Optional Parameters

In TypeScript, you can make function parameters optional using the `?` operator. This is different from JavaScript where all parameters are inherently optional.

```typescript
// Optional parameters with '?'
function showData(name?: string, age?: number, country?: string) {
  return `${name} - ${age} - ${country}`;
}

// All these calls are valid
console.log(showData("Osama", 40, "Egypt"));  // "Osama - 40 - Egypt"
console.log(showData("Osama", 40));           // "Osama - 40 - undefined"
console.log(showData("Osama"));               // "Osama - undefined - undefined"
console.log(showData());                      // "undefined - undefined - undefined"
```

Key points about optional parameters:
1. Marked with `?` after the parameter name
2. Their type automatically includes `undefined`

> [!warning]
>  Must come after required parameters

## Default Parameters

TypeScript also supports default parameter values, which work similarly to JavaScript but with type safety:

```typescript
// Default parameters
function registerUser(
  name: string, 
  age: number = 18,          // Default value
  country: string = "Egypt"   // Default value
) {
  return `${name} - ${age} - ${country}`;
}

console.log(registerUser("Osama", 40, "USA"));  // "Osama - 40 - USA"
console.log(registerUser("Osama", 40));         // "Osama - 40 - Egypt"
console.log(registerUser("Osama"));             // "Osama - 18 - Egypt"
```

Important notes about default parameters:
1. Provide a value directly in the parameter list
2. Don't need the `?` operator
3. Type is inferred from the default value if not specified
4. Like optional parameters, must come after required parameters

## Combining Optional and Default Parameters

```typescript
function createProfile(
  username: string,
  isVerified?: boolean,        // Optional parameter
  followers: number = 0       // Default parameter
) {
  return `${username} (${isVerified ? "✓" : "x"}) - ${followers} followers`;
}

console.log(createProfile("Osama", true, 1000));  // "Osama (✓) - 1000 followers"
console.log(createProfile("Osama", true));        // "Osama (✓) - 0 followers"
console.log(createProfile("Osama"));              // "Osama (x) - 0 followers"
```

## Type Safety Considerations

TypeScript helps prevent common mistakes with optional parameters:

```typescript
function calculatePrice(price: number, discount?: number) {
  // Error: Object is possibly 'undefined'
  // return price - discount;
  
  // Proper handling
  return discount ? price - discount : price;
}
```

## Best Practices

1. Put required parameters first, then optional/default parameters
2. Use default parameters instead of `undefined` checks when possible
3. Be explicit with types even when using default values
4. Document optional parameters with JSDoc comments

```typescript
/**
 * Creates a user profile string
 * @param username - Required username
 * @param isVerified - Optional verification status
 * @param followers - Defaults to 0 if not provided
 */
function createProfile(
  username: string,
  isVerified?: boolean,
  followers: number = 0
) {
  // ...
}
```

These features make your functions more flexible while maintaining TypeScript's type safety benefits.
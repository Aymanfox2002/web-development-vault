
Rest parameters allow a function to accept an indefinite number of arguments as an array. In TypeScript, we can also strongly type these parameters.
### Basic Syntax

```typescript
function sumAll(...numbers: number[]): number {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sumAll(1, 2, 3));       // 6
console.log(sumAll(5, 10, 15, 20)); // 50
```

Key characteristics:
- Prefix the parameter name with `...`
- Must be the last parameter in the list
- Collects all remaining arguments into an array

## Type Safety with Rest Parameters

TypeScript enforces type checking on rest parameters:

```typescript
// Only numbers allowed
function calculateAverage(...scores: number[]): number {
  const total = scores.reduce((sum, score) => sum + score, 0);
  return total / scores.length;
}

// calculateAverage(1, 2, "3"); // Error: Argument of type 'string' is not assignable
console.log(calculateAverage(90, 85, 95)); // 90
```

## Combining with Regular Parameters

Rest parameters can be combined with regular parameters:

```typescript
function buildSentence(subject: string, verb: string, ...objects: string[]): string {
  return `${subject} ${verb} ${objects.join(' ')}`;
}

console.log(buildSentence("I", "love", "TypeScript", "and", "JavaScript"));
// "I love TypeScript and JavaScript"
```


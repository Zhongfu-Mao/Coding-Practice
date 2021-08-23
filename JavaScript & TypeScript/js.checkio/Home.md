# Sum Numbers

## My Solution

```typescript
function sumNumbers(test: string): number {
  return test.split(" ").reduce((previous, current) => {
    const match = current.match(/^\d+$/);
    return previous + (match ? parseInt(match[0]) : 0);
  }, 0);
}
```

## Others' Solution

### map filter reduce

```typescript
function sumNumbers(test: string): number {
  return test
    .split(" ")
    .map((v) => Number(v))
    .filter((v) => v)
    .reduce((p, c) => p + c, 0);
}
```

# Three Words

## My Solution

```typescript

```


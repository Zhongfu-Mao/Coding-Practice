# Easy Unpack

## My Solution

```typescript
function easyUnpack(values: any[]): any[] {
    return [values[0], values[2], values[values.length-2]];
}
```

JavaScript不像Python有负数索引

# Number Length

## My Solution

```typescript
function numberLength(value: number): number {
    return value.toString().length;
}
```

## Others' Solutions

```typescript
var numberLength = v => String(v).length
var numberLength = v => (v+'').length
var numberLength = v => `${v}`.length
```

# End Zeros

## My Solution

```typescript
function endZeros(value: number): number {
    const array = Array.from(value.toString());
    let count = 0;

    for(let i=array.length - 1; i >= 0; i--) {
        if (array[i] === "0") {
            count++;
        } else {
            break;
        }
    }

    return count;
}
```

## Others' Solutions

### replace

```typescript
function endZeros(value: number): number {
    const s = String(value);
    return s.length - s.replace(/0*$/, '').length;
}
```

### match

```typescript
var endZeros=(v: number): number => (''+v).match(/0*$/)[0].length;
```

### div and recursion

```typescript
var endZeros=(value: number): number => value? (value%10)? 0 : 1 + endZeros( value/10 ) : 1
```

# Backward String

## My Solution

```typescript
function backwardString(value: string): string {
    return Array.from(value).reverse().join("");
}
```

## Others' Solutions

### spread

```typescript
var backwardString = (value: string): string =>[...value].reverse().join("");
```

### split reverse join

```typescript
function backwardString(value: string): string {
    return value.split('').reverse().join('');
}
```

# Remove All Before

## My Solution

```typescript
function removeAllBefore(values: number[], b: number): number[] {
    let start = values.includes(b) ? values.indexOf(b) : 0;
    return values.slice(start, values.length);
}
```

## Others' Solutions

### Math.max

```typescript
var removeAllBefore = (values: number[], b: number): number[] => values.slice(Math.max(0, values.indexOf(b)));
```

slice的end如果不指定就到最后

### slice

```typescript
function removeAllBefore(values: number[], b: number): number[] {
    return values.includes(b) ? values.slice(values.indexOf(b)) : values 
}
```

# Repalce First

## My Solution

```typescript
function replaceFirst(values: number[]): number[] {
    return values.length > 1 ? [...values.slice(1), values[0]] : values;
}
```

## Others' Solutions

### push shift

```typescript
function replaceFirst(values: number[]): number[] {
    if (values.length > 1) {
        values.push(values.shift());
    }
    return values;
}
```

### slice concat

```typescript
function replaceFirst(values: number[]): number[] {
    return values.length > 0 ? values.slice(1).concat(values[0]) : [];
}
```

### comma operator(很少见)

```typescript
function replaceFirst(v: number[]): number[] {
    return v.length && v.push(v.shift()), v;
}
```

> The comma operator (,) evaluates each of its operands (from left to right) and returns the value of the last operand

```typescript
if (values.length) {
    values.push(v.shift())
} 
return values;
```

# Max Digit

## My Solution

```typescript
function maxDigit(value: number): number {
    return `${value}`.split('').reduce((prev, cur) => Math.max(Number(prev), Number(cur)), 0);
}
```

## Others' Solutions

### max spread

```typescript
// @ts-ignore
function maxDigit(value) {
  return Math.max(...value.toString());
}
```

### sort pop

```typescript
function maxDigit(v: number): number {
    return +[...(v+'')].sort().pop()
}
```

### sort reverse

```typescript
function maxDigit(value: number): number {
    return Number([...String(value)].sort().reverse()[0]);
}
```

### max map

```typescript
function maxDigit(value: number): number {
    const digits = String(value).split('').map(Number);
    return Math.max(...digits);
}
```

# Split Pairs

## My Solution

```typescript
function splitPairs(text: string): string[] {
    // your code here
    switch (text.length) {
        case 0: return [];
        case 1: return [text + "_"];
        case 2: return [text];
        default: return [text.substr(0, 2), ...splitPairs(text.substr(2))]
    }
}
```

## Others' Solutions

# Beginning Zeros

## My Solution

```typescript
function beginningZeros(text: string): number {
    // @ts-ignore
    return (/^0+/).test(text) ? text.match(/^0+/)[0].length : 0;
}
```

## Others' Solutions

### match

```typescript
var beginningZeros = text => text.match(/^0*/)[0].length;
```



# Nearest Value

## My Solution

```typescript
function nearestValue(values: number[], search: number): number {
    const sortedValues = values.sort((a, b) => a - b);
    const absValues = sortedValues.map((value) => Math.abs(value-search));
    const index = absValues.indexOf(Math.min(...absValues));

    return sortedValues[index];
}
```

## Others' Solutions

# Between Markers

## My Solution

```typescript
function betweenMarkers(line: string, left: string, right: string): string {
    const start = line.indexOf(left);
    const end = line.indexOf(right);
    return line.substring(start+1, end);
}
```

## Others' Solutions

# Correct Sentence

## My Solution

```typescript
function correctSentence(text: string): string {
    return text[0].toUpperCase() + text.substring(1) + (text.endsWith(".") ? "" : ".");
}
```

## Others' Solutions

# IS Even

## My Solution

```typescript
function isEven(num: number): boolean {
    return !!!(num % 2);
}
```

## Others' Solutions

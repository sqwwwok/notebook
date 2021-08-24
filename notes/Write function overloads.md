[ts docs](https://www.typescriptlang.org/docs/handbook/2/functions.html#function-overloads)

### Implementation signature make no sense
```ts
// overload signatures
function makeDate(timestamp: number): Date;
function makeDate(m: number, d: number, y: number): Date;

// implement signature
function makeDate(mOrTimestamp: number, d?: number, y?: number): Date {
  if (d !== undefined && y !== undefined) {
    return new Date(y, mOrTimestamp, d);
  } else {
    return new Date(mOrTimestamp);
  }
}


const d1 = makeDate(12345678);
const d2 = makeDate(5, 5, 5);

// implementation signature make no sense because of overload 
const d3 = makeDate(1, 3);
```

### Use union type instead of overload
```ts
function len(s: string): number;
function len(arr: any[]): number;
function len(x: any) {
  return x.length;
}
len(""); // OK
len([0]); // OK

// TypeScript can only resolve a function call to a single overload
len(Math.random() > 0.5 ? "hello" : [0]);

// Always prefer parameters with union types instead of overloads when possible
function len(x: any[] | string) {
  return x.length;
}
```
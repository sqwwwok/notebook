[Reference](https://www.typescriptlang.org/docs/handbook/2/functions.html#call-signatures)


```ts
type DescribableFunction = {
    description: string;
    // Construct signature
    new (s: string): SomeObject;
    // Call signature
    (someArg: number): boolean;
}

// implement a function like Date, Object, etc.

interface MyClass {
  val: number;
}

interface MyClassConstructor {
  new(val: number): MyClass;  // newable
  (val: string): string; // callable
}

const MyClass: MyClassConstructor = function(this: MyClass | void, val: number|string) {
  if (!(this instanceof MyClass)) {
    if(typeof(val)==='string') return val;
  } else {
    if(typeof(val)==='number') this!.val = val;
  }
} as MyClassConstructor;

const a = MyClass('fsd')

const b = new MyClass(12)

console.log(a, b)

```

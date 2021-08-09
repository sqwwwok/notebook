[Reference](https://www.typescriptlang.org/docs/handbook/2/functions.html#call-signatures)

```ts
type DescribableFunction = {
    description: string;
    (someArg: number): boolean;
}

const foo :DescribableFunction = (a) => {
    return a===6
}

foo.description = 'foo'


function doSomething(fn: DescribableFunction) {
    console.log(fn.description + " returned " + fn(6));
}

doSomething(foo)
```

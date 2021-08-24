[ts handbook](https://www.typescriptlang.org/docs/handbook/2/functions.html#optional-parameters-in-callbacks)

### no error hint

```ts
function myForEach(arr: any[], callback: (arg: any, index?: number) => void) {
  for (let i = 0; i < arr.length; i++) {
    // I don't feel like providing the index today
    callback(arr[i]);
  }
}

// 
myForEach([1, 2, 3], (a, i) => {
  console.log(i.toFixed());
});

```
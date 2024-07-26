# TypeScript Tutorial
[W3 Schools](https://www.w3schools.com/typescript/typescript_aliases_and_interfaces.php)



## TypeScript Union Types


### Number :
```
// the `: number` here specifies that this function returns a number
function getTime(): number {
  return new Date().getTime();
}
```

### Void :
```
function printHello(): void {
  console.log('Hello!');
}
```

### Parameters :
```
function multiply(a: number, b: number) {
  return a * b;
}
```

### Optional Parameters :
```
// the `?` operator here marks parameter `c` as optional
function add(a: number, b: number, c?: number) {
  return a + b + (c || 0);
}
```

### Default Parameters :
```
function pow(value: number, exponent: number = 10) {
  return value ** exponent;
}
```

### Named Parameters :
```
function divide({ a, b }: { a: number, b: number }) {
  return a / b;
}
```

### Rest Parameters
```
function add(a: number, b: number, ...rest: number[]) {
  return a + b + rest.reduce((p, c) => p + c, 0);
}
```

### Type Alias
```
type Negate = (value: number) => number;

// in this function, the parameter `value` automatically gets assigned the type `number` from the type `Negate`
const negateFunction: Negate = (value) => value * -1;
```
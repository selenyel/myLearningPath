# TypeScript Tutorial
[W3 Schools](https://www.w3schools.com/typescript/typescript_aliases_and_interfaces.php)



## TypeScript Classes

```
class Person {
  public constructor(private name: string) {
    this.name = name;
  }

  public getName(): string {
    return this.name;
  }
}

const person = new Person("Jane");
console.log(person.getName());

```

### Readonly

- ###### Cannot assign to 'name' because it is a read-only property.
```
class Person {
  private readonly name: string;

  public constructor(name: string) {
    // name cannot be changed after this initial definition, which has to be either at it's declaration or in the constructor.
    this.name = name;
  }

  public getName(): string {
    return this.name;
  }
  public setName(a) {
    this.name = a;
  }
}
      
const person = new Person("Jane");

console.log(person.getName());
```

### Inheritance: Implementation

```
interface Shape {
  getArea: () => number;
}

class Rectangle implements Shape,Color {
  public constructor(protected readonly width: number, protected readonly height: number) {}

  public getArea(): number {
    return this.width * this.height;
  }
}
```

### Inheritance: Extends
- ###### A class can only extends one other class.

```
interface Shape {
  getArea: () => number;
}

class Rectangle implements Shape {
  public constructor(protected readonly width: number, protected readonly height: number) {}

  public getArea(): number {
    return this.width * this.height;
  }
}

class Square extends Rectangle {
  public constructor(width: number) {
    super(width, width);
  }

  // getArea gets inherited from Rectangle
}
```

### Inheritance: Override
- ###### Newer versions of TypeScript allow explicitly marking this with the override keyword.

```
interface Shape {
  getArea: () => number;
}

class Rectangle implements Shape {
  // using protected for these members allows access from classes that extend from this class, such as Square
  public constructor(protected readonly width: number, protected readonly height: number) {}

  public getArea(): number {
    return this.width * this.height;
  }

  public toString(): string {
    return `Rectangle[width=${this.width}, height=${this.height}]`;
  }
}

class Square extends Rectangle {
  public constructor(width: number) {
    super(width, width);
  }

  // this toString replaces the toString from Rectangle
  public override toString(): string {
    return `Square[width=${this.width}]`;
  }
}
```

### Abstract Classes
- ###### A base class for other classes without having to implement all the members.

```
abstract class Polygon {
  public abstract getArea(): number;

  public toString(): string {
    return `Polygon[area=${this.getArea()}]`;
  }
}

class Rectangle extends Polygon {
  public constructor(protected readonly width: number, protected readonly height: number) {
    super();
  }

  public getArea(): number {
    return this.width * this.height;
  }
}
```

# TypeScript Tutorial
[W3 Schools](https://www.w3schools.com/typescript/typescript_aliases_and_interfaces.php)



## TypeScript Type Aliases and Interfaces

Type :

```
type CarYear = number;
type CarType = string;
type CarIcon = symbol;

type Car = {
    year: CarYear,
    type: CarType,
    model: CarModel
};

const carYear : CarYear = 2001;
const carType : CarType = "Toyota";
const carIcon : CarIcon = Symbol("Corolla");

```

Interface :

```
interface IRectangle {
    height: number,
    width: number
}

const rectangle : IRectangle = {
    height: 20,
    width:10
}

interface IColoredRectangle extends IRectangle {
    color : string
}

const ColoredRectangle : IColoredRectangle = { height:20,width:20,color:'#aba' }
```



# Typescript Type Narrowing

In TypeScript, "narrowing" refers to the process of refining the type of a variable to a more specific type than
its current type. This is typically done using control flow constructs 
like `if`, `switch`, or `try/catch` statements, and `type guards`. <br/>
Here are some common ways to narrow types in TypeScript: <br/>

**Type Guards**
> TypeScript's type guards are expressions that perform runtime checks which guarantee the type in a specific scope.

`typeof` Type Guard
You can use the typeof operator to narrow down primitive types like string, number, boolean, symbol, bigint, undefined, or object.

```javascript
function printId(id: number | string) {
  if (typeof id === "string") {
    console.log(`ID in string format: ${id.toUpperCase()}`);
  } else {
    console.log(`ID in number format: ${id.toFixed()}`);
  }
}
```
`instanceof` **Type Guard**
> The instanceof operator is used to narrow down types based on constructor functions.
```javascript
class Cat {
  meow() { console.log("Meow"); }
}

class Dog {
  bark() { console.log("Woof"); }
}

function speak(animal: Cat | Dog) {
  if (animal instanceof Cat) {
    animal.meow();
  } else {
    animal.bark();
  }
}
```
**Control Flow Analysis**
> TypeScript uses control flow analysis to narrow types based on the code flow.
```javascript
function example(x: string | number | boolean) {
  if (typeof x === "string") {
    // x is of type string
    console.log(x.toUpperCase());
  } else if (typeof x === "number") {
    // x is of type number
    console.log(x.toFixed());
  } else {
    // x is of type boolean
    console.log(x ? "true" : "false");
  }
}
```
By using these techniques, you can help TypeScript understand the more specific type of a variable at any point
in your code, which improves type safety and reduces potential runtime errors.


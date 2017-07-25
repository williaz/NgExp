 [Handbook](https://www.typescriptlang.org/docs/handbook/basic-types.html)
 - In TypeScript, two types are compatible if their internal structure is compatible. 
 This allows us to implement an interface just by having the shape the interface requires, without an explicit implements clause.
### Basic Type
- : boolean, : number, 
- : string ; template strings: surrounded by the backtick/backquote (`) character, and embedded expressions are of the form ${ expr }.
- : number[]; : Array<number>
- Tuple types allow you to express an array where the type of a fixed number of elements is known, but need not be the same. 
  - When accessing an element outside the set of known indices, a union type is used instead
```js
// Declare a tuple type
let x: [string, number];
// Initialize it
x = ["hello", 10]; // OK
// Initialize it incorrectly
x = [10, "hello"]; // Error
```
- enum
```js
enum Color {Red = 1, Green, Blue}
let colorName: string = Color[2];
```
- : any ; : Object (variables of type Object only allow you to assign any value to them - you can’t call arbitrary methods on them, even ones that actually exist)
- : void = undefined/null; : undefined; : null
  - By default null and undefined are subtypes of all other types. 
- union type
- : never 
  - The never type is a subtype of, and assignable to, every type; 
  - however, no type is a subtype of, or assignable to, never (except never itself). Even any isn’t assignable to never.
- Type assertion
  - <string>
  - as string: JSX only work with it


 

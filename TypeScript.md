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

### Variable Declarations
- var declarations are accessible anywhere within their containing function, module, namespace, or global scope, regardless of the containing block. 
```js
//the inner for-loop will accidentally overwrite the variable i because i refers to the same function-scoped variable
for (var i = 0; i < matrix.length; i++) {
        var currentRow = matrix[i];
        for (var i = 0; i < currentRow.length; i++) {
            sum += currentRow[i];
        }
    }
```
- IIFE: creating a new variable environment for our captured variables.
- let: exical-scoping/ block-scoping:
  - block-scoped variables are not visible outside of their nearest containing block or for-loop
  - can’t be read or written to before they’re actually declared.
- The act of introducing a new name in a more nested scope is called shadowing
- const: no re-assign
  - the internal state of a const variable is still modifiable.
- Array destructuring
  - assignment
  - swap variables
  - create a variable for the remaining items in a list using the syntax ...(...rest), or just ignore trailing elements
- Object destructuring
  - surround with parentheses


  











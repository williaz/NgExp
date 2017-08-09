# NgExp
Typescript, Angular2


### Overview
- Component
  - @Component links class with a HTML tag,
  - An Angular application is therefore just a set of custom tags that interact with each other, we call these tags Components.
  - ```import { Component } from '@angular/core'```;
  - params:
    - selector: tag
    - template: `HTML`; templateUrl:.html
    - styleUrls
- bootstrapping
  - In Angular 2 your code is structured into packages called Angular Modules, or NgModules
  - @NgModule
    - to tell Angular that we want to use Angular on this page.
    - params: 
      - imports: The other Angular Modules
      - declarations: The list of components or directives belonging to this module.
      - bootstrap: Identifies the root component that Angular should bootstrap when it starts the application.
- in index.html file we will never see anything other than the tag for our root component
- SUMMARY:
  - A Component is the building block of an Angular application. It lets us create a new HTML language of custom tags and link them with javascript classes which describe the behaviour of that tag.
  - An application is composed of a tree of such Components glued together all depending from one root component. 
  - We package together related Components and supporting code into something called an Angular Module which we use to bootstrap Angular onto a webpage.
- moustache syntax: {{ }} contains JavaScript which is run by Angular and the output inserted in the HTML.
- Directive: structural directive since it changes the structure of the DOM
- When we declare an array in TypeScript we also tell it what Type of thing the array holds using Type\[] or the Array<Type> syntax.
- We can repeat the same element multiple times in Angular using the *NgFor directive
  
- HTML attribute & DOM property: Angular doesn’t manipulate HTML attributes, it manipulates DOM properties because the DOM is what actually gets displayed.
- Input Property Binding: The target inside \[] is the name of the property.
- Output Event Binding: The target inside the () is an event we want to listen for

- Domain Model
  - to isolate the data structures you are using from the component code

- An application in Angular is a set of custom components glued together in HTML via inputs and outputs. 
- @Input: 
  - tells Angular that the class's property is an input property and therefore in HTML we can bind to it using the [] input property binding syntax.
  - @Input annotation takes a parameter which is the name of the input property to the outside world,
  - We can make properties of our custom components input bindable with the [] syntax by prepending them with the @Input annotation.
  - ```@Input('joke') data: Joke;```
  
- @Output
  - ```@Output() jokeCreated = new EventEmitter<Joke>();```
  - An EventEmitter is a helper class which we can use to emit events when something happens, other components can then bind and react to these events.
  - The name between the <> on the EventEmitter is the type of thing that will be output by this property.
  - emit(): We output an event by calling the emit function, Whatever we pass to the emit function is what will be output by the property.
  - $event is a special variable and holds whatever was emitted by the EventEmitter
  - template reference variable: #prop, to get the values in HTML(points to the DOM element), pass prop.value to event function

- SUMMARY:
- ```import {Component, NgModule, Input, Output, EventEmitter} from '@angular/core';```
- Similar to input properties, we can also create output properties on our custom components using the @Output annotation.
- These output properties are always instances of the EventEmitter class and we output events by calling the emit function. Whatever we pass in to the emit function is output as the $event template variable.
- We can create local template variables by adding variables starting with the # character on any element in our template.
- By default that variable is only visible in the template that it’s declared in and points to the DOM element it’s attached to.


### ES&TypeScript
- IIFE: Immediately Invoked Function Expression
```js
function hello() {
var a = "function";
for (var i=0; i<5; i++) {
(function() {
var a = "block";
})();
}
console.log(a);
}
hello();

function something() {
var a = "block";
}
something();
```
- let
- const
  - must be immediately initialised -> syntax error
  - block-scoped
  - The important gotcha with const is that the variable is immutable, but not the value, the thing the variable points to.
  - using ```Object.freeze(…)``` -> no error, else "use strict" mode to throw SyntaxError

- Multi-Line Strings: using the back-tick character `
- expand variables using the ${variable_name} syntax

- JavaScript has first class functions.
- fat arrow(=>): to define anonymous functions
  - solved the thorny issue of stabilising the value of this

- this:
  - the value of this in a function depends on how the function is called.
  - if we use fat arrow functions the value of this inside a fat arrow function will be the same as the value of this outside the fat arrow function.

- Destructuring is a way of extracting values into variables from data stored in objects and arrays.
  - object
  - array
  - function: define the function parameter list as an object destructure pattern
```js
const {first: f} = obj; 
// translates to extract the property first and store in a constant called f.
const {first, last} = obj;
const [x, y] = arr;

function f({x=2}) { //default value
console.log(x); // Refer to x directly
}
f({x:1});//1
f({});//0
```
- For
- ForEach: no break, continue, or return
- For In: for iterating over an objects properties -> string
- For of
  - array, Set, Map
  - It works with break, continue, and return

- Map
  - initialize use set() (chainable) or an array of pairs, 
  - loop: keys(), values(), entry()
  - record the insert order
```js
let map = new Map([
[ "A", 1 ],
[ "B", 2 ],
[ "C", 3 ]
]);

for (let [key, value] of map.entries()) {
console.log(key, value);
}
```
- Set
  - initialize use add() (chainable) or an array


```js
let set = new Set(['APPLE', 'ORANGE', 'MANGO']);
```

- Promise
  - A promise is a placeholder for a future value.
  - Inside this inner function we perform our asynchronous processing and then when we are ready we call resolve()
  - If there was an error in the async task then we call the reject() function
  - to get notified: then() can take two arguments, the second argument is a error handler that gets called if the promise is rejected
  - if we add a then handler after the promise resolves or rejects the handler still gets called.
  - Promises pass an error along the chain till it finds an error handler.
  - The catch function works exactly the same way as the then error handler, it’s just clearer and more explicitly describes our intent to handle errors.

- Interface
  - We can append ? to the name of the property or function to mark it as optional

- Decorators
  - With decorators we can configure and customise our classes at design time.
  - They are just functions that can be used to add meta-data, properties or functions to the thing they are attached to.

- Module
  - TS transpile to ES5 -> CommonJS module loading system
  - export: says which of those functions can be exported, and therefore imported and used in other modules.
  - use that destructuring syntax to import/export
```js
import {square as sqr} from './utils';
import * as utils from './utils';
```
- ``` ng g <scaffold> <name>``` 
  - the generate command will create files relative to the current folder you are in
  - Available Scaffolds: component, directive, pipe, service, class, interface, enum


































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







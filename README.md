# NgExp
Typescript, Angular2


### Overview
- Component
  - @Component links class with a HTML tag,
  - An Angular application is therefore just a set of custom tags that interact with each other, we call these tags Components.
  - import { Component } from '@angular/core';
  - params:
    - selector: tag
    - template: HTML; templateUrl
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

















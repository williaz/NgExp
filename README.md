
## Template syntax
https://angular.io/guide/architecture-components#template-syntax

### Structural directives
- Structural directives shape or **reshape** the DOM's structure, typically by adding, removing, and manipulating the elements to which they are attached. 
- Directives with an asterisk, *, are structural directives
- *ngFor
- *ngIf

### Interpolation 
-  Interpolation renders a property's value as text
- ```{{ }}```

### property binding
- ```[]```
-  Interpolation {{ }} lets you render the property value as text; 
property binding [ ] lets you use the property value in a template expression.

### Event binding
- Event binding uses a set of parentheses, ( ), around the event

## Component
- Components define areas of responsibility in the user interface, or UI, that let you reuse sets of UI functionality
- 3 things
  - A component class that handles data and functionality.
  - An HTML template that determines the UI
  - Component-specific styles that define the look and feel. CSS

- An Angular application comprises a tree of components, in which each Angular component has a specific purpose and responsibility.

- @Component
  - selector: ID, HTML element name
    - convention: app-
  - templateUrl: html
  - styleUrls: CSS
  - export class
  
### Input
- @Input() decorator indicates that the property value passes in from the component's parent
  
https://angular.io/guide/component-interaction

### Output
- @Output() 

https://angular.io/guide/component-interaction
  

### Routing
https://angular.io/guide/glossary#router

- In a single-page app, instead of loading new pages, you show different components and data to the user based on where the user is in the application.
- The router lets you display full product details in separate views, each with its own URL. Routing enables navigation from one view to the next
- app.modules.ts: A route associates one or more URL paths with a component
- The **RouterLink** directive gives the router control over the anchor element.
- The **ActivatedRoute** is specific to each routed component that the Angular Router loads. It contains information about the route, its parameters, and additional data associated with the route.


### Service
- a service is an instance of a class that you can make available to any part of your application using Angular's **dependency injection** system.
- Services are the place where you **share data** between parts of your application - Components. 

https://angular.io/guide/architecture-services

### Pipes
- A pipe is a way you can transform data in your HTML template

https://angular.io/guide/pipes

### HttpClient
- Angular's HttpClientModule registers the providers your app needs to use a **single instance** of the HttpClient service throughout your app.

- app.modules.ts
  - This file contains imports and functionality that is available to the entire app.
  - Add HttpClientModule to the AppModule @NgModule() imports array to register Angular's HttpClient providers **globally**

https://angular.io/guide/http

- The async pipe returns the latest value from a stream of data and **continues** to do so for the life of a given component.

### form validating
-  Angular uses validation directives to match these attributes with validator functions in the framework.
- NgModel: Creates a FormControl instance from a domain model and binds it to a form control element.








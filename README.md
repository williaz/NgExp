
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
  






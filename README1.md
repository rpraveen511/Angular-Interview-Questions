
# Angular Interview Questions & Answers - Topic Wise

<a href='https://www.scholarhat.com/tutorial/angular/angular-interview-questions-and-answers' target="_blank">Scholarhat Angular Interview Questions</a>
<br>
<a href='https://www.interviewbit.com/angular-interview-questions/' target="_blank">Interviewbit Angular Interview Questions</a>

---

## 📚 Table of Topics

1. [Angular Basics](#angular-basics)
2. [Components & Directives](#components--directives)
3. [Modules & Dependency Injection](#modules--dependency-injection)
4. [Data Binding & Templates](#data-binding--templates)
5. [Routing](#routing)
6. [Forms](#forms)
7. [Services & HTTP](#services--http)
8. [RxJS & Observables](#rxjs--observables)
9. [Change Detection](#change-detection)
10. [Compilation & Build](#compilation--build)
11. [Testing](#testing)
12. [Security](#security)
13. [Performance & Optimization](#performance--optimization)
14. [Advanced Features](#advanced-features)
15. [Angular Versions & Updates](#angular-versions--updates)

---

## Angular Basics

### 1. What is Angular Framework?

Angular is a **TypeScript-based open-source** Application design framework.

Key characteristics:
- Development platform for efficient and sophisticated SPA
- A component based framework for building scalable web applications
- A suite of developer tools to help you develop, build, test and update code
- A collection of well integrated Libraries with features like Routing, Forms Management, Data binding, Client-server Communication, Dependency Injection, Directives, Declarative Templates, End-End Tooling

A front-end platform that makes easy to build applications with in web/mobile/desktop. It is used to build awesome SPA(single Page Application), web applications.

**[⬆ Back to Top](#table-of-topics)**

### 2. What is the difference between AngularJS and Angular?

Angular is a completely revived component-based framework in which an application is a tree of individual components.

| AngularJS | Angular |
|---- | ---------
| It is based on MVC architecture| This is based on Service/Controller|
| It uses JavaScript to build the application| Introduced the TypeScript to write the application|
| Based on controllers concept| This is a component based UI approach|
| Not a mobile friendly framework| Developed considering mobile platform|
| Difficulty in SEO friendly application development| Ease to create SEO friendly applications|

**[⬆ Back to Top](#table-of-topics)**

### 3. What is TypeScript?

TypeScript is a typed superset of JavaScript created by Microsoft that adds optional types, classes, async/await, and many other features, and compiles to plain JavaScript. Angular built entirely in TypeScript and used as a primary language.

You can install it globally as:
```cmd
npm install -g typescript
```

Example:
```typescript
function greeter(person: string) {
  return "Hello, " + person;
}

let user = "Sudheer";
document.body.innerHTML = greeter(user);
```

The greeter method allows only string type as argument.

**[⬆ Back to Top](#table-of-topics)**

### 4. What is Angular CLI?

Angular CLI(**Command Line Interface**) is a command line interface to scaffold and build angular apps using nodejs style (commonJs) modules.

Installation:
```
npm install @angular/cli@latest
```

Common commands:
- **Creating New Project:** `ng new <project-name>`
- **Generating Components, Directives & Services:** `ng generate/g <feature-name>`
  - `ng generate class my-new-class`
  - `ng generate component my-new-component`
  - `ng generate directive my-new-directive`
  - `ng generate service my-new-service`
  - `ng generate module my-new-module`
  - `ng generate pipe my-new-pipe`
- **Running the Project:** `ng serve`

**[⬆ Back to Top](#table-of-topics)**

### 5. What are the case types in Angular?

Angular uses capitalization conventions to distinguish the names of various types:

1. **camelCase:** Symbols, properties, methods, pipe names, non-component directive selectors, constants use lowercase on the first letter. Example: "selectedUser"
2. **UpperCamelCase (or PascalCase):** Class names, including components, interfaces, NgModules, directives, and pipes use uppercase on the first letter
3. **dash-case (or "kebab-case"):** Descriptive file names and component selectors use dashes between words. Example: "app-user-list"
4. **UPPER_UNDERSCORE_CASE:** All constants use capital letters connected with underscores. Example: "NUMBER_OF_USERS"

**[⬆ Back to Top](#table-of-topics)**

### 6. What is the browser support for Angular?

Angular supports most recent browsers:

| Browser | Version |
|---- | --------- |
| Chrome | latest |
| Firefox | latest |
| Edge | 2 most recent major versions |
| IE | 11, 10, 9 |
| Safari | 2 most recent major versions |
| IE Mobile | 11 |
| iOS | 2 most recent major versions |
| Android | 7.0, 6.0, 5.0, 5.1, 4.4 |

**[⬆ Back to Top](#table-of-topics)**

### 7. What are the key components of Angular?

Angular has the following key components:

1. **Modules:** A set of angular basic building blocks like component, directives, services etc. An application is divided into logical pieces
2. **Component:** Basic building blocks of angular application to control HTML views
3. **Templates:** Represent the views of an Angular application
4. **Services:** Used to create components which can be shared across the entire application
5. **Metadata:** Used to decorate a class so that it can configure the expected behavior of the class

**[⬆ Back to Top](#table-of-topics)**

---

## Components & Directives

### 8. What are components?

Components are the most basic UI building blocks of an application.

A component includes:
- TypeScript class with a @Component() decorator
- HTML template
- Optional CSS styles

@Component specifies:
- A selector that defines how the component is used in a template
- HTML elements in your template that match this selector become instances of the component
- An HTML template that instructs Angular how to render the component
- An optional set of CSS styles

Example:
```typescript
import { Component } from '@angular/core';

@Component ({
   selector: 'my-app',
   template: ` <div>
  <h1>{{title}}</h1>
  <div>Learn Angular6 with examples</div>
   </div> `,
})

export class AppComponent {
   title: string = 'Welcome to Angular world';
}
```

**[⬆ Back to Top](#table-of-topics)**

### 9. What are directives?

Directives **add behaviour to an existing DOM element** or an existing component instance.

Example:
```typescript
import { Directive, ElementRef } from '@angular/core';

@Directive({ selector: '[myHighlight]' })
export class HighlightDirective {
  constructor(el: ElementRef) {
   el.nativeElement.style.backgroundColor = 'yellow';
  }
}
```

Usage:
```html
<p myHighlight>Highlight me!</p>
```

**[⬆ Back to Top](#table-of-topics)**

### 10. What are the various kinds of directives?

There are mainly three kinds of directives:

1. **Components** — Directives with a template
2. **Structural directives** — Change the DOM layout by adding and removing DOM elements
3. **Attribute directives** — Change the appearance or behavior of an element, component, or another directive

**[⬆ Back to Top](#table-of-topics)**

### 11. How do you create directives using CLI?

Use the CLI command:
```
ng generate directive <directive-name>
```

This creates the source file(`src/app/components/directivename.directive.ts`), the respective test file(.spec.ts) and declares the directive class file in root module.

**[⬆ Back to Top](#table-of-topics)**

### 12. Give an example for attribute directives?

Creating a highlighter directive:

1. Create HighlightDirective class:
```typescript
import { Directive, ElementRef } from '@angular/core';

@Directive({
  selector: '[appHighlight]'
})
export class HighlightDirective {
  constructor(el: ElementRef) {
   el.nativeElement.style.backgroundColor = 'red';
  }
}
```

2. Apply the attribute directive:
```html
<p appHighlight>Highlight me!</p>
```

3. Run the application:
```
ng serve
```

**[⬆ Back to Top](#table-of-topics)**

### 13. What are the differences between Component and Directive?

| Component | Directive |
|---- | ---------
| To register a component we use @Component meta-data annotation  | To register directives we use @Directive meta-data annotation |
| Components are typically used to create UI widgets| Directives are used to design re-usable components |
| Component is used to break up the application into smaller components| Directives are used to add behavior to an existing DOM element|
| Only one component can be present per DOM element | Many directives can be used per DOM element |
| @View decorator or templateurl/template are mandatory | Directive doesn't use View|

**Note:** A component(@component) is a directive-with-a-template.

**[⬆ Back to Top](#table-of-topics)**

### 14. What is a template?

A template is an HTML view where you can **display data by binding controls to properties** of an Angular component.

**Using inline template:**
```typescript
import { Component } from '@angular/core';

@Component ({
   selector: 'my-app',
   template: '
  <div>
   <h1>{{title}}</h1>
   <div>Learn Angular</div>
  </div>
   '
})

export class AppComponent {
   title: string = 'Hello World';
}
```

**Using separate template file:**
```typescript
import { Component } from '@angular/core';

@Component ({
   selector: 'my-app',
   templateUrl: 'app/app.component.html'
})

export class AppComponent {
   title: string = 'Hello World';
}
```

**[⬆ Back to Top](#table-of-topics)**

### 15. What is the option to choose between inline and external template file?

You can store your component's template in one of two places:
- **Inline** using the template property
- **External** using the templateUrl property

For small portions of code, use inline template. For bigger views, use external template file.

By default, Angular CLI generates components with a template file. Override with:
```
ng generate component hero -it
```

**[⬆ Back to Top](#table-of-topics)**

### 16. How do you select an element within a component template?

Use `@ViewChild` directive to access elements in the view directly:

```html
<input #uname>
```

Define view child directive and access it in ngAfterViewInit:
```typescript
@ViewChild('uname') input;

ngAfterViewInit() {
  console.log(this.input.nativeElement.value);
}
```

Alternatively, use ElementRef:
```typescript
constructor(myElement: ElementRef) {
   el.nativeElement.style.backgroundColor = 'yellow';
}
```

**[⬆ Back to Top](#table-of-topics)**

### 17. What is host property in css?

The `:host` pseudo-class selector is used to target styles in the element that hosts the component.

Example:
```css
:host {
  display: block;
  border: 1px solid black;
  padding: 20px;
}
```

**[⬆ Back to Top](#table-of-topics)**

### 18. How do you create displayBlock components?

Create components with display: block style using `displayBlock` option:

```
ng generate component my-component --displayBlock
```

Or set it as default in Angular.json:
```json
"schematics.@schematics/angular:component.displayBlock": true
```

**[⬆ Back to Top](#table-of-topics)**

---

## Modules & Dependency Injection

### 19. What is a module?

Modules are logical boundaries in your application. The application is divided into separate modules to separate the functionality.

Example of **app.module.ts** root module:
```typescript
import { NgModule }      from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent }  from './app.component';

@NgModule ({
   imports:      [ BrowserModule ],
   declarations: [ AppComponent ],
   bootstrap:    [ AppComponent ],
   providers: []
})
export class AppModule { }
```

The @NgModule decorator has important options:
1. **imports:** Import other dependent modules (BrowserModule is required for web apps)
2. **declarations:** Define components in the respective module
3. **bootstrap:** Tell Angular which Component to bootstrap
4. **providers:** Configure injectable objects available in the injector
5. **entryComponents:** Set of components dynamically loaded into the view

**[⬆ Back to Top](#table-of-topics)**

### 20. What is dependency injection in Angular?

Dependency injection lets you declare the dependencies of your Typescript classes without taking care of their instantiation. Angular handles the instantiation for you and lets you write more testable and flexible code.

Instead of creating objects inside a class, you request them from external sources, making your code more modular and testable.

**[⬆ Back to Top](#table-of-topics)**

### 21. What is a service?

A service is used when a common functionality needs to be provided to various modules. Services allow for greater separation of concerns and better modularity.

Example:
```typescript
import { Injectable } from '@angular/core';
import { Http } from '@angular/http';

@Injectable({
  providedIn: 'root',
})
export class RepoService{
  constructor(private http: Http){
  }

  fetchAll(){
  return this.http.get('https://api.github.com/repositories');
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 22. How is Dependency Hierarchy formed?

The dependency hierarchy is formed through Angular's injector system where parent injectors can provide dependencies to child injectors, creating a hierarchical structure of dependency resolution.

**[⬆ Back to Top](#table-of-topics)**

### 23. What are the differences between AngularJS and Angular with respect to dependency injection?

| AngularJS | Angular |
|---- | ---------
| Dependency injection tokens are always strings  | Tokens can have different types. They are often classes and sometimes can be strings |
| There is exactly one injector even though it is a multi-module applications | There is a tree hierarchy of injectors, with a root injector and an additional injector for each component |

**[⬆ Back to Top](#table-of-topics)**

### 24. What is a provider?

A provider is an instruction to the Dependency Injection system on how to obtain a value for a dependency (services created).

Create using Angular CLI:
```
ng generate service my-service
```

Created service:
```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class MyService {
}
```

**[⬆ Back to Top](#table-of-topics)**

### 25. What is the recommendation for provider scope?

You should always provide your service in the root injector unless there is a case where you want the service to be available only if you import a particular @NgModule.

**[⬆ Back to Top](#table-of-topics)**

### 26. How do you restrict provider scope to a module?

Two ways to restrict service provider scope:

1. **Using providedIn in service:**
```typescript
import { Injectable } from '@angular/core';
import { SomeModule } from './some.module';

@Injectable({
  providedIn: SomeModule,
})
export class SomeService {
}
```

2. **Declare provider for the service in module:**
```typescript
import { NgModule } from '@angular/core';
import { SomeService } from './some.service';

@NgModule({
  providers: [SomeService],
})
export class SomeModule {
}
```

**[⬆ Back to Top](#table-of-topics)**

### 27. How do you provide a singleton service?

Two ways to provide a singleton service:

1. **Using providedIn (preferred since Angular 6.0):**
```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class MyService {
}
```

2. **Include in root module:**
```typescript
@NgModule({
  ...
  providers: [MyService],
  ...
})
```

**[⬆ Back to Top](#table-of-topics)**

### 28. What are the different ways to remove duplicate service registration?

Three ways to prevent duplicate service registration:

1. Use the providedIn syntax instead of registering in the module
2. Separate your services into their own module
3. Define forRoot() and forChild() methods in the module

**[⬆ Back to Top](#table-of-topics)**

### 29. How does forRoot method helpful to avoid duplicate router instances?

If the `RouterModule` module didn't have forRoot() static method, each feature module would instantiate a new Router instance. After using forRoot():
- Root application module imports `RouterModule.forRoot(...)`
- Feature modules import `RouterModule.forChild(...)` which doesn't instantiate another Router

**[⬆ Back to Top](#table-of-topics)**

### 30. Is it mandatory to use injectable on every service class?

No. The `@Injectable()` decorator is not strictly required if the class has other Angular decorators or doesn't have any dependencies. But it's recommended for services with dependencies.

**[⬆ Back to Top](#table-of-topics)**

### 31. What is an optional dependency?

The optional dependency is a parameter decorator that marks a parameter as an optional dependency. The DI framework provides null if the dependency is not found.

Example:
```typescript
import { Optional } from '@angular/core';

constructor(@Optional() private logger?: Logger) {
  if (this.logger) {
  this.logger.log('This is an optional dependency message');
  } else {
  console.log('The logger is not registered');
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 32. What are the types of injector hierarchies?

Two types of injector hierarchies in Angular:

1. **ModuleInjector hierarchy:** Configured on a module level using @NgModule() or @Injectable()
2. **ElementInjector hierarchy:** Created implicitly at each DOM element (empty by default)

**[⬆ Back to Top](#table-of-topics)**

### 33. How do you configure injectors with providers at different levels?

Configure injectors with providers at three levels:

1. In the `@Injectable()` decorator for the service itself
2. In the `@NgModule()` decorator for an NgModule
3. In the `@Component()` decorator for a component

**[⬆ Back to Top](#table-of-topics)**

### 34. What is a DI token?

A DI token is a lookup token associated with a dependency provider. The injector maintains an internal token-provider map that it references when asked for a dependency.

Example:
```typescript
const BASE_URL = new InjectionToken<string>('BaseUrl');
const injector =
   Injector.create({providers: [{provide: BASE_URL, useValue: 'http://some-domain.com'}]});
const url = injector.get(BASE_URL);
```

**[⬆ Back to Top](#table-of-topics)**

### 35. What is metadata?

Metadata is used to decorate a class so that it can configure the expected behavior of the class. The metadata is represented by decorators.

**Decorators are a design pattern that is used to separate modification of a class:**

1. **Class decorators:** @Component and @NgModule
2. **Property decorators:** @Input and @Output
3. **Method decorators:** @HostListener
4. **Parameter decorators:** @Inject, @Optional

**[⬆ Back to Top](#table-of-topics)**

### 36. What are the class decorators in Angular?

Class decorators that appear immediately before a class definition:

1. @Component()
2. @Directive()
3. @Pipe()
4. @Injectable()
5. @NgModule()

**[⬆ Back to Top](#table-of-topics)**

### 37. What are class field decorators?

Class field decorators declared immediately before a field in a class definition:

```typescript
@Input() myProperty;
@Output() myEvent = new EventEmitter();
```

Examples: @Input and @Output

**[⬆ Back to Top](#table-of-topics)**

### 38. What is declarable in Angular?

Declarable is a class type that you can add to the declarations list of an NgModule.

Class types that can be declared: components, directives, and pipes

Structure:
```typescript
declarations: [
  YourComponent,
  YourPipe,
  YourDirective
],
```

**[⬆ Back to Top](#table-of-topics)**

### 39. What are the restrictions on declarable classes?

Below classes shouldn't be declared:

1. A class that's already declared in another NgModule
2. NgModule classes
3. Service classes
4. Helper classes

**[⬆ Back to Top](#table-of-topics)**

### 40. What is Angular DSL?

Angular DSL (Domain-Specific Language) is Angular's own Domain Specific Language which allows you to write Angular specific html-like syntax on top of normal html. It has its own compiler that compiles this syntax to html that the browser can understand.

Three main syntax in Angular DSL:
1. `()`: Used for Output and DOM events
2. `[]`: Used for Input and specific DOM element attributes
3. `*`: Structural directives (*ngFor or *ngIf) will affect/change the DOM structure

**[⬆ Back to Top](#table-of-topics)**

### 41. What is a shared module?

The Shared Module is the module in which you put commonly used directives, pipes, and components into one module that is shared throughout the application.

Example:
```typescript
import { CommonModule } from '@angular/common';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { UserComponent } from './user.component';
import { NewUserDirective } from './new-user.directive';
import { OrdersPipe } from './orders.pipe';

@NgModule({
 imports:      [ CommonModule ],
 declarations: [ UserComponent, NewUserDirective, OrdersPipe ],
 exports:      [ UserComponent, NewUserDirective, OrdersPipe,
         CommonModule, FormsModule ]
})
export class SharedModule { }
```

**[⬆ Back to Top](#table-of-topics)**

### 42. Can I share services using modules?

No, it is not recommended to share services by importing module. Import modules when you want to use directives, pipes, and components only. The best approach to get a hold of shared services is through Angular dependency injection.

**[⬆ Back to Top](#table-of-topics)**

### 43. What is a bootstrapping module?

Every application has at least one Angular module, the root module that you bootstrap to launch the application is called the bootstrapping module (commonly known as AppModule).

Example structure:
```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { HttpClientModule } from '@angular/common/http';

import { AppComponent } from './app.component';

@NgModule({
  declarations: [
  AppComponent
  ],
  imports: [
  BrowserModule,
  FormsModule,
  HttpClientModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

**[⬆ Back to Top](#table-of-topics)**

### 44. What are feature modules?

Feature modules are NgModules used for organizing code. Create using Angular CLI:

```
ng generate module MyCustomFeature
```

Creates a folder `my-custom-feature` with `my-custom-feature.module.ts`:

```typescript
import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';

@NgModule({
  imports: [
  CommonModule
  ],
  declarations: []
})
export class MyCustomFeature { }
```

**[⬆ Back to Top](#table-of-topics)**

### 45. What are the imported modules in CLI generated feature modules?

Two JavaScript import statements at the top:

1. **NgModule:** To use the `@NgModule` decorator
2. **CommonModule:** Provides common directives such as `ngIf` and `ngFor`

**[⬆ Back to Top](#table-of-topics)**

### 46. What are the differences between ngmodule and javascript module?

| NgModule | JavaScript module |
|---- | --------- |
| NgModule bounds declarable classes only | There is no restriction classes |
| List the module's classes in declarations array only | Can define all member classes in one giant file |
| It only export the declarable classes it owns or imports from other modules| It can export any classes |
| Extend the entire application with services by adding providers to provides array | Can't extend the application with services |

**[⬆ Back to Top](#table-of-topics)**

### 47. What are the possible errors with declarations?

Two common possible errors:

1. If you use a component without declaring it, Angular returns an error message
2. If you try to declare the same class in more than one module, compiler emits an error

**[⬆ Back to Top](#table-of-topics)**

### 48. What are the steps to use declaration elements?

Steps to follow:

1. Create the element(component, directive and pipes) and export it from the file where you wrote it
2. Import it into the appropriate module
3. Declare it in the @NgModule declarations array

**[⬆ Back to Top](#table-of-topics)**

### 49. What happens if browserModule used in feature module?

If you import `BrowserModule` into a lazy loaded feature module, Angular returns an error. Use `CommonModule` instead. BrowserModule's providers are for the entire app so it should only be in the root module.

**[⬆ Back to Top](#table-of-topics)**

### 50. What are the types of feature modules?

Five categories of feature modules:

1. **Domain:** Deliver a user experience dedicated to a particular application domain
2. **Routed:** Domain feature modules whose top components are the targets of router navigation routes
3. **Routing:** Provides routing configuration for another module
4. **Service:** Provides utility services such as data access and messaging
5. **Widget:** Makes components, directives, and pipes available to external modules

**[⬆ Back to Top](#table-of-topics)**

### 51. What is the purpose of common module?

The commonly-needed services, pipes, and directives provided by @angular/common module. HttpClientModule is available under @angular/common/http.

**[⬆ Back to Top](#table-of-topics)**

### 52. What happens if I import the same module twice?

If multiple modules imports the same module then angular evaluates it only once (When it encounters the module first time). It follows this condition even the module appears at any level in a hierarchy of imported NgModules.

**[⬆ Back to Top](#table-of-topics)**

### 53. What classes should not be added to declarations?

The below class types shouldn't be added to declarations:

1. A class which is already declared in any another module
2. Directives imported from another module
3. Module classes
4. Service classes
5. Non-Angular classes and objects, such as strings, numbers, functions, entity models, configurations, business logic, and helper classes

**[⬆ Back to Top](#table-of-topics)**

### 54. What is ngcc?

The ngcc (Angular Compatibility Compiler) is a tool which upgrades node_modules compiled with non-ivy ngc into ivy compliant format. The `postinstall` script from package.json will make sure your node_modules will be compatible with the Ivy renderer.

```json
"scripts": {
   "postinstall": "ngcc"
}
```

Whereas, Ivy compiler (ngtsc), which compiles Ivy-compatible code.

**[⬆ Back to Top](#table-of-topics)**

---

## Data Binding & Templates

### 55. What is a data binding?

Data binding is a core concept in Angular that allows you to define communication between a component and the DOM, making it very easy to define interactive applications.

There are four forms of data binding (divided as 3 categories):

1. **From the Component to the DOM:**

   **Interpolation:** {{ value }}
   ```html
   <li>Name: {{ user.name }}</li>
   <li>Address: {{ user.address }}</li>
   ```

   **Property binding:** [property]="value"
   ```html
   <input type="email" [value]="user.email">
   ```

2. **From the DOM to the Component:**

   **Event binding:** (event)="function"
   ```html
   <button (click)="logout()"></button>
   ```

3. **Two-way binding:**

   **Two-way data binding:** [(ngModel)]="value"
   ```html
   <input type="email" [(ngModel)]="user.email">
   ```

**[⬆ Back to Top](#table-of-topics)**

### 56. How do you categorize data binding types?

Binding types grouped into three categories by the direction of data flow:

| Data direction | Syntax | Type |
|---- | --------- | ---- |
| From the source-to-view (One-way)  | 1. {{expression}} 2. [target]="expression" 3. bind-target="expression" | Interpolation, Property, Attribute, Class, Style|
| From view-to-source (One-way) | 1. (target)="statement" 2. on-target="statement" | Event |
| View-to-source-to-view (Two-way)| 1. [(target)]="expression" 2. bindon-target="expression"| Two-way |

**[⬆ Back to Top](#table-of-topics)**

### 57. What is interpolation?

Interpolation is a special syntax that Angular converts into property binding. It's a convenient alternative to property binding represented by double curly braces({{}}).

Example:
```html
<h3>
  {{title}}
  <img src="{{url}}" style="height:30px">
</h3>
```

Angular evaluates the title and url properties and fills in the blanks.

**[⬆ Back to Top](#table-of-topics)**

### 58. What are template expressions?

A template expression produces a value similar to any Javascript expression. Angular executes the expression and assigns it to a property of a binding target.

Example:
```html
<h3>{{username}}, welcome to Angular</h3>
```

Below javascript expressions are prohibited in template expression:
1. assignments (=, +=, -=, ...)
2. new
3. chaining expressions with ; or ,
4. increment and decrement operators (++ and --)

**[⬆ Back to Top](#table-of-topics)**

### 59. What are template statements?

A template statement responds to an event raised by a binding target such as an element, component, or directive.

Example of button click event:
```html
<button (click)="editProfile()">Edit Profile</button>
```

The below JavaScript syntax expressions are not allowed:
1. new
2. increment and decrement operators, ++ and --
3. operator assignment, such as += and -=
4. the bitwise operators | and &
5. the template expression operators

**[⬆ Back to Top](#table-of-topics)**

### 60. What is the purpose of ngFor directive?

The ngFor directive is used in the template to display each item in the list.

Example:
```html
<li *ngFor="let user of users">
  {{ user }}
</li>
```

The user variable is a **template input variable**

**[⬆ Back to Top](#table-of-topics)**

### 61. What is the purpose of ngIf directive?

The ngIf directive inserts or removes an element based on a truthy/falsy condition.

Example:
```html
<p *ngIf="user.age > 18">You are not eligible for student pass!</p>
```

**Note:** Angular isn't showing and hiding the message. It is adding and removing the paragraph element from the DOM for better performance.

**[⬆ Back to Top](#table-of-topics)**

### 62. What is the purpose of ngSwitch directive?

**NgSwitch** directive is similar to JavaScript switch statement which displays one element from among several possible elements, based on a switch condition.

Example:
```html
<div [ngSwitch]="currentBrowser.name">
  <chrome-browser    *ngSwitchCase="'chrome'"    [item]="currentBrowser"></chrome-browser>
  <firefox-browser   *ngSwitchCase="'firefox'"     [item]="currentBrowser"></firefox-browser>
  <opera-browser     *ngSwitchCase="'opera'"  [item]="currentBrowser"></opera-browser>
  <safari-browser     *ngSwitchCase="'safari'"   [item]="currentBrowser"></safari-browser>
  <ie-browser  *ngSwitchDefault           [item]="currentItem"></ie-browser>
</div>
```

**[⬆ Back to Top](#table-of-topics)**

### 63. What is the index property in ngFor directive?

The index property returns the zero-based index of the item in each iteration.

Example:
```html
<div *ngFor="let todo of todos; let i=index">{{i + 1}} - {{todo.name}}</div>
```

**[⬆ Back to Top](#table-of-topics)**

### 64. What is the purpose of ngFor trackBy?

The main purpose of using *ngFor with trackBy option is **performance optimization**. A small change to one item can trigger a cascade of DOM manipulations. You can help Angular track which items added or removed by providing a `trackBy` function.

Example:
```html
<div *ngFor="let todo of todos; trackBy: trackByTodos">
  ({{todo.id}}) {{todo.name}}
</div>
```

Define the trackByTodos method:
```typescript
trackByTodos(index: number, item: Todo): number { return todo.id; }
```

**[⬆ Back to Top](#table-of-topics)**

### 65. How to set ngFor and ngIf on the same element?

You cannot have multiple template bindings on one element. Use either ng-container or ng-template.

Incorrect:
```html
<ul *ngIf="items" *ngFor="let item of items">
  <li></li>
</ul>
```

Correct:
```html
<ng-container *ngIf="items">
  <ul *ngFor="let item of items">
  <li></li>
  </ul>
</ng-container>
```

**[⬆ Back to Top](#table-of-topics)**

### 66. What happens if you use script tag inside template?

Angular recognizes the value as unsafe and automatically sanitizes it, which removes the `script` tag but keeps safe content. This way it eliminates the risk of script injection attacks.

Example:
```typescript
export class InnerHtmlBindingComponent {
  htmlSnippet = 'Template <script>alert("0wned")</script> <b>Syntax</b>';
}
```

**[⬆ Back to Top](#table-of-topics)**

### 67. What are the lifecycle hooks available?

Angular application goes through an entire set of processes or has a lifecycle:

1. **ngOnChanges:** Called when the value of a data bound property changes
2. **ngOnInit:** Called after Angular first displays the data-bound properties
3. **ngDoCheck:** For detection and to act on changes that Angular can't detect
4. **ngAfterContentInit:** Called after Angular projects external content into the component's view
5. **ngAfterContentChecked:** Called after Angular checks the content projected into the component
6. **ngAfterViewInit:** Called after Angular initializes the component's views and child views
7. **ngAfterViewChecked:** Called after Angular checks the component's views and child views
8. **ngOnDestroy:** The cleanup phase just before Angular destroys the directive/component

**[⬆ Back to Top](#table-of-topics)**

### 68. What is the difference between constructor and ngOnInit?

TypeScript classes has a default method called **constructor** which is normally used for the initialization purpose. Whereas **ngOnInit** is specific to Angular, especially used to define Angular bindings.

Even though constructor getting called first, it is preferred to move all of your Angular bindings to ngOnInit method.

Example:
```typescript
export class App implements OnInit{
  constructor(){
   //called first time before the ngOnInit()
  }

  ngOnInit(){
   //called after the constructor and called after the first ngOnChanges()
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 69. What is the purpose of async pipe?

The AsyncPipe subscribes to an observable or promise and returns the latest value it has emitted. When a new value is emitted, the pipe marks the component to be checked for changes.

Example:
```typescript
@Component({
  selector: 'async-observable-pipe',
  template: `<div><code>observable|async</code>:
   Time: {{ time | async }}</div>`
})
export class AsyncObservablePipeComponent {
  time = new Observable(observer =>
  setInterval(() => observer.next(new Date().toString()), 2000)
  );
}
```

**[⬆ Back to Top](#table-of-topics)**

### 70. What is the safe navigation operator?

The safe navigation operator(?) (or known as Elvis Operator) is used to guard against `null` and `undefined` values in property paths when you are not aware whether a path exists or not.

Example:
```html
<p>The user firstName is: {{user?.fullName.firstName}}</p>
```

Angular stops evaluating the expression when it hits the first null value and renders the view without any errors.

**[⬆ Back to Top](#table-of-topics)**

---

## Pipes

### 71. What are pipes?

A pipe takes in data as input and transforms it to a desired output. Pipes are used to format data for display.

Example:
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-birthday',
  template: `<p>Birthday is {{ birthday | date }}</p>`
})
export class BirthdayComponent {
  birthday = new Date(1987, 6, 18); // June 18, 1987
}
```

**[⬆ Back to Top](#table-of-topics)**

### 72. What is a parameterized pipe?

A pipe can accept any number of optional parameters to fine-tune its output. Separate the values with colons.

Example:
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-birthday',
  template: `<p>Birthday is {{ birthday | date:'dd/MM/yyyy'}}</p>` // 18/06/1987
})
export class BirthdayComponent {
  birthday = new Date(1987, 6, 18);
}
```

**[⬆ Back to Top](#table-of-topics)**

### 73. How do you chain pipes?

You can chain pipes together in potentially useful combinations.

Example:
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-birthday',
  template: `<p>Birthday is {{  birthday | date:'fullDate' | uppercase}} </p>` 
  // THURSDAY, JUNE 18, 1987
})
export class BirthdayComponent {
  birthday = new Date(1987, 6, 18);
}
```

**[⬆ Back to Top](#table-of-topics)**

### 74. What is a custom pipe?

A custom pipe is a user-defined pipe with the below key characteristics:

1. A pipe is a class decorated with @Pipe decorator
2. The pipe class implements the **PipeTransform** interface's transform method
3. The @Pipe decorator allows you to define the pipe name

Structure:
```typescript
@Pipe({name: 'myCustomPipe'})
export class MyCustomPipe implements PipeTransform {
  transform(value: any, ...args: any[]): any {
  // transformation logic
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 75. Give an example of custom pipe?

Custom pipe for finding file size based on an extension:

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({name: 'customFileSizePipe'})
export class FileSizePipe implements PipeTransform {
  transform(size: number, extension: string = 'MB'): string {
  return (size / (1024 * 1024)).toFixed(2) + extension;
  }
}
```

Usage in template:
```typescript
template: `
  <h2>Find the size of a file</h2>
  <p>Size: {{288966 | customFileSizePipe: 'GB'}}</p>
`
```

**[⬆ Back to Top](#table-of-topics)**

### 76. What is the difference between pure and impure pipe?

- **Pure pipe:** Only called when Angular detects a change in the value or the parameters passed to a pipe. Changes to primitive input values (String, Number, Boolean, Symbol) or a changed object reference trigger it.

- **Impure pipe:** Called for every change detection cycle no matter whether the value or parameters changes. Called often as every keystroke or mouse-move.

**[⬆ Back to Top](#table-of-topics)**

### 77. What is slice pipe?

The slice pipe is used to create a new Array or String containing a subset (slice) of the elements.

Syntax:
```
{{ value_expression | slice : start [ : end ] }}
```

Example:
```typescript
@Component({
  selector: 'list-pipe',
  template: `<ul>
  <li *ngFor="let i of greeting | slice:0:5">{{i}}</li>
  </ul>`
})
export class PipeListComponent {
  greeting: string[] = ['h', 'e', 'l', 'l', 'o', 'm','o', 'r', 'n', 'i', 'n', 'g'];
}
```

**[⬆ Back to Top](#table-of-topics)**

---

## Routing

### 78. What is Angular Router?

Angular Router is a mechanism in which navigation happens from one view to the next as users perform application tasks. It borrows the concepts or model of browser's application navigation.

**[⬆ Back to Top](#table-of-topics)**

### 79. What is the purpose of base href tag?

The routing application should add <base> element to the index.html as the first child in the <head> tag to indicate how to compose navigation URLs.

Example:
```html
<base href="/">
```

**[⬆ Back to Top](#table-of-topics)**

### 80. What are the router imports?

The Angular Router is available in library named `@angular/router`:

```typescript
import { RouterModule, Routes } from '@angular/router';
```

**[⬆ Back to Top](#table-of-topics)**

### 81. What is router outlet?

The RouterOutlet is a directive from the router library that acts as a placeholder marking the spot in the template where the router should display the components.

```html
<router-outlet></router-outlet>
<!-- Routed components go here -->
```

**[⬆ Back to Top](#table-of-topics)**

### 82. What are router links?

The RouterLink is a directive on the anchor tags that gives the router control over those elements. Since the navigation paths are fixed, you can assign string values to router-link directive.

Example:
```html
<h1>Angular Router</h1>
<nav>
  <a routerLink="/todosList" >List of todos</a>
  <a routerLink="/completed" >Completed todos</a>
</nav>
<router-outlet></router-outlet>
```

**[⬆ Back to Top](#table-of-topics)**

### 83. What are active router links?

RouterLinkActive is a directive that toggles css classes for active RouterLink bindings based on the current RouterState.

Example:
```html
<h1>Angular Router</h1>
<nav>
  <a routerLink="/todosList" routerLinkActive="active">List of todos</a>
  <a routerLink="/completed" routerLinkActive="active">Completed todos</a>
</nav>
<router-outlet></router-outlet>
```

**[⬆ Back to Top](#table-of-topics)**

### 84. What is router state?

RouterState is a tree of activated routes. Every node in this tree knows about the "consumed" URL segments, the extracted parameters, and the resolved data.

Example:
```typescript
@Component({templateUrl:'template.html'})
class MyComponent {
  constructor(router: Router) {
  const state: RouterState = router.routerState;
  const root: ActivatedRoute = state.root;
  const child = root.firstChild;
  const id: Observable<string> = child.params.map(p => p.id);
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 85. What are router events?

During each navigation, the Router emits navigation events through the Router.events property allowing you to track the lifecycle of the route.

The sequence of router events:
1. NavigationStart
2. RouteConfigLoadStart
3. RouteConfigLoadEnd
4. RoutesRecognized
5. GuardsCheckStart
6. ChildActivationStart
7. ActivationStart
8. GuardsCheckEnd
9. ResolveStart
10. ResolveEnd
11. ActivationEnd
12. ChildActivationEnd
13. NavigationEnd
14. NavigationCancel
15. NavigationError
16. Scroll

**[⬆ Back to Top](#table-of-topics)**

### 86. What is activated route?

ActivatedRoute contains the information about a route associated with a component loaded in an outlet.

Example:
```typescript
@Component({...})
class MyComponent {
  constructor(route: ActivatedRoute) {
  const id: Observable<string> = route.params.pipe(map(p => p.id));
  const url: Observable<string> = route.url.pipe(map(segments => segments.join('')));
  const user = route.data.pipe(map(d => d.user));
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 87. How do you define routes?

A router must be configured with a list of route definitions via the `RouterModule.forRoot()` method:

```typescript
const appRoutes: Routes = [
  { path: 'todo/:id',      component: TodoDetailComponent },
  {
  path: 'todos',
  component: TodosListComponent,
  data: { title: 'Todos List' }
  },
  { path: '',
  redirectTo: '/todos',
  pathMatch: 'full'
  },
  { path: '**', component: PageNotFoundComponent }
];

@NgModule({
  imports: [
  RouterModule.forRoot(
    appRoutes,
    { enableTracing: true } // for debugging purposes only
  )
  ],
  ...
})
export class AppModule { }
```

**[⬆ Back to Top](#table-of-topics)**

### 88. What is the purpose of Wildcard route?

If the URL doesn't match any predefined routes, the router throws an error. Use a wildcard route with a path consisting of two asterisks to match every URL.

Example:
```typescript
{ path: '**', component: PageNotFoundComponent }
```

**[⬆ Back to Top](#table-of-topics)**

### 89. Do I need a Routing Module always?

No, the Routing Module is a design choice. You can merge the routing configuration directly into the companion module when the configuration is simple. It's recommended to use a Routing Module when the configuration is complex.

**[⬆ Back to Top](#table-of-topics)**

### 90. How do you detect route change in Angular?

Subscribe to router to detect the changes:

```typescript
import { Component } from '@angular/core';
import { Router, Event, NavigationStart, NavigationEnd, NavigationError } from '@angular/router';

@Component({
  selector: 'app-root',
  template: `<router-outlet></router-outlet>`
})
export class AppComponent {

  constructor(private router: Router) {

    this.router.events.subscribe((event: Event) => {
      if (event instanceof NavigationStart) {
        // Show loading indicator
      }

      if (event instanceof NavigationEnd) {
        // Hide loading indicator
      }

      if (event instanceof NavigationError) {
        console.log(event.error); // For debugging
      }
    });
   }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 91. How do you get the current route?

Use the `url` property of router package:

1. Import Router:
```typescript
import { Router } from '@angular/router';
```

2. Inject router:
```typescript
constructor(private router: Router ) {}
```

3. Access url:
```typescript
console.log(this.router.url); //  /routename
```

**[⬆ Back to Top](#table-of-topics)**

### 92. What is lazy loading?

Lazy loading is a concept of Angular Routing that helps us to download the web pages in chunks instead of downloading everything in a big bundle. It's used for lazy loading by asynchronously loading the feature module for routing whenever required using the property `loadChildren`.

Example:
```typescript
const routes: Routes = [
  {
  path: 'customers',
  loadChildren: () => import('./customers/customers.module').then(module => module.CustomersModule)
  },
  {
  path: 'orders',
  loadChildren: () => import('./orders/orders.module').then(module => module.OrdersModule)
  },
  {
  path: '',
  redirectTo: '',
  pathMatch: 'full'
  }
];
```

**[⬆ Back to Top](#table-of-topics)**

### 93. Is Angular supports dynamic imports?

Yes, Angular 8 supports dynamic imports in router configuration. Using the import statement for lazy loading makes it clear during compile time.

Before (with potential typos):
```typescript
{path: 'user', loadChildren: './users/user.module#UserModulee'},
```

After (with dynamic imports):
```typescript
{path: 'user', loadChildren: () => import('./users/user.module').then(m => m.UserModule)};
```

**[⬆ Back to Top](#table-of-topics)**

### 94. What are the Route Parameters? Could you explain each of them?

Three types of route parameters:

1. **Path parameters:** Dynamic segments in the URL path specified by a colon (":") followed by the parameter name
   ```typescript
   { path: 'users/:id', component: UserComponent }
   ```

2. **Query parameters:** Additional information in the URL as key-value pairs appended after "?"
   ```typescript
   { path: 'search', component: SearchComponent }
   // URL: "/search?query=angular"
   ```

3. **Optional parameters:** Route parameters made optional by placing a question mark ("?") after the parameter name
   ```typescript
   { path: 'products/:id/:category?', component: ProductComponent }
   ```

**[⬆ Back to Top](#table-of-topics)**

---

## Forms

### 95. What are reactive forms?

Reactive forms is a model-driven approach for creating forms in a reactive style where form inputs changes over time are represented as streams.

Steps to create reactive forms:

1. Register the reactive forms module:
```typescript
import { ReactiveFormsModule } from '@angular/forms';

@NgModule({
  imports: [
  ReactiveFormsModule
  ],
})
export class AppModule { }
```

2. Create a new FormControl instance:
```typescript
import { Component } from '@angular/core';
import { FormControl } from '@angular/forms';

@Component({
  selector: 'user-profile',
  styleUrls: ['./user-profile.component.css']
})
export class UserProfileComponent {
  userName = new FormControl('');
}
```

3. Register the FormControl in the template:
```html
<label>
  User name:
  <input type="text" [formControl]="userName">
</label>
```

**[⬆ Back to Top](#table-of-topics)**

### 96. What are template driven forms?

Template driven forms are model-driven forms where you write the logic, validations, controls etc, in the template part of the code using directives.

Steps to create:

1. Import the FormsModule:
```typescript
import { FormsModule } from '@angular/forms'

@NgModule({
  imports: [
  FormsModule
  ],
})
export class AppModule { }
```

2. Bind the form from template using ngModel:
```html
<input type="text" class="form-control" id="name"
     required
     [(ngModel)]="model.name" name="name">
```

3. Attach NgForm directive:
```html
<form #registerForm="ngForm">
```

4. Apply validation messages:
```html
<label for="name">Name</label>
<input type="text" class="form-control" id="name"
     required
     [(ngModel)]="model.name" name="name"
     #name="ngModel">
<div [hidden]="name.valid || name.pristine"
   class="alert alert-danger">
  Please enter your name
</div>
```

5. Submit the form with ngSubmit:
```html
<form (ngSubmit)="onSubmit()" #heroForm="ngForm">
  <button type="submit" class="btn btn-success" [disabled]="!registerForm.form.valid">Submit</button>
</form>
```

**[⬆ Back to Top](#table-of-topics)**

### 97. What are dynamic forms?

Dynamic forms is a pattern in which we build a form dynamically based on metadata that describes a business object model. You can create them based on reactive form API.

**[⬆ Back to Top](#table-of-topics)**

### 98. What are the differences between reactive forms and template driven forms?

| Feature | Reactive | Template-Driven |
|---- |---- | --------- |
| Form model setup | Created (FormControl instance) in component explicitly | Created by directives  |
| Data updates | Synchronous | Asynchronous |
| Form custom validation | Defined as Functions | Defined as Directives |
| Testing | No interaction with change detection cycle | Need knowledge of the change detection process |
| Mutability | Immutable | Mutable |
| Scalability | More scalable | Less scalable |

**[⬆ Back to Top](#table-of-topics)**

### 99. What are the different ways to group form controls?

Two ways of grouping:

1. **FormGroup:** Defines a form with a fixed set of controls that can be managed together
```typescript
import { Component } from '@angular/core';
import { FormGroup, FormControl } from '@angular/forms';

@Component({
  selector: 'user-profile',
  templateUrl: './user-profile.component.html',
  styleUrls: ['./user-profile.component.css']
})
export class UserProfileComponent {
  userProfile = new FormGroup({
  firstName: new FormControl(''),
  lastName: new FormControl(''),
  address: new FormGroup({
      street: new FormControl(''),
      city: new FormControl(''),
      state: new FormControl(''),
      zip: new FormControl('')
    })
  });

  onSubmit() {
  // Store this.userProfile.value in DB
  }
}
```

2. **FormArray:** Defines a dynamic form in an array format where you can add and remove controls at run time
```typescript
import { Component } from '@angular/core';
import { FormArray, FormControl } from '@angular/forms';

@Component({
  selector: 'order-form',
  templateUrl: './order-form.component.html',
  styleUrls: ['./order-form.component.css']
})
export class OrderFormComponent {
  constructor () {
  this.orderForm = new FormGroup({
    firstName: new FormControl('John', Validators.minLength(3)),
    lastName: new FormControl('Rodson'),
    items: new FormArray([
    new FormControl(null)
    ])
  });
  }

  onAddItem () {
  this.orderForm.controls
  .items.push(new FormControl(null));
  }

  onRemoveItem (index) {
  this.orderForm.controls['items'].removeAt(index);
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 100. How do you update specific properties of a form model?

Use `patchValue()` method to update specific properties:

```typescript
updateProfile() {
  this.userProfile.patchValue({
  firstName: 'John',
  address: {
    street: '98 Crescent Street'
  }
  });
}
```

```html
<button (click)="updateProfile()">Update Profile</button>
```

You can also use `setValue` method to update properties.

**[⬆ Back to Top](#table-of-topics)**

### 101. What is the purpose of FormBuilder?

FormBuilder is used as syntactic sugar for easily creating instances of a FormControl, FormGroup, or FormArray. This reduces the amount of boilerplate needed to build complex reactive forms.

Example:
```typescript
export class UserProfileComponent {
  profileForm = this.formBuilder.group({
  firstName: [''],
  lastName: [''],
  address: this.formBuilder.group({
    street: [''],
    city: [''],
    state: [''],
    zip: ['']
  }),
  });
  constructor(private formBuilder: FormBuilder) { }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 102. How do you verify the model changes in forms?

Add a getter property to return a JSON representation of the model:

```typescript
export class UserProfileComponent {

  model = new User('John', 29, 'Writer');

  get diagnostic() { return JSON.stringify(this.model); }
}
```

Add the diagnostic binding in the template:
```html
{{diagnostic}}
<div class="form-group">
  // FormControls goes here
</div>
```

**[⬆ Back to Top](#table-of-topics)**

### 103. What are the state CSS classes provided by ngModel?

The ngModel directive updates the form control with special Angular CSS classes:

| Form control state | If true | If false |
|---- | --------- | --- |
| Visited | ng-touched | ng-untouched |
| Value has changed | ng-dirty	 | ng-pristine |
| Value is valid| 	ng-valid | ng-invalid |

**[⬆ Back to Top](#table-of-topics)**

### 104. How do you reset the form?

Call the `reset()` function on your form model:

```typescript
onSubmit() {
  if (this.myform.valid) {
  console.log("Form is submitted");
  // Perform business logic here
  this.myform.reset();
  }
}
```

Your form model resets the form back to its original pristine state.

**[⬆ Back to Top](#table-of-topics)**

### 105. What are the types of validator functions?

Two types of validators:

1. **Sync validators:** Synchronous functions that immediately return either a set of validation errors or null
   ```typescript
   this.myForm = formBuilder.group({
     firstName: ['value'],
     lastName: ['value', Validators.required],
   });
   ```

2. **Async validators:** Asynchronous functions that return a Promise or Observable
   ```typescript
   email: ['value', *Some validation function*, *Some asynchronous validation function*]
   ```

**[⬆ Back to Top](#table-of-topics)**

### 106. Can you give an example of built-in validators?

Built-in validators like `required` and `minlength` can be used:

Example in reactive forms:
```typescript
this.registrationForm = new FormGroup({
  'name': new FormControl(this.hero.name, [
    Validators.required,
    Validators.minLength(4),
  ])
  });
```

Example in template-driven forms:
```html
<input type="text" required minlength="4">
```

**[⬆ Back to Top](#table-of-topics)**

### 107. How do you optimize the performance of async validators?

Delay the form validity by changing the updateOn property from change (default) to submit or blur:

1. **Template-driven forms:** Set the property on `ngModelOptions` directive
```html
<input [(ngModel)]="name" [ngModelOptions]="{updateOn: 'blur'}">
```

2. **Reactive-forms:** Set the property on FormControl instance
```typescript
name = new FormControl('', {updateOn: 'blur'});
```

**[⬆ Back to Top](#table-of-topics)**

### 108. Is it possible to do aliasing for inputs and outputs?

Yes, it is possible in two ways:

1. **Aliasing in metadata:**
```typescript
inputs: ['input1: buyItem'],
outputs: ['outputEvent1: completedEvent']
```

2. **Aliasing with @Input()/@Output() decorator:**
```typescript
@Input('buyItem') input1: string;
@Output('completedEvent') outputEvent1 = new EventEmitter<string>();
```

**[⬆ Back to Top](#table-of-topics)**

---

## Services & HTTP

### 109. What is HttpClient and its benefits?

Most front-end applications communicate with backend services over HTTP protocol. Angular provides a simplified client HTTP API known as **HttpClient** based on top of XMLHttpRequest interface.

Import in your root module:
```typescript
import { HttpClientModule } from '@angular/common/http';
```

Major advantages:
1. Contains testability features
2. Provides typed request and response objects
3. Intercept request and response
4. Supports Observable APIs
5. Supports streamlined error handling

**[⬆ Back to Top](#table-of-topics)**

### 110. Explain on how to use HttpClient with an example?

Steps:

1. **Import HttpClient into root module:**
```typescript
import { HttpClientModule } from '@angular/common/http';
@NgModule({
  imports: [
  BrowserModule,
  HttpClientModule,
  ],
})
export class AppModule {}
```

2. **Inject the HttpClient into the application:**
```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';

const userProfileUrl: string = 'assets/data/profile.json';

@Injectable()
export class UserProfileService {
  constructor(private http: HttpClient) { }

  getUserProfile() {
  return this.http.get(this.userProfileUrl);
  }
}
```

3. **Create a component for subscribing to the service:**
```typescript
fetchUserProfile() {
  this.userProfileService.getUserProfile()
  .subscribe((data: User) => this.user = {
  id: data['userId'],
  name: data['firstName'],
  city:  data['city']
  });
}
```

**[⬆ Back to Top](#table-of-topics)**

### 111. How can you read full response?

Use the observe option from HttpClient to get full response:

```typescript
getUserResponse(): Observable<HttpResponse<User>> {
  return this.http.get<User>(
  this.userUrl, { observe: 'response' });
}
```

Now HttpClient.get() returns an Observable of typed HttpResponse rather than just the JSON data.

**[⬆ Back to Top](#table-of-topics)**

### 112. How do you perform Error handling?

Pass an error object as a second callback to subscribe():

```typescript
fetchUser() {
  this.userService.getProfile()
  .subscribe(
  (data: User) => this.userProfile = { ...data }, // success path
  error => this.error = error // error path
  );
}
```

It's a good idea to give the user meaningful feedback instead of displaying the raw error object.

**[⬆ Back to Top](#table-of-topics)**

### 113. How do you pass headers for HTTP client?

Two ways:

1. **Pass object map directly:**
```typescript
this._http.get('someUrl',{
   headers: {'header1':'value1','header2':'value2'}
});
```

2. **Create HttpHeaders class:**
```typescript
let headers = new HttpHeaders().set('header1', headerValue1);
headers = headers.append('header2', headerValue2);
headers = headers.append('header3', headerValue3);

let params = new HttpParams().set('param1', value1);
params = params.append('param2', value2);
params = params.append('param3', value3);

return this._http.get<any[]>('someUrl', { headers: headers, params: params })
```

**[⬆ Back to Top](#table-of-topics)**

### 114. What is the reason for No provider for HTTP exception?

This exception is due to missing HttpClientModule in your module. Import it:

```typescript
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  imports: [
  BrowserModule,
  HttpClientModule,
  ],
  declarations: [ AppComponent ],
  bootstrap:    [ AppComponent ]
})
export class AppModule { }
```

**[⬆ Back to Top](#table-of-topics)**

### 115. What are Http Interceptors?

Http Interceptors are part of @angular/common/http that inspect and transform HTTP requests from your application to the server and vice-versa on HTTP responses.

Syntax:
```typescript
interface HttpInterceptor {
  intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>>
}
```

Implementation:
```typescript
@Injectable()
export class MyInterceptor implements HttpInterceptor {
  constructor() {}
  intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
    ...
  }
}
```

Usage in module:
```typescript
@NgModule({
  ...
  providers: [
    {
      provide: HTTP_INTERCEPTORS,
      useClass: MyInterceptor,
      multi: true
    }
  ]
  ...
})
export class AppModule {}
```

**[⬆ Back to Top](#table-of-topics)**

### 116. What are the applications of HTTP interceptors?

HTTP Interceptors can be used for:

1. Authentication
2. Logging
3. Caching
4. Fake backend
5. URL transformation
6. Modifying headers

**[⬆ Back to Top](#table-of-topics)**

### 117. Is multiple interceptors supported in Angular?

Yes, Angular supports multiple interceptors. Define them in providers:

```typescript
providers: [
  { provide: HTTP_INTERCEPTORS, useClass: MyFirstInterceptor, multi: true },
  { provide: HTTP_INTERCEPTORS, useClass: MySecondInterceptor, multi: true }
],
```

Interceptors are called in the order they were provided.

**[⬆ Back to Top](#table-of-topics)**

### 118. How can I use interceptor for an entire application?

Import HttpClientModule only in AppModule and add the interceptors to the root application injector:

```typescript
@Injectable()
export class MyInterceptor implements HttpInterceptor {
  intercept(
  req: HttpRequest<any>,
  next: HttpHandler
  ): Observable<HttpEvent<any>> {

  return next.handle(req).do(event => {
    if (event instanceof HttpResponse) {
       // Code goes here
    }
  });

  }
}
```

Import HttpClientModule in AppModule:
```typescript
@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, HttpClientModule],
  providers: [
  { provide: HTTP_INTERCEPTORS, useClass: MyInterceptor, multi: true }
  ],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

**[⬆ Back to Top](#table-of-topics)**

---

## RxJS & Observables

### 119. What is RxJS?

RxJS is a library for composing asynchronous and callback-based code in a functional, reactive style using Observables. Many APIs such as HttpClient produce and consume RxJS Observables and use operators for processing observables.

Import:
```typescript
import { Observable, throwError } from 'rxjs';
import { catchError, retry } from 'rxjs/operators';
```

**[⬆ Back to Top](#table-of-topics)**

### 120. What are observables?

Observables are declarative which provide support for passing messages between publishers and subscribers in your application.

They are mainly used for:
- Event handling
- Asynchronous programming
- Handling multiple values

Example:
```typescript
import { Observable } from 'rxjs';

const observable = new Observable(observer => {
  setTimeout(() => {
  observer.next('Hello from a Observable!');
  }, 2000);
});
```

**[⬆ Back to Top](#table-of-topics)**

### 121. What is subscribing?

An Observable instance begins publishing values only when someone subscribes to it. You subscribe by calling the **subscribe()** method of the instance, passing an observer object.

Example:
```typescript
const source = range(1, 5);

const myObserver = {
  next: x => console.log('Observer got a next value: ' + x),
  error: err => console.error('Observer got an error: ' + err),
  complete: () => console.log('Observer got a complete notification'),
};

source.subscribe(myObserver);
// => Observer got a next value: 1
// => Observer got a next value: 2
// => Observer got a next value: 3
// => Observer got a next value: 4
// => Observer got a next value: 5
// => Observer got a complete notification
```

**[⬆ Back to Top](#table-of-topics)**

### 122. What is an observable?

An Observable is a unique Object similar to a Promise that can help manage async code. Observables are not part of the JavaScript language so we need to rely on a popular Observable library called RxJS.

Created using new keyword:

```typescript
import { Observable } from 'rxjs';

const observable = new Observable(observer => {
  setTimeout(() => {
  observer.next('Hello from a Observable!');
  }, 2000);
});
```

**[⬆ Back to Top](#table-of-topics)**

### 123. What is an observer?

Observer is an interface for a consumer of push-based notifications delivered by an Observable.

Structure:
```typescript
interface Observer<T> {
  closed?: boolean;
  next: (value: T) => void;
  error: (err: any) => void;
  complete: () => void;
}
```

Handler passed as parameter:
```typescript
myObservable.subscribe(myObserver);
```

**Note:** If you don't supply a handler for a notification type, the observer ignores notifications of that type.

**[⬆ Back to Top](#table-of-topics)**

### 124. What is the difference between promise and observable?

| Observable | Promise |
|---- | --------- |
| Declarative: Computation does not start until subscription | Execute immediately on creation|
| Provide multiple values over time | Provide only one |
| Subscribe method is used for error handling | Push errors to the child promises |
| Provides chaining and subscription to handle complex applications | Uses only .then() clause |

**[⬆ Back to Top](#table-of-topics)**

### 125. What is multicasting?

Multi-casting is the practice of broadcasting to a list of multiple subscribers in a single execution.

Example:
```typescript
var source = Rx.Observable.from([1, 2, 3]);
var subject = new Rx.Subject();
var multicasted = source.multicast(subject);

// These are, under the hood, `subject.subscribe({...})`:
multicasted.subscribe({
  next: (v) => console.log('observerA: ' + v)
});
multicasted.subscribe({
  next: (v) => console.log('observerB: ' + v)
});

// This is, under the hood, `subject.subscribe(...)`
```

**[⬆ Back to Top](#table-of-topics)**

### 126. How do you perform error handling in observables?

Specify an **error callback** on the observer:

```typescript
myObservable.subscribe({
  next(num) { console.log('Next num: ' + num)},
  error(err) { console.log('Received an errror: ' + err)}
});
```

**[⬆ Back to Top](#table-of-topics)**

### 127. What is the short hand notation for subscribe method?

The subscribe() method can accept callback function definitions in line as positional arguments:

```typescript
myObservable.subscribe(
  x => console.log('Observer got a next value: ' + x),
  err => console.error('Observer got an error: ' + err),
  () => console.log('Observer got a complete notification')
);
```

**[⬆ Back to Top](#table-of-topics)**

### 128. What are the utility functions provided by RxJS?

RxJS library provides utility functions for:

1. Converting existing code for async operations into observables
2. Iterating through the values in a stream
3. Mapping values to different types
4. Filtering streams
5. Composing multiple streams

**[⬆ Back to Top](#table-of-topics)**

### 129. What are observable creation functions?

RxJS provides creation functions for creating observables from promises, events, timers and Ajax requests.

1. **Create from promise:**
```typescript
import { from } from 'rxjs';
const data = from(fetch('/api/endpoint'));
data.subscribe({
 next(response) { console.log(response); },
 error(err) { console.error('Error: ' + err); },
 complete() { console.log('Completed'); }
});
```

2. **Create from AJAX request:**
```typescript
import { ajax } from 'rxjs/ajax';
const apiData = ajax('/api/data');
apiData.subscribe(res => console.log(res.status, res.response));
```

3. **Create from counter:**
```typescript
import { interval } from 'rxjs';
const secondsCounter = interval(1000);
secondsCounter.subscribe(n =>
  console.log(`Counter value: ${n}`));
```

4. **Create from event:**
```typescript
import { fromEvent } from 'rxjs';
const el = document.getElementById('custom-element');
const mouseMoves = fromEvent(el, 'mousemove');
const subscription = mouseMoves.subscribe((e: MouseEvent) => {
  console.log(`Coordinates of mouse pointer: ${e.clientX} * ${e.clientY}`);
  });
```

**[⬆ Back to Top](#table-of-topics)**

### 130. What will happen if you do not supply handler for observer?

If you don't supply a handler for a notification type, the observer just ignores notifications of that type.

**[⬆ Back to Top](#table-of-topics)**

### 131. What is an rxjs Subject?

An RxJS Subject is a special type of Observable that allows values to be multicasted to many Observers. While plain Observables are unicast, Subjects are multicast.

A Subject is like an Observable, but can multicast to many Observers. Subjects are like EventEmitters:

```typescript
import { Subject } from 'rxjs';

const subject = new Subject<number>();

subject.subscribe({
  next: (v) => console.log(`observerA: ${v}`)
});
subject.subscribe({
  next: (v) => console.log(`observerB: ${v}`)
});

subject.next(1);
subject.next(2);
```

**[⬆ Back to Top](#table-of-topics)**

---

## Change Detection

### 132. What are the possible data update scenarios for change detection?

The change detection works in the following scenarios:

1. **Component initialization:** Angular triggers `ApplicationRef.tick()` to call change detection and View Rendering
2. **Event listener:** DOM event listener can update the data and trigger change detection
   ```typescript
   @Component({
   template: `<button (click)="onClick()">Click</button>{{message}}`
   })
   export class EventListenerComponent {
   message = '';
   onClick() {
     this.message = 'data updated';
   }
   }
   ```

3. **HTTP Data Request:** Get data from a server through an HTTP request
   ```typescript
   ngOnInit() {
   this.httpClient.get(this.serverUrl).subscribe(response => {
     this.data = response.data;
   });
   }
   ```

4. **Macro tasks setTimeout() or setInterval():** Update the data in the callback function
   ```typescript
   ngOnInit() {
   setTimeout(() => {
     this.data = 'data updated';
   });
   }
   ```

5. **Micro tasks Promises:** Update the data in the callback function of promise
   ```typescript
   ngOnInit() {
   Promise.resolve(1).then(v => {
     this.data = v;
   });
   }
   ```

6. **Async operations:** WebSocket.onmessage() and Canvas.toBlob()

**[⬆ Back to Top](#table-of-topics)**

### 133. What is a zone context?

Execution Context is an abstract concept that holds information about the environment within the current code being executed. A zone provides an execution context that persists across asynchronous operations.

Example:
```typescript
zone.run(() => {
  // outside zone
  expect(zoneThis).toBe(zone);
  setTimeout(function() {
  // the same outside zone exist here
  expect(zoneThis).toBe(zone);
  });
});
```

The current zone is retrieved through `Zone.current`.

**[⬆ Back to Top](#table-of-topics)**

### 134. What is NgZone?

Angular provides a service called NgZone which creates a zone named `angular` to automatically trigger change detection when:
1. When a sync or async function is executed
2. When there is no microTask scheduled

**[⬆ Back to Top](#table-of-topics)**

### 135. What is NoopZone?

Zone is loaded by default in Angular applications. You can also use Angular without Zone but the change detection need to be implemented on your own.

Steps to remove zone.js:

1. Remove the zone.js import from polyfills.ts:
```typescript
// import 'zone.js/dist/zone';
```

2. Bootstrap Angular with noop zone in src/main.ts:
```typescript
platformBrowserDynamic().bootstrapModule(AppModule, {ngZone: 'noop'})
  .catch(err => console.error(err));
```

**[⬆ Back to Top](#table-of-topics)**

### 136. What are the lifecycle hooks of a zone?

Four lifecycle hooks for asynchronous operations from zone.js:

1. **onScheduleTask:** Triggers when a new asynchronous task is scheduled (e.g., setTimeout())
```typescript
onScheduleTask: function(delegate, curr, target, task) {
  console.log('new task is scheduled:', task.type, task.source);
  return delegate.scheduleTask(target, task);
  }
```

2. **onInvokeTask:** Triggers when an asynchronous task is about to execute
```typescript
onInvokeTask: function(delegate, curr, target, task, applyThis, applyArgs) {
  console.log('task will be invoked:', task.type, task.source);
  return delegate.invokeTask(target, task, applyThis, applyArgs);
  }
```

3. **onHasTask:** Triggers when the status of one kind of task changes
```typescript
onHasTask: function(delegate, curr, target, hasTaskState) {
  console.log('task state changed in the zone:', hasTaskState);
  return delegate.hasTask(target, hasTaskState);
  }
```

4. **onInvoke:** Triggers when a synchronous function is going to execute
```typescript
onInvoke: function(delegate, curr, target, callback, applyThis, applyArgs) {
  console.log('the callback will be invoked:', callback);
  return delegate.invoke(target, callback, applyThis, applyArgs);
  }
```

**[⬆ Back to Top](#table-of-topics)**

### 137. What are the methods of NgZone used to control change detection?

NgZone provides methods to control change detection:

1. **run():** Execute a function inside the angular zone to trigger change detection
```typescript
export class AppComponent implements OnInit {
  constructor(private ngZone: NgZone) {}
  ngOnInit() {
  this.ngZone.run(() => {
    someNewAsyncAPI(() => {
    // update the data of the component
    });
  });
  }
}
```

2. **runOutsideAngular():** Execute without triggering change detection
```typescript
export class AppComponent implements OnInit {
  constructor(private ngZone: NgZone) {}
  ngOnInit() {
  this.ngZone.runOutsideAngular(() => {
    setTimeout(() => {
    // update component data and don't trigger change detection
    });
  });
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 138. How do you change the settings of zonejs?

Configure zone settings in a separate file and import it after zonejs import.

Example zone-flags.js:
```typescript
// disable patching requestAnimationFrame
(window as any).__Zone_disable_requestAnimationFrame = true;

// disable patching specified eventNames
(window as any).__zone_symbol__UNPATCHED_EVENTS = ['scroll', 'mousemove'];
```

Import in polyfill.ts:
```typescript
import `./zone-flags`;
import 'zone.js/dist/zone';
```

**[⬆ Back to Top](#table-of-topics)**

### 139. What is zone?

A Zone is an execution context that persists across async tasks. Angular relies on zone.js to run Angular's change detection processes when native JavaScript operations raise events.

**[⬆ Back to Top](#table-of-topics)**

---

## Compilation & Build

### 140. What are different types of compilation in Angular?

Angular offers two ways to compile your application:

1. **Just-in-Time (JIT)**
2. **Ahead-of-Time (AOT)**

**[⬆ Back to Top](#table-of-topics)**

### 141. What is JIT?

Just-in-Time (JIT) is a type of compilation that compiles your app in the browser at runtime. JIT compilation is the default when you run the ng build (build only) or ng serve (build and serve locally) CLI commands.

Commands for JIT compilation:
```
ng build
ng serve
```

**[⬆ Back to Top](#table-of-concepts)**

### 142. What is AOT?

Ahead-of-Time (AOT) is a type of compilation that compiles your app at build time. Include the `--aot` option:

```
ng build --aot
ng serve --aot
```

**Note:** The `ng build --prod` command compiles with AOT by default.

**[⬆ Back to Top](#table-of-topics)**

### 143. Why do we need compilation process?

Angular components and templates cannot be understood by the browser directly. Angular applications require a compilation process before they can run in a browser. In AOT compilation, both Angular HTML and TypeScript code are converted into efficient JavaScript code during the build phase.

**[⬆ Back to Top](#table-of-topics)**

### 144. What are the advantages with AOT?

Benefits of AOT:

1. **Faster rendering:** Browser downloads a pre-compiled version of the application and can render immediately
2. **Fewer asynchronous requests:** Inlines external HTML templates and CSS within the application javascript
3. **Smaller Angular framework download size:** Doesn't require downloading the Angular compiler
4. **Detect template errors earlier:** Detects and reports template binding errors during the build step
5. **Better security:** Compiles HTML templates and components into JavaScript (no injection attacks)

**[⬆ Back to Top](#table-of-topics)**

### 145. What are the ways to control AOT compilation?

Two ways to control compilation:

1. By providing template compiler options in the `tsconfig.json` file
2. By configuring Angular metadata with decorators

**[⬆ Back to Top](#table-of-topics)**

### 146. What are the restrictions of metadata?

In Angular, metadata must be written with the following constraints:

1. Write expression syntax within the supported range of javascript features
2. The compiler can only reference symbols which are exported
3. Only call the functions supported by the compiler
4. Decorated and data-bound class members must be public

**[⬆ Back to Top](#table-of-topics)**

### 147. What are the three phases of AOT?

The AOT compiler works in three phases:

1. **Code Analysis:** The compiler records a representation of the source
2. **Code generation:** It handles the interpretation and places restrictions on what it interprets
3. **Validation:** The Angular template compiler uses the TypeScript compiler to validate the binding expressions in templates

**[⬆ Back to Top](#table-of-topics)**

### 148. Can I use arrow functions in AOT?

No, arrow functions can't be used to assign values to the decorator properties. This is invalid:

```typescript
@Component({
  providers: [{
  provide: MyService, useFactory: () => getService()
  }]
})
```

Fix it with an exported function:

```typescript
function getService(){
  return new MyService();
}

@Component({
  providers: [{
  provide: MyService, useFactory: getService
  }]
})
```

**Note:** From Angular5 onwards, the compiler automatically performs this rewriting.

**[⬆ Back to Top](#table-of-topics)**

### 149. What is the purpose of metadata json files?

The metadata.json file can be treated as a diagram of the overall structure of a decorator's metadata, represented as an abstract syntax tree(AST). During the analysis phase, the AOT collector scans the metadata recorded in Angular decorators and outputs metadata information in .metadata.json files.

**[⬆ Back to Top](#table-of-topics)**

### 150. Can I use any javascript feature for expression syntax in AOT?

No, the AOT collector understands only a limited subset of JavaScript features. If an expression uses unsupported syntax, the collector writes an error node to the .metadata.json file.

**[⬆ Back to Top](#table-of-topics)**

### 151. What is folding?

Folding is a process in which the collector evaluates an expression during collection and records the result in the .metadata.json instead of the original expression. The compiler can only resolve references to exported symbols in the metadata.

Example - not exported:
```typescript
let selector = 'app-root';
@Component({
  selector: selector
})
```

Will be folded into inline selector:
```typescript
@Component({
    selector: 'app-root'
  })
```

**[⬆ Back to Top](#table-of-topics)**

### 152. What are macros?

The AOT compiler supports macros in the form of functions or static methods that return an expression in a single return expression.

Example macro function:
```typescript
export function wrapInArray<T>(value: T): T[] {
  return [value];
}
```

Usage in metadata:
```typescript
@NgModule({
  declarations: wrapInArray(TypicalComponent)
})
export class TypicalModule {}
```

The compiler treats the macro expression as written directly:
```typescript
@NgModule({
  declarations: [TypicalComponent]
})
export class TypicalModule {}
```

**[⬆ Back to Top](#table-of-topics)**

### 153. What is metadata rewriting?

Metadata rewriting is the process in which the compiler converts the expression initializing the fields such as useClass, useValue, useFactory, and data into an exported variable, which replaces the expression. The compiler does this rewriting during the emit of the .js file but not in definition files(.d.ts file).

**[⬆ Back to Top](#table-of-topics)**

### 154. How do you provide configuration inheritance?

Angular Compiler supports configuration inheritance through extends in the tsconfig.json on angularCompilerOptions:

```typescript
{
  "extends": "../tsconfig.base.json",
  "compilerOptions": {
  "experimentalDecorators": true,
  ...
  },
  "angularCompilerOptions": {
  "fullTemplateTypeCheck": true,
  "preserveWhitespaces": true,
  ...
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 155. How do you specify angular template compiler options?

The angular template compiler options are specified as members of the **angularCompilerOptions** object in the tsconfig.json file:

```typescript
{
  "compilerOptions": {
  "experimentalDecorators": true,
      ...
  },
  "angularCompilerOptions": {
  "fullTemplateTypeCheck": true,
  "preserveWhitespaces": true,
      ...
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 156. How do you enable binding expression validation?

Add the compiler option **fullTemplateTypeCheck** in the "angularCompilerOptions" of the project's tsconfig.json:

Example:
```typescript
@Component({
  selector: 'my-component',
  template: '{{user.contacts.email}}'
})
class MyComponent {
  user?: User;
}
```

This will produce error:
```
my.component.ts.MyComponent.html(1,1): Property 'contacts' does not exist on type 'User'. Did you mean 'contact'?
```

**[⬆ Back to Top](#table-of-topics)**

### 157. What is the purpose of any type cast function?

You can disable binding expression type checking using $any() type cast function by surrounding the expression:

```html
{{ $any(user).contacts.email }}
```

The $any() cast function also works with this:
```html
{{ $any(this).contacts.email }}
```

**[⬆ Back to Top](#table-of-topics)**

### 158. What is Non null type assertion operator?

You can use the non-null type assertion operator to suppress the "Object is possibly 'undefined'" error:

```typescript
@Component({
  selector: 'my-component',
  template: '<span *ngIf="user"> {{user.name}} contacted through {{contact!.email}} </span>'
})
class MyComponent {
  user?: User;
  contact?: Contact;

  setData(user: User, contact: Contact) {
  this.user = user;
  this.contact = contact;
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 159. What is type narrowing?

The expression used in an ngIf directive is used to narrow type unions in the Angular template compiler similar to if expression in typescript:

```typescript
@Component({
  selector: 'my-component',
  template: '<span *ngIf="user"> {{user.contact.email}} </span>'
})
class MyComponent {
  user?: User;
}
```

**[⬆ Back to Top](#table-of-topics)**

### 160. What is Angular compiler?

The Angular compiler is used to convert the application code into JavaScript code. It reads the template markup, combines it with the corresponding component class code, and emits component factories.

**[⬆ Back to Top](#table-of-topics)**

### 161. What is the role of ngModule metadata in compilation process?

The `@NgModule` metadata is used to tell the Angular compiler what components to be compiled for this module and how to link this module with other modules.

**[⬆ Back to Top](#table-of-topics)**

### 162. How does angular finds components, directives and pipes?

The Angular compiler finds:
- A component or directive when it can match the selector in that template
- A pipe if the pipe's name appears within the pipe syntax of the template HTML

**[⬆ Back to Top](#table-of-topics)**

### 163. Give few examples for NgModules?

Angular core libraries and third-party libraries are available as NgModules:

1. Angular libraries: FormsModule, HttpClientModule, RouterModule
2. Third-party libraries: Material Design, Ionic, AngularFire2

**[⬆ Back to Top](#table-of-topics)**

### 164. What is an entry component?

An entry component is any component that Angular loads imperatively (not referencing it in the template) by type. These components can't be found by the Angular compiler during compilation and are created dynamically with `ComponentFactoryResolver`.

Two main kinds:
1. The bootstrapped root component
2. A component you specify in a route

**[⬆ Back to Top](#table-of-topics)**

### 165. What is a bootstrapped component?

A bootstrapped component is an entry component that Angular loads into the DOM during the bootstrap process. Generally, this bootstrapped or root component is named `AppComponent`:

```typescript
@NgModule({
  declarations: [
  AppComponent
  ],
  imports: [
  BrowserModule,
  FormsModule,
  HttpClientModule,
  AppRoutingModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
```

**[⬆ Back to Top](#table-of-topics)**

### 166. How do you manually bootstrap an application?

Use `ngDoBootstrap` hook for manual bootstrapping instead of using bootstrap array:

```typescript
interface DoBootstrap {
  ngDoBootstrap(appRef: ApplicationRef): void
}
```

Implementation:
```typescript
class AppModule implements DoBootstrap {
  ngDoBootstrap(appRef: ApplicationRef) {
  appRef.bootstrap(AppComponent);
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 167. Is it necessary for bootstrapped component to be entry component?

Yes, the bootstrapped component needs to be an entry component because the bootstrapping process is an imperative process.

**[⬆ Back to Top](#table-of-topics)**

### 168. What is a routed entry component?

The components referenced in router configuration are called routed entry components. This routed entry component is defined in a route definition:

```typescript
const routes: Routes = [
  {
  path: '',
  component: TodoListComponent // router entry component
  }
];
```

The compilers are smart enough to recognize a router definition and automatically add the router component into `entryComponents`.

**[⬆ Back to Top](#table-of-topics)**

### 169. Why is not necessary to use entryComponents array every time?

Most of the time, Angular adds components from both @NgModule.bootstrap and route definitions to entry components automatically.

**[⬆ Back to Top](#table-of-topics)**

### 170. Do I still need to use entryComponents array in Angular9?

No. In previous angular releases, the entryComponents array is used to tell the compiler which components would be created and inserted dynamically. In Angular9 with Ivy, this is not required anymore.

**[⬆ Back to Top](#table-of-topics)**

### 171. Is it all components generated in production build?

No, only the entry components and template components appear in production builds. If a component isn't an entry component and isn't found in a template, the tree shaker will throw it away.

**[⬆ Back to Top](#table-of-topics)**

### 172. What is the purpose of differential loading in CLI?

From Angular8 release onwards, applications are built using differential loading strategy to build two separate bundles:

1. **First build:** ES2015 syntax for modern browsers, less polyfills, smaller bundle size
2. **Second build:** Old ES5 syntax for older browsers with all polyfills, larger bundle size

This strategy supports multiple browsers but only loads the code that the browser needs.

**[⬆ Back to Top](#table-of-topics)**

### 173. What is Angular Universal?

Angular Universal is a server-side rendering module for Angular applications in various scenarios. It's a community driven project available under @angular/platform-server package. Recently Angular Universal has been integrated with Angular CLI.

**[⬆ Back to Top](#table-of-topics)**

---

## Security

### 174. What are the security principles in angular?

Below are the list of security principles in angular:

1. You should avoid direct use of the DOM APIs
2. You should enable Content Security Policy (CSP) and configure your web server
3. You should Use the offline template compiler
4. You should Use Server Side XSS protection
5. You should Use DOM Sanitizer
6. You should Preventing CSRF or XSRF attacks

**[⬆ Back to Top](#table-of-topics)**

### 175. What are the best practices for security in angular?

Below are the best practices of security in angular:

1. Use the latest Angular library releases
2. Don't modify your copy of Angular
3. Avoid Angular APIs marked in the documentation as "Security Risk"

**[⬆ Back to Top](#table-of-topics)**

### 176. What is Angular security model for preventing XSS attacks?

Angular treats all values as untrusted by default. Angular sanitizes and escapes untrusted values when a value is inserted into the DOM from a template, via property, attribute, style, class binding, or interpolation.

**[⬆ Back to Top](#table-of-topics)**

### 177. What is the role of template compiler for prevention of XSS attacks?

The offline template compiler prevents vulnerabilities caused by template injection and greatly improves application performance. It's recommended to use offline template compiler in production deployments without dynamically generating any template.

**[⬆ Back to Top](#table-of-topics)**

### 178. What are the various security contexts in Angular?

Angular defines the following security contexts for sanitization:

1. **HTML:** When interpreting a value as HTML such as binding to innerHtml
2. **Style:** When binding CSS into the style property
3. **URL:** For URL properties such as `<a href>`
4. **Resource URL:** A URL that will be loaded and executed as code such as `<script src>`

**[⬆ Back to Top](#table-of-topics)**

### 179. What is Sanitization? Is angular supports it?

**Sanitization** is the inspection of an untrusted value, turning it into a value that's safe to insert into the DOM. Yes, Angular supports sanitization. It sanitizes untrusted values for HTML, styles, and URLs but sanitizing resource URLs isn't possible because they contain arbitrary code.

**[⬆ Back to Top](#table-of-topics)**

### 180. What is the purpose of innerHTML?

The innerHtml is a property of HTML-Elements, which allows you to set its html-content programmatically.

Example:
```html
<div [innerHTML]="htmlSnippet"></div>
```

Component:
```typescript
export class myComponent {
  htmlSnippet: string = '<b>Hello World</b>, Angular';
}
```

**Note:** This property could cause Cross Site Scripting (XSS) security bugs when improperly handled.

**[⬆ Back to Top](#table-of-topics)**

### 181. What is the difference between interpolated content and innerHTML?

- **Interpolated content** is always escaped (HTML isn't interpreted, browser displays angle brackets in text content)
- **innerHTML binding** is interpreted (browser converts < and > characters as HTMLEntities)

Example:
```html
<p>Interpolated value:</p>
<div >{{htmlSnippet}}</div>
<p>Binding of innerHTML:</p>
<div [innerHTML]="htmlSnippet"></div>
```

Component:
```typescript
export class InnerHtmlBindingComponent {
  htmlSnippet = 'Template <script>alert("XSS Attack")</script> <b>Code attached</b>';
}
```

Angular automatically sanitizes the innerHTML binding, removing the script tag.

**[⬆ Back to Top](#table-of-topics)**

### 182. How do you prevent automatic sanitization?

Sometimes applications need to include executable code. Prevent automatic sanitization by injecting DomSanitizer and calling the appropriate bypass methods:

1. **Inject DomSanitizer:**
```typescript
constructor(private sanitizer: DomSanitizer) {}
```

2. **Mark the trusted value using bypass methods:**
- bypassSecurityTrustHtml
- bypassSecurityTrustScript
- bypassSecurityTrustStyle
- bypassSecurityTrustUrl
- bypassSecurityTrustResourceUrl

Example:
```typescript
constructor(private sanitizer: DomSanitizer) {
  this.dangerousUrl = 'javascript:alert("XSS attack")';
  this.trustedUrl = sanitizer.bypassSecurityTrustUrl(this.dangerousUrl);
}
```

**[⬆ Back to Top](#table-of-topics)**

### 183. Is safe to use direct DOM API methods in terms of security?

No, the built-in browser DOM APIs or methods don't automatically protect you from security vulnerabilities. It is recommended to use Angular templates instead of directly interacting with DOM. If it is unavoidable then use the built-in Angular sanitization functions.

**[⬆ Back to Top](#table-of-topics)**

### 184. What is DOM sanitizer?

`DomSanitizer` is used to help preventing Cross Site Scripting Security bugs (XSS) by sanitizing values to be safe to use in the different DOM contexts.

**[⬆ Back to Top](#table-of-topics)**

### 185. How do you support server side XSS protection in Angular application?

Server-side XSS protection is supported by using a templating language that automatically escapes values. Don't use a templating language to generate Angular templates on the server side as it creates a high risk of introducing template-injection vulnerabilities.

**[⬆ Back to Top](#table-of-topics)**

### 186. Is angular prevents http level vulnerabilities?

Yes, Angular has built-in support for preventing HTTP level vulnerabilities such as:
- Cross-site request forgery (CSRF or XSRF)
- Cross-site script inclusion (XSSI)

Even though these vulnerabilities need to be mitigated on server-side:
1. HttpClient supports a token mechanism used to prevent XSRF attacks
2. HttpClient library recognizes the convention of prefixed JSON responses and automatically strips the string ")]}',\n" from all responses before further parsing

**[⬆ Back to Top](#table-of-topics)**

---

## Testing

### 187. How do you test Angular application using CLI?

Angular CLI provides support for testing using Jasmine Test framework:

Run tests:
```bash
ng test
```

By default this command:
- Builds the app in watch mode
- Launches the Karma test runner

Output:
```
10% building modules 1/1 modules 0 active
...INFO [karma]: Karma v1.7.1 server started at http://0.0.0.0:9876/
...INFO [launcher]: Launching browser Chrome ...
...INFO [launcher]: Starting browser Chrome
...INFO [Chrome ...]: Connected on socket ...
Chrome ...: Executed 3 of 3 SUCCESS (0.135 secs / 0.205 secs)
```

A chrome browser also opens and displays the test output in the "Jasmine HTML Reporter".

**[⬆ Back to Top](#table-of-topics)**

### 188. What is TestBed?

TestBed is an API for writing unit tests for Angular applications and libraries. Even though tests are written in Jasmine and run using Karma, this API provides an easier way to:
- Create components
- Handle injection
- Test asynchronous behaviour
- Interact with the application

**[⬆ Back to Top](#table-of-topics)**

### 189. What is protractor?

Protractor is an end-to-end test framework for Angular and AngularJS applications. It runs tests against your application running in a real browser, interacting with it as a user would.

Installation:
```
npm install -g protractor
```

**[⬆ Back to Top](#table-of-topics)**

### 190. What is Component Test Harnesses?

A component harness is a testing API around an Angular directive or component to make tests simpler by hiding implementation details. This can be shared between unit tests, integration tests, and end-to-end tests.

The idea comes from the **PageObject** pattern commonly used for integration testing.

**[⬆ Back to Top](#table-of-topics)**

---

## Performance & Optimization

### 191. How to use polyfills in Angular application?

The Angular CLI provides support for polyfills officially. When you create a new project, a `src/polyfills.ts` configuration file is created.

**Mandatory polyfills:** Installed automatically and import statements enabled in 'src/polyfills.ts'

**Optional polyfills:** Install the npm package and create import statement in 'src/polyfills.ts'

Example for web animations (optional):
```bash
npm install --save web-animations-js
```

Add import statement:
```typescript
import 'web-animations-js';
```

**[⬆ Back to Top](#table-of-topics)**

### 192. What are the ways to trigger change detection in Angular?

Three possible ways:

1. **ApplicationRef.tick():** Explicitly process change detection and its side-effects. Checks the full component tree.
2. **NgZone.run(callback):** Evaluate the callback function inside the Angular zone.
3. **ChangeDetectorRef.detectChanges():** Detects only the components and its children.

**[⬆ Back to Top](#table-of-topics)**

### 193. How do you upgrade angular version?

Use Angular CLI `ng update` command:

Example (upgrade from Angular 7 to 8):
```bash
ng update @angular/cli @angular/core
```

Lazy loaded route imports are migrated to the new import syntax automatically.

**[⬆ Back to Top](#table-of-topics)**

### 194. How can I use SASS in angular project?

When creating your project with angular cli:

```
ng new My_New_Project --style=sass
```

If changing existing style:
```
ng set defaults.styleExt scss
```

**[⬆ Back to Top](#table-of-topics)**

### 195. What is the benefit of Automatic Inlining of Fonts?

During compile time, Angular CLI downloads and inlines the fonts that your application is using. This performance update speeds up the first contentful paint (FCP). This feature is enabled by default in apps built with version 11.

**[⬆ Back to Top](#table-of-topics)**

### 196. What is codelyzer?

Codelyzer provides set of tslint rules for static code analysis of Angular TypeScript projects. You can run the static code analyzer over web apps, NativeScript, Ionic etc.

Angular CLI has support:
```bash
ng new codelyzer
ng lint
```

**[⬆ Back to Top](#table-of-topics)**

### 197. What are workspace APIs?

Angular 8.0 release introduces Workspace APIs to make it easier for developers to read and modify the angular.json file instead of manually modifying it. Currently, the only supported storage format is the JSON-based format used by the Angular CLI.

Example:
```typescript
import { NodeJsSyncHost } from '@angular-devkit/core/node';
import { workspaces } from '@angular-devkit/core';

async function addBuildTargetOption() {
  const host = workspaces.createWorkspaceHost(new NodeJsSyncHost());
  const workspace = await workspaces.readWorkspace('path/to/workspace/directory/', host);

  const project = workspace.projects.get('my-app');
  if (!project) {
    throw new Error('my-app does not exist');
  }

  const buildTarget = project.targets.get('build');
  if (!buildTarget) {
    throw new Error('build target does not exist');
  }

  buildTarget.options.optimization = true;

  await workspaces.writeWorkspace(workspace, host);
}

addBuildTargetOption();
```

**[⬆ Back to Top](#table-of-topics)**

---

## Advanced Features

### 198. What is Angular Material?

Angular Material is a collection of Material Design components for Angular framework following the Material Design spec.

Installation:
```bash
npm install --save @angular/material @angular/cdk @angular/animations
(OR)
yarn add @angular/material @angular/cdk @angular/animations
```

Supports the most recent two versions of all major browsers. Latest version of Angular material is 8.1.1

**[⬆ Back to Top](#table-of-topics)**

### 199. What is content projection?

Content projection is a pattern in which you insert, or project, the content you want to use inside another component. This increases component reusability.

**[⬆ Back to Top](#table-of-topics)**

### 200. What is ng-content and its purpose?

The ng-content is used to insert the content dynamically inside the component that helps to increase component reusability.

**[⬆ Back to Top](#table-of-topics)**

### 201. What is standalone component?

A standalone component is a type of component which is not part of any Angular module. It provides a simplified way to build Angular applications.

**[⬆ Back to Top](#table-of-topics)**

### 202. How to create a standalone component using CLI command?

Generate using CLI:
```bash
ng generate component component-name --standalone
```

This creates:
1. `component-name.component.ts`
2. `component-name.component.css`
3. `component-name.component.spec`
4. `component-name.component.html`

Update app.module.ts:
```typescript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { ComponentNameComponent } from './component-name/component-name.component';

@NgModule({
  imports: [
  BrowserModule,
  ComponentNameComponent
  ],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

**[⬆ Back to Top](#table-of-topics)**

### 203. How to create a standalone component manually?

Add `standalone: true` in the component:

```typescript
import { CommonModule } from '@angular/common';
import { Component, OnInit } from '@angular/core';

@Component({
  standalone: true,
  imports: [CommonModule],
  selector: 'app-standalone-component',
  templateUrl: './standalone-component.component.html',
  styleUrls: ['./standalone-component.component.css'],
})
export class ComponentNameComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
}
```

Update app.module.ts:
```typescript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { ComponentNameComponent } from './component-name/component-name.component';

@NgModule({
  imports: [
  BrowserModule,
  ComponentNameComponent
  ],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

**[⬆ Back to Top](#table-of-topics)**

### 204. What is hydration?

Hydration is the process that restores the server side rendered application on the client. This includes:
- Reusing server rendered DOM structures
- Persisting application state
- Transferring application data retrieved by the server

To enable hydration with Angular Universal:
```typescript
import {
  bootstrapApplication,
  provideClientHydration,
} from '@angular/platform-browser';

bootstrapApplication(RootCmp, {
  providers: [provideClientHydration()]
});
```

Or in App Module:
```typescript
import {provideClientHydration} from '@angular/platform-browser';
import {NgModule} from '@angular/core';

@NgModule({
  declarations: [RootCmp],
  exports: [RootCmp],
  bootstrap: [RootCmp],
  providers: [provideClientHydration()],
})
export class AppModule {}
```

**[⬆ Back to Top](#table-of-topics)**

### 205. What are Angular Signals?

A signal is a wrapper around a value that can notify interested consumers when that value changes. Signals can contain any value, from simple primitives to complex data structures.

**[⬆ Back to Top](#table-of-topics)**

### 206. Explain Angular Signals with an example

TypeScript file:
```typescript
import { Component, OnInit } from '@angular/core';
import { signal, computed } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent implements OnInit {
  count = signal(0);
  doubleCount = computed(() => this.count() * 2);

  constructor() {}

  ngOnInit() {
  // Optional logging for debugging
  }

  incrementCount() {
  this.count.set(this.count() + 1);
  }

  decrementCount() {
  this.count.update((value) => Math.max(0, value - 1));
  }
}
```

HTML file:
```html
<h1>Angular Signals Example</h1>

<button (click)="incrementCount()" style="margin-right: 10px;">Increment Count</button>
<button (click)="decrementCount()">Decrement Count</button>

<p>Count: {{ count() }}</p>
<p>Double Count: {{ doubleCount() }}</p>
```

**[⬆ Back to Top](#table-of-topics)**

### 207. What is NgRx?

NgRx is a framework for building reactive applications in Angular. It is a state management library that provides a Redux-inspired architecture for managing and centralizing application state.

Main components:
1. **Store:** Single, immutable data structure holding entire application state
2. **Actions:** Plain objects describing events that can change the state
3. **Reducers:** Pure functions taking current state and action, returning new state
4. **Effects:** Side effect handlers listening to actions
5. **Selectors:** Functions used to query and derive data from the store

NgRx is useful for:
- Complex data flows
- Multiple components sharing the same data
- Time-travel debugging
- State persistence requirements

Example:
```typescript
// Action
export const loadUsers = createAction('[User List] Load Users');

// Reducer
export const userReducer = createReducer(
  initialState,
  on(loadUsers, state => ({ ...state, loading: true }))
);

// Selector
export const selectUsers = (state: AppState) => state.users;

// Component
export class UserComponent {
  users$ = this.store.select(selectUsers);
  
  constructor(private store: Store<AppState>) {}
  
  loadUsers() {
  this.store.dispatch(loadUsers());
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 208. What is Angular Ivy?

Angular Ivy is a new rendering engine for Angular. You can choose to opt in a preview version from Angular 8.

Create new project with Ivy:
```bash
ng new ivy-demo-app --enable-ivy
```

Add to existing project in tsconfig.app.json:
```typescript
{
  "compilerOptions": { ... },
  "angularCompilerOptions": {
  "enableIvy": true
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 209. What are the features included in ivy preview?

You can expect these features:

1. Generated code that is easier to read and debug at runtime
2. Faster re-build time
3. Improved payload size
4. Improved template type checking

**[⬆ Back to Top](#table-of-topics)**

### 210. Can I use AOT compilation with Ivy?

Yes, it is a recommended configuration. AOT compilation with Ivy is faster. Set it as default in angular.json:

```typescript
{
  "projects": {
  "my-project": {
    "architect": {
    "build": {
      "options": {
      ...
      "aot": true,
      }
    }
    }
  }
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 211. What is Angular Language Service?

The Angular Language Service is a way to get completions, errors, hints, and navigation inside your Angular templates whether they are external in an HTML file or embedded in annotations/decorators. It autodetects that you are opening an Angular file, reads your `tsconfig.json` file, finds all the templates, and provides all the language services.

**[⬆ Back to Top](#table-of-topics)**

### 212. How do you install angular language service in the project?

Install with npm:
```bash
npm install --save-dev @angular/language-service
```

Add to "compilerOptions" in tsconfig.json:
```typescript
"plugins": [
  {"name": "@angular/language-service"}
]
```

**Note:** Completion and diagnostic services work for .ts files only.

**[⬆ Back to Top](#table-of-topics)**

### 213. Is there any editor support for Angular Language Service?

Yes, currently available for:
- Visual Studio Code (IDE support)
- WebStorm (IDE support)
- Sublime editor (with typescript language service plugin model)

**[⬆ Back to Top](#table-of-topics)**

### 214. Explain the features provided by Angular Language Service?

Three main features:

1. **Autocompletion:** Provides contextual possibilities and hints as you type within interpolation and elements

2. **Error checking:** Warns you of mistakes in your code

3. **Navigation:** Hover a component, directive, module and then click/press F12 to go directly to its definition

**[⬆ Back to Top](#table-of-topics)**

### 215. How do you add web workers in your application?

Add web worker using CLI:
```
ng generate web-worker app
```

This creates `src/app/app.worker.ts` and performs:
1. Configures your project to use Web Workers
2. Adds app.worker.ts to receive messages:
   ```typescript
   addEventListener('message', ({ data }) => {
   const response = `worker response to ${data}`;
   postMessage(response);
   });
   ```

3. Updates app.component.ts:
   ```typescript
   if (typeof Worker !== 'undefined') {
   const worker = new Worker('./app.worker', { type: 'module' });
   worker.onmessage = ({ data }) => {
     console.log('page got message: ${data}');
   };
   worker.postMessage('hello');
   } else {
   // Web Workers are not supported in this environment.
   }
   ```

**Note:** May need to refactor scaffolding code for sending/receiving messages.

**[⬆ Back to Top](#table-of-topics)**

### 216. What are the limitations with web workers?

Important limitations:

1. Some environments (like @angular/platform-server for Server-side Rendering) don't support Web Workers. Provide a fallback mechanism for computations.
2. Running Angular in web worker using `@angular/platform-webworker` is not yet supported in Angular CLI

**[⬆ Back to Top](#table-of-topics)**

### 217. What is Angular CLI Builder?

In Angular8, the CLI Builder API is stable and available to customize the `Angular CLI` by adding or modifying commands. You can supply a builder to perform an entirely new task or change which third-party tool is used by an existing command.

**[⬆ Back to Top](#table-of-topics)**

### 218. What is a builder?

A builder function uses the `Architect API` to perform a complex process such as "build" or "test". The builder code is defined in an npm package.

Examples: BrowserBuilder runs a webpack build for a browser target, KarmaBuilder starts the Karma server and runs a webpack build for unit tests.

**[⬆ Back to Top](#table-of-topics)**

### 219. How do you invoke a builder?

Use the Angular CLI command `ng run` to invoke a builder with a specific target configuration. The workspace configuration file, `angular.json`, contains default configurations for built-in builders.

**[⬆ Back to Top](#table-of-topics)**

### 220. How do you create app shell in Angular?

An App shell is a way to render a portion of your application via a route at build time for faster first paint.

Create using CLI:
```
ng generate appShell [options] (or)
ng g appShell [options]
```

The output is in the dist/bin folder.

**[⬆ Back to Top](#table-of-topics)**

### 221. How do you use Bazel with Angular CLI?

@angular/bazel package provides a builder for Angular CLI to use Bazel as the build tool.

1. **Use in existing application:**
```
ng add @angular/bazel
```

2. **Use in new application:**
```
npm install -g @angular/bazel
ng new --collection=@angular/bazel
```

When you use ng build and ng serve, Bazel is used and outputs results in dist/bin folder.

**[⬆ Back to Top](#table-of-topics)**

### 222. What is Bazel tool?

Bazel is a powerful build tool developed and used by Google that keeps track of dependencies between different packages and build targets. In Angular8, you can build your CLI application with Bazel.

**Note:** The Angular framework itself is built with Bazel.

**[⬆ Back to Top](#table-of-topics)**

### 223. What are the advantages of Bazel tool?

Key advantages:

1. Creates the possibility of building back-ends and front-ends with the same tool
2. Incremental build and tests
3. Creates the possibility to have remote builds and cache on a build farm

**[⬆ Back to Top](#table-of-topics)**

### 224. How do you run Bazel directly?

Bazel CLI is available under @bazel/bazel package. After installation you can apply common commands:

```
bazel build [targets] // Compile the default output artifacts of the given targets
bazel test [targets] // Run the tests with *_test targets found in the pattern
bazel run [target]: Compile the program represented by target and then run it
```

**[⬆ Back to Top](#table-of-topics)**

### 225. What is platform in Angular?

A platform is the context in which an Angular application runs. The most common platform is a web browser, but it can also be an operating system for mobile device or a web server.

The runtime-platform is provided by @angular/platform-* packages allowing applications using @angular/core and @angular/common to execute in different environments:

- **platform-browser:** While running in the browser
- **platform-server:** When SSR (server-side rendering) is used

**[⬆ Back to Top](#table-of-topics)**

### 226. What is NgUpgrade?

NgUpgrade is a library put together by the Angular team to mix and match AngularJS and Angular components. It bridges the AngularJS and Angular dependency injection systems.

**[⬆ Back to Top](#table-of-topics)**

### 227. How do you upgrade location service of angularjs?

If you are using `$location` service in your old AngularJS application, use `LocationUpgradeModule` which puts the responsibilities of `$location` service to `Location` service in Angular.

Add this module to AppModule:
```typescript
import { LocationUpgradeModule } from '@angular/common/upgrade';

@NgModule({
  imports: [
  LocationUpgradeModule.config()
  ]
})
export class AppModule {}
```

**[⬆ Back to Top](#table-of-topics)**

### 228. How do you use jquery in Angular?

Steps:

1. **Install the dependency:**
```bash
npm install --save jquery
```

2. **Add the jquery script in angular.json:**
```typescript
"scripts": [
   "node_modules/jquery/dist/jquery.min.js"
]
```

3. **Start using jquery:**

In template:
```html
<div id="elementId">
  <h1>JQuery integration</h1>
</div>
```

In component:
```typescript
import {Component, OnInit} from '@angular/core';

declare var $: any; // (or) import * as $ from 'jquery';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent implements OnInit {
  ngOnInit(): void {
  $(document).ready(() => {
    $('#elementId').css({'text-color': 'blue', 'font-size': '150%'});
  });
  }
}
```

**[⬆ Back to Top](#table-of-topics)**

### 229. What is the purpose of hidden property?

The hidden property is used to show or hide the associated DOM element based on an expression. It can be compared close to `ng-show` directive in AngularJS.

Example:
```html
<div [hidden]="!user.name">
  My name is: {{user.name}}
</div>
```

**[⬆ Back to Top](#table-of-topics)**

### 230. What is the difference between ngIf and hidden property?

Main difference:

- ***ngIf** will remove the element from the DOM
- **[hidden]** plays with the CSS style by setting `display:none`

Generally it is expensive to add and remove stuff from the DOM for frequent actions.

**[⬆ Back to Top](#table-of-topics)**

### 231. How do you inject the dynamic script in angular?

Use DomSanitizer to inject dynamic Html, Style, Script, Url:

```typescript
import { Component, OnInit } from '@angular/core';
import { DomSanitizer } from '@angular/platform-browser';

@Component({
   selector: 'my-app',
   template: `
     <div [innerHtml]="htmlSnippet"></div>
   `,
})
export class App {
   constructor(protected sanitizer: DomSanitizer) {}
   htmlSnippet: string = this.sanitizer.bypassSecurityTrustScript("<script>safeCode()</script>");
}
```

**[⬆ Back to Top](#table-of-topics)**

### 232. What is a service worker and its role in Angular?

A service worker is a script that runs in the web browser and manages caching for an application. Starting from 5.0.0 version, Angular ships with a service worker implementation.

The service worker is designed to:
- Optimize the end user experience of using an application over slow/unreliable network
- Minimize the risks of serving outdated content

**[⬆ Back to Top](#table-of-topics)**

### 233. What are the design goals of service workers?

Below are the design goals of Angular's service workers:

1. It caches an application just like installing a native application
2. A running application continues with the same version of all files without incompatible files
3. When you refresh, it loads the latest fully cached version
4. When changes are published, it immediately updates in the background
5. Service workers save bandwidth by downloading resources only when they changed

**[⬆ Back to Top](#table-of-topics)**

### 234. What is schematic?

It's a scaffolding library that defines how to generate or transform a programming project by creating, modifying, refactoring, or moving files and code. It defines rules that operate on a virtual file system called a tree.

**[⬆ Back to Top](#table-of-topics)**

### 235. What is rule in Schematics?

In schematics world, it's a function that operates on a file tree to create, delete, or modify files in a specific manner.

**[⬆ Back to Top](#table-of-topics)**

### 236. What is Schematics CLI?

Schematics come with their own command-line tool known as Schematics CLI. It is used to install the schematics executable, which you can use to create a new schematics collection with an initial named schematic.

Install Schematic CLI globally:
```bash
npm install -g @angular-devkit/schematics-cli
```

**[⬆ Back to Top](#table-of-topics)**

### 237. How do you create schematics for libraries?

Create your own schematic collections to integrate your library with Angular CLI. Three main schematics:

1. **Add schematics:** Install library using `ng add` command
   ```
   ng add @angular/material
   ```

2. **Generate schematics:** Modify projects using `ng generate` command
   ```
   ng generate @angular/material:table
   ```

3. **Update schematics:** Update library's dependencies using `ng update` command
   ```
   ng update @angular/material
   ```

**[⬆ Back to Top](#table-of-topics)**

### 238. What is an angular library?

An Angular library is an Angular project that differs from an app because it cannot run on its own. It must be imported and used in an app.

Example: Adding the service worker library to an Angular application turns it into a Progressive Web App (PWA).

**Note:** You can create your own third party library and publish it as npm package.

**[⬆ Back to Top](#table-of-topics)**

### 239. What is AOT compiler?

The AOT compiler is part of a build process that produces a small, fast, ready-to-run application package, typically for production. It converts your Angular HTML and TypeScript code into efficient JavaScript code during the build phase before the browser downloads and runs that code.

**[⬆ Back to Top](#table-of-topics)**

### 240. How do you find angular CLI version?

Angular CLI provides its installed version using below commands:

```bash
ng v
ng version
ng -v
ng --version
```

Output:
```
Angular CLI: 1.6.3
Node: 8.11.3
OS: darwin x64
Angular:
...
```

**[⬆ Back to Top](#table-of-topics)**

### 241. Give an example of few metadata errors?

Below are some of the errors encountered in metadata:

1. **Expression form not supported:**
```typescript
export class User { ... }
const prop = typeof User; // typeof is not valid in metadata
{ provide: 'token', useValue: { [prop]: 'value' } }; // bracket notation invalid
```

2. **Reference to a local (non-exported) symbol:**
```typescript
let username: string; // neither exported nor initialized
@Component({
  providers: [
  { provide: User, useValue: username }
  ]
})
```

3. **Function calls are not supported:**
```typescript
providers: [
   { provide: MyStrategy, useFactory: function() { ... } },
   { provide: OtherStrategy, useFactory: () => { ... } }
]
```

4. **Destructured variable or constant not supported:**
```typescript
import { user } from './user';
const {name, age} = user;
providers: [
   {provide: Name, useValue: name},
   {provide: Age, useValue: age},
]
```

**[⬆ Back to Top](#table-of-topics)**

---

## Angular Versions & Updates

### 242. What are major changes in Angular versions?

**(Angular 18)**

1. **Zoneless Change Detection:** Add `provideExperimentalZonelessChangeDetection` to your application. Remove zone.js from your polyfills in angular.json
2. **Coalescing by Default**
3. **Material 3, Deferrable Views, Built-in Control Flow** are now stable
4. **Improvements in Server-Side Rendering**
5. **Route Redirects as Functions**
6. **Hydration Support in CDK and Material**
7. **Robust Hosting for Your Apps with Firebase App Hosting**
8. **Improved Debugging Experience**
9. **Understanding Event Replay in Angular**

**(Angular 17)**
1. Deferrable Views introduced
2. Built-in Control Flow
3. Performance Boost with esbuild
4. Standalone Components for Enhanced Reusability
5. Improved Server-Side Rendering (SSR)

**Ivy Renderer (Angular 9+):**
Advantage: New rendering engine with improved bundle size, faster compilation, runtime performance, better tree-shakability

**Angular Language Service (Angular 9+):**
Advantage: Better editor support with autocompletion, error checking, and navigation

**Strict Mode (Angular 11+):**
Advantage: Enforces stricter type checking and better runtime performance

**Improved HMR Support (Angular 11+):**
Advantage: See changes instantly without full page refresh

**Webpack 5 Support (Angular 11+):**
Advantage: Performance improvements and better tree-shaking

**Angular Forms (Angular 8+):**
Advantage: Continuous improvements with powerful form handling

**Angular CLI Improvements:**
Advantage: New commands and optimizations for development workflow

**Angular Universal (SSR):**
Advantage: Improved initial page load times, SEO, and performance

**Angular Elements (Angular 6+):**
Advantage: Use Angular components outside Angular applications

**Improved Dependency Injection (Angular 6+):**
Advantage: More flexible and easier to use

**[⬆ Back to Top](#table-of-topics)**

### 243. What are Differences between var, let, and const?

| Feature | var | let | const |
|---- | ---- | ---- | ---- |
| Scope | Functional or global | Block scope | Block scope |
| Updated | Can be updated and re-declared | Can be updated but cannot be re-declared | Cannot be updated or re-declared |
| Initialization | Can be declared without initialization | Can be declared without initialization | Cannot be declared without initialization |
| Access before init | Accessible as "undefined" | Cannot be accessed (ReferenceError) | Cannot be accessed |
| Hoisting | Hoisted | Hoisted but in temporal dead zone | Hoisted but in temporal dead zone |

**[⬆ Back to Top](#table-of-topics)**

---


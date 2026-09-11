# 🚀 Angular Beginner to Advanced

> A complete Angular learning guide from **Beginner → Intermediate → Advanced**, including concepts, explanations, and practical code examples.

**Language:** English 🇬🇧 + Khmer 🇰🇭
**Framework:** Angular
**Language:** TypeScript
**Level:** Beginner → Advanced

---

# 📚 Table of Contents

* [1. What is Angular?](#1-what-is-angular)
* [2. Angular vs JavaScript vs React](#2-angular-vs-javascript-vs-react)
* [3. Prerequisites](#3-prerequisites)
* [4. Installing Angular](#4-installing-angular)
* [5. Creating Your First Project](#5-creating-your-first-project)
* [6. Angular Project Structure](#6-angular-project-structure)
* [7. Components](#7-components)
* [8. Templates](#8-templates)
* [9. Interpolation](#9-interpolation)
* [10. Property Binding](#10-property-binding)
* [11. Event Binding](#11-event-binding)
* [12. Two-Way Binding](#12-two-way-binding)
* [13. Control Flow](#13-control-flow)
* [14. Signals](#14-signals)
* [15. Computed Signals](#15-computed-signals)
* [16. Effects](#16-effects)
* [17. Inputs](#17-inputs)
* [18. Outputs](#18-outputs)
* [19. Components Communication](#19-components-communication)
* [20. Services](#20-services)
* [21. Dependency Injection](#21-dependency-injection)
* [22. Pipes](#22-pipes)
* [23. Custom Pipes](#23-custom-pipes)
* [24. Directives](#24-directives)
* [25. Custom Directives](#25-custom-directives)
* [26. Routing](#26-routing)
* [27. Route Parameters](#27-route-parameters)
* [28. Query Parameters](#28-query-parameters)
* [29. Route Guards](#29-route-guards)
* [30. Lazy Loading](#30-lazy-loading)
* [31. Forms](#31-forms)
* [32. Reactive Forms](#32-reactive-forms)
* [33. Form Validation](#33-form-validation)
* [34. HTTP Client](#34-http-client)
* [35. CRUD API](#35-crud-api)
* [36. HTTP Interceptors](#36-http-interceptors)
* [37. RxJS](#37-rxjs)
* [38. Observable](#38-observable)
* [39. RxJS Operators](#39-rxjs-operators)
* [40. Error Handling](#40-error-handling)
* [41. Loading State](#41-loading-state)
* [42. Authentication](#42-authentication)
* [43. JWT Authentication](#43-jwt-authentication)
* [44. State Management](#44-state-management)
* [45. Signal Store Pattern](#45-signal-store-pattern)
* [46. Environment Configuration](#46-environment-configuration)
* [47. Angular Lifecycle](#47-angular-lifecycle)
* [48. Change Detection](#48-change-detection)
* [49. OnPush](#49-onpush)
* [50. ViewChild](#50-viewchild)
* [51. ContentChild](#51-contentchild)
* [52. Dynamic Components](#52-dynamic-components)
* [53. HTTP Resource](#53-http-resource)
* [54. SSR](#54-ssr)
* [55. Security](#55-security)
* [56. Testing](#56-testing)
* [57. Performance](#57-performance)
* [58. Project Architecture](#58-project-architecture)
* [59. Best Practices](#59-best-practices)
* [60. Final Project](#60-final-project)
* [61. Learning Roadmap](#61-learning-roadmap)

---

# 1. What is Angular?

## English

Angular is a web application framework developed and maintained by Google.

It is mainly used to build:

* Single Page Applications (SPA)
* Enterprise applications
* Dashboards
* Admin systems
* E-commerce applications
* POS systems
* Large frontend applications

Angular provides many features out of the box:

* Components
* Routing
* Forms
* HTTP Client
* Dependency Injection
* Signals
* RxJS integration
* Testing
* SSR
* CLI
* Security features

Angular applications are built mainly with **TypeScript**.

Official documentation:

https://angular.dev/

## Khmer

Angular គឺជា **Web Application Framework** ដែលបង្កើត និងថែទាំដោយ Google។

វាត្រូវបានប្រើសម្រាប់បង្កើត៖

* Single Page Application
* Dashboard
* Admin System
* E-commerce
* POS System
* Enterprise Application
* Large-scale Web Application

Angular មាន feature ជាច្រើនស្រាប់ដូចជា៖

* Component
* Routing
* Form
* HTTP Client
* Dependency Injection
* Signal
* RxJS
* Testing
* SSR
* CLI
* Security

Angular ប្រើ **TypeScript** ជាភាសាសំខាន់។

---

# 2. Angular vs JavaScript vs React

| Technology | Type                 | Main Purpose             |
| ---------- | -------------------- | ------------------------ |
| JavaScript | Programming Language | Web programming          |
| TypeScript | Programming Language | JavaScript + types       |
| React      | UI Library           | Build user interfaces    |
| Angular    | Framework            | Complete web application |

## Khmer

* JavaScript = ភាសាសរសេរកម្មវិធី
* TypeScript = JavaScript ដែលមាន Type System
* React = UI Library
* Angular = Full Framework

Angular មាន tools ជាច្រើនស្រាប់ ដូចជា Router, Forms, HTTP, DI និង Testing។

---

# 3. Prerequisites

Before learning Angular, understand:

```text
HTML
  ↓
CSS
  ↓
JavaScript
  ↓
TypeScript
  ↓
Angular
```

You should know:

* HTML
* CSS
* JavaScript
* TypeScript
* ES6+
* npm
* Git
* HTTP
* REST API
* JSON

## Khmer

មុនរៀន Angular គួរតែចេះ៖

1. HTML
2. CSS
3. JavaScript
4. TypeScript
5. npm
6. Git
7. REST API
8. JSON

---

# 4. Installing Angular

Install Angular CLI:

```bash
npm install -g @angular/cli
```

Check version:

```bash
ng version
```

Create a project:

```bash
ng new angular-app
```

Run:

```bash
cd angular-app
npm start
```

Open:

```text
http://localhost:4200
```

Angular's current installation guide recommends Node.js 22.22.3 or newer for the current documentation version.

## Khmer

`Angular CLI` គឺជា command-line tool សម្រាប់៖

* បង្កើត project
* បង្កើត component
* Build
* Test
* Deploy
* Maintain application

---

# 5. Creating Your First Project

```bash
ng new my-angular-app
```

Useful options:

```bash
ng new my-angular-app --routing
```

```bash
ng new my-angular-app --style=scss
```

```bash
ng new my-angular-app --ssr
```

Generate a component:

```bash
ng generate component home
```

Short version:

```bash
ng g c home
```

Generate service:

```bash
ng generate service services/user
```

Short version:

```bash
ng g s services/user
```

---

# 6. Angular Project Structure

Typical modern Angular project:

```text
my-angular-app/
│
├── src/
│   ├── app/
│   │   ├── app.component.ts
│   │   ├── app.component.html
│   │   ├── app.component.css
│   │   ├── app.routes.ts
│   │   └── app.config.ts
│   │
│   ├── assets/
│   ├── index.html
│   ├── main.ts
│   └── styles.css
│
├── angular.json
├── package.json
├── tsconfig.json
└── README.md
```

## Important Files

### `main.ts`

Application entry point.

### `app.config.ts`

Global application configuration.

### `app.routes.ts`

Application routes.

### `app.component.ts`

Root component.

### `package.json`

Project dependencies and scripts.

---

# 7. Components

A component contains:

```text
TypeScript
HTML
CSS
```

Example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-user',
  template: `
    <h1>Hello Angular</h1>
    <p>My first component</p>
  `,
})
export class UserComponent {}
```

Angular components contain a TypeScript class, template, and selector. Modern Angular components are standalone by default.

## Khmer

Component គឺជា UI ផ្នែកតូចមួយ។

ឧទាហរណ៍៖

```text
Navbar
Sidebar
Login Form
Product Card
User Table
Footer
```

អាចបែងចែកជា Component ដាច់ៗ។

---

# 8. Templates

HTML template:

```html
<h1>Hello Angular</h1>

<p>This is my application.</p>

<button>Click Me</button>
```

Component:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
})
export class AppComponent {}
```

---

# 9. Interpolation

Interpolation displays data.

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <h1>{{ title }}</h1>
    <p>Age: {{ age }}</p>
  `,
})
export class AppComponent {
  title = 'Angular Application';
  age = 20;
}
```

Output:

```text
Angular Application
Age: 20
```

## Khmer

`{{ }}` ប្រើសម្រាប់បង្ហាញ value ពី TypeScript ទៅ HTML។

```typescript
name = 'Heng';
```

```html
<h1>{{ name }}</h1>
```

---

# 10. Property Binding

Property binding uses:

```html
[property]="value"
```

Example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <img [src]="imageUrl" [alt]="imageAlt">
  `,
})
export class AppComponent {
  imageUrl = 'https://example.com/image.jpg';
  imageAlt = 'Product';
}
```

Another example:

```html
<button [disabled]="isDisabled">
  Save
</button>
```

```typescript
isDisabled = true;
```

## Khmer

Property Binding គឺការបញ្ជូន data ពី TypeScript ទៅ property របស់ HTML element។

---

# 11. Event Binding

Event binding:

```html
(event)="function()"
```

Example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-counter',
  template: `
    <h1>{{ count }}</h1>

    <button (click)="increment()">
      Increase
    </button>
  `,
})
export class CounterComponent {
  count = 0;

  increment(): void {
    this.count++;
  }
}
```

## Khmer

Event Binding ប្រើសម្រាប់ទទួល event ពី User ដូចជា៖

* click
* input
* submit
* keydown
* mouseover

---

# 12. Two-Way Binding

Two-way binding:

```html
[(ngModel)]="name"
```

Import FormsModule:

```typescript
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-root',
  imports: [FormsModule],
  template: `
    <input [(ngModel)]="name">

    <p>Hello {{ name }}</p>
  `,
})
export class AppComponent {
  name = '';
}
```

## Khmer

Two-way binding មានន័យថា៖

```text
TypeScript → HTML
HTML → TypeScript
```

Data អាចផ្លាស់ប្តូរទាំងពីរទិស។

---

# 13. Control Flow

Modern Angular supports built-in control flow.

## `@if`

```html
@if (isLoggedIn) {
  <p>Welcome!</p>
} @else {
  <p>Please login.</p>
}
```

TypeScript:

```typescript
isLoggedIn = true;
```

## `@for`

```html
<ul>
  @for (user of users; track user.id) {
    <li>
      {{ user.name }}
    </li>
  }
</ul>
```

TypeScript:

```typescript
users = [
  { id: 1, name: 'Dara' },
  { id: 2, name: 'Sok' },
  { id: 3, name: 'Heng' },
];
```

## `@switch`

```html
@switch (role) {
  @case ('admin') {
    <p>Admin</p>
  }

  @case ('user') {
    <p>User</p>
  }

  @default {
    <p>Unknown</p>
  }
}
```

## Khmer

Control Flow ប្រើសម្រាប់គ្រប់គ្រង logic នៅក្នុង template។

```text
@if      → condition
@for     → loop
@switch  → multiple conditions
```

---

# 14. Signals

Signals are Angular's reactive state primitive.

```typescript
import { Component, signal } from '@angular/core';

@Component({
  selector: 'app-counter',
  template: `
    <h1>{{ count() }}</h1>

    <button (click)="increment()">
      +
    </button>

    <button (click)="decrement()">
      -
    </button>
  `,
})
export class CounterComponent {
  count = signal(0);

  increment(): void {
    this.count.update(value => value + 1);
  }

  decrement(): void {
    this.count.update(value => value - 1);
  }
}
```

A signal is read by calling it:

```typescript
count()
```

Update:

```typescript
count.set(10);
```

Or:

```typescript
count.update(value => value + 1);
```

Angular Signals track where state is used and notify consumers when the state changes.

## Khmer

Signal គឺជា reactive state។

ធម្មតា៖

```typescript
count = 0;
```

Signal៖

```typescript
count = signal(0);
```

អាន៖

```typescript
count()
```

កំណត់ value:

```typescript
count.set(10);
```

Update:

```typescript
count.update(value => value + 1);
```

---

# 15. Computed Signals

Use `computed()` for derived values.

```typescript
import {
  Component,
  signal,
  computed,
} from '@angular/core';

@Component({
  selector: 'app-cart',
  template: `
    <p>Price: ${{ price() }}</p>
    <p>Quantity: {{ quantity() }}</p>
    <p>Total: ${{ total() }}</p>
  `,
})
export class CartComponent {
  price = signal(10);
  quantity = signal(3);

  total = computed(() =>
    this.price() * this.quantity()
  );
}
```

## Khmer

`computed()` ប្រើសម្រាប់ value ដែលគណនាចេញពី signal ផ្សេងទៀត។

```text
price × quantity = total
```

មិនគួរ manually update `total` ទេ។

---

# 16. Effects

`effect()` runs when signals it reads change.

```typescript
import {
  Component,
  effect,
  signal,
} from '@angular/core';

@Component({
  selector: 'app-example',
  template: `
    <button (click)="increase()">
      Increase
    </button>
  `,
})
export class ExampleComponent {
  count = signal(0);

  constructor() {
    effect(() => {
      console.log('Count:', this.count());
    });
  }

  increase(): void {
    this.count.update(value => value + 1);
  }
}
```

## Khmer

`effect()` ប្រើនៅពេលយើងចង់ធ្វើ side effect ពេល signal ផ្លាស់ប្តូរ។

ឧទាហរណ៍៖

* logging
* localStorage
* analytics
* external API integration

កុំប្រើ `effect()` សម្រាប់ derived state ប្រសិនបើ `computed()` អាចប្រើបាន។

---

# 17. Inputs

Parent → Child.

Modern input:

```typescript
import {
  Component,
  input,
} from '@angular/core';

@Component({
  selector: 'app-user-card',
  template: `
    <h2>{{ name() }}</h2>
    <p>Age: {{ age() }}</p>
  `,
})
export class UserCardComponent {
  name = input.required<string>();
  age = input<number>(0);
}
```

Parent:

```typescript
import { Component } from '@angular/core';
import { UserCardComponent } from './user-card.component';

@Component({
  selector: 'app-parent',
  imports: [UserCardComponent],
  template: `
    <app-user-card
      [name]="'Heng'"
      [age]="22"
    />
  `,
})
export class ParentComponent {}
```

## Khmer

Input ប្រើសម្រាប់បញ្ជូន data៖

```text
Parent
   ↓
Child
```

---

# 18. Outputs

Child → Parent.

```typescript
import {
  Component,
  output,
} from '@angular/core';

@Component({
  selector: 'app-child',
  template: `
    <button (click)="save()">
      Save
    </button>
  `,
})
export class ChildComponent {
  saved = output<string>();

  save(): void {
    this.saved.emit('Saved successfully');
  }
}
```

Parent:

```typescript
import { Component } from '@angular/core';
import { ChildComponent } from './child.component';

@Component({
  selector: 'app-parent',
  imports: [ChildComponent],
  template: `
    <app-child
      (saved)="handleSaved($event)"
    />
  `,
})
export class ParentComponent {
  handleSaved(message: string): void {
    console.log(message);
  }
}
```

## Khmer

Output ប្រើសម្រាប់បញ្ជូន event៖

```text
Child
  ↓
Parent
```

---

# 19. Components Communication

Common patterns:

```text
Parent → Child
Input

Child → Parent
Output

Shared State
Service + Signal

Large Application
State Management
```

Example:

```text
App
│
├── Navbar
│
├── Sidebar
│
└── Dashboard
     │
     ├── UserCard
     └── ProductList
```

---

# 20. Services

Create:

```bash
ng g s services/user
```

Service:

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class UserService {

  getUserName(): string {
    return 'Heng';
  }
}
```

Component:

```typescript
import { Component, inject } from '@angular/core';
import { UserService } from './services/user.service';

@Component({
  selector: 'app-profile',
  template: `
    <h1>{{ name }}</h1>
  `,
})
export class ProfileComponent {
  private userService = inject(UserService);

  name = this.userService.getUserName();
}
```

## Khmer

Service ប្រើសម្រាប់ logic ដែលត្រូវការ reuse។

ឧទាហរណ៍៖

* API
* Authentication
* User management
* Shared state
* Business logic

---

# 21. Dependency Injection

Angular has Dependency Injection built into the framework.

Example:

```typescript
@Injectable({
  providedIn: 'root',
})
export class LoggerService {
  log(message: string): void {
    console.log(message);
  }
}
```

Inject:

```typescript
private logger = inject(LoggerService);
```

Use:

```typescript
this.logger.log('Hello');
```

## Khmer

Dependency Injection មានន័យថា Angular ជួយបង្កើត និងផ្តល់ object/service ដែល component ត្រូវការ។

---

# 22. Pipes

Built-in pipes:

```html
<p>{{ name | uppercase }}</p>

<p>{{ name | lowercase }}</p>

<p>{{ price | currency }}</p>

<p>{{ date | date }}</p>
```

Example:

```typescript
name = 'heng';
price = 100;
date = new Date();
```

Output:

```text
HENG
$100.00
Sep 11, 2026
```

---

# 23. Custom Pipes

Generate:

```bash
ng g pipe pipes/reverse
```

Code:

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'reverse',
})
export class ReversePipe implements PipeTransform {

  transform(value: string): string {
    return value
      .split('')
      .reverse()
      .join('');
  }
}
```

Use:

```html
<p>{{ 'Angular' | reverse }}</p>
```

Output:

```text
ralugnA
```

## Khmer

Custom Pipe ប្រើសម្រាប់ transform data មុនបង្ហាញ។

---

# 24. Directives

Directive changes the behavior or appearance of an element.

Common built-in concepts:

```html
[class.active]="isActive"

[style.color]="color"
```

Example:

```html
<p [class.active]="isActive">
  User status
</p>
```

---

# 25. Custom Directives

Generate:

```bash
ng g directive directives/highlight
```

Code:

```typescript
import {
  Directive,
  ElementRef,
  Renderer2,
} from '@angular/core';

@Directive({
  selector: '[appHighlight]',
})
export class HighlightDirective {

  constructor(
    private element: ElementRef,
    private renderer: Renderer2,
  ) {
    this.renderer.setStyle(
      this.element.nativeElement,
      'background',
      'yellow'
    );
  }
}
```

Use:

```html
<p appHighlight>
  Highlight me
</p>
```

---

# 26. Routing

Angular Router manages navigation between views in a Single Page Application.

`app.routes.ts`:

```typescript
import { Routes } from '@angular/router';
import { HomeComponent } from './pages/home/home.component';
import { AboutComponent } from './pages/about/about.component';

export const routes: Routes = [
  {
    path: '',
    component: HomeComponent,
  },
  {
    path: 'about',
    component: AboutComponent,
  },
  {
    path: '**',
    redirectTo: '',
  },
];
```

Configure router:

```typescript
import { ApplicationConfig } from '@angular/core';
import { provideRouter } from '@angular/router';
import { routes } from './app.routes';

export const appConfig: ApplicationConfig = {
  providers: [
    provideRouter(routes),
  ],
};
```

Template:

```html
<nav>
  <a routerLink="/">Home</a>
  <a routerLink="/about">About</a>
</nav>

<router-outlet />
```

---

# 27. Route Parameters

Routes:

```typescript
export const routes: Routes = [
  {
    path: 'users/:id',
    component: UserDetailComponent,
  },
];
```

URL:

```text
/users/123
```

Component:

```typescript
import {
  ActivatedRoute,
} from '@angular/router';
import { Component, inject } from '@angular/core';

@Component({
  selector: 'app-user-detail',
  template: `
    <h1>User ID: {{ userId }}</h1>
  `,
})
export class UserDetailComponent {

  private route = inject(ActivatedRoute);

  userId = this.route.snapshot.paramMap.get('id');
}
```

## Khmer

`:id` គឺ Dynamic Route Parameter។

```text
/users/1
/users/2
/users/3
```

Component មួយអាចទទួល ID ខុសៗគ្នា។

---

# 28. Query Parameters

Navigate:

```typescript
import { Router, NavigationExtras } from '@angular/router';

const router = inject(Router);

router.navigate(
  ['/products'],
  {
    queryParams: {
      category: 'phone',
      page: 2,
    },
  }
);
```

URL:

```text
/products?category=phone&page=2
```

Read:

```typescript
private route = inject(ActivatedRoute);

category =
  this.route.snapshot.queryParamMap.get('category');
```

---

# 29. Route Guards

Guard protects routes.

Create:

```bash
ng g guard guards/auth
```

Example:

```typescript
import {
  CanActivateFn,
  Router,
} from '@angular/router';
import { inject } from '@angular/core';

export const authGuard: CanActivateFn = () => {

  const router = inject(Router);

  const token =
    localStorage.getItem('token');

  if (token) {
    return true;
  }

  return router.createUrlTree(['/login']);
};
```

Route:

```typescript
{
  path: 'dashboard',
  component: DashboardComponent,
  canActivate: [authGuard],
}
```

## Khmer

Guard ប្រើសម្រាប់ការពារ route។

ឧទាហរណ៍៖

```text
/login
   ↓
authenticate
   ↓
/dashboard
```

បើគ្មាន token → `/login`

---

# 30. Lazy Loading

Lazy loading prevents loading every page immediately.

```typescript
export const routes: Routes = [
  {
    path: 'admin',
    loadComponent: () =>
      import('./pages/admin/admin.component')
        .then(m => m.AdminComponent),
  },
];
```

Or lazy-load routes:

```typescript
{
  path: 'admin',
  loadChildren: () =>
    import('./admin/admin.routes')
      .then(m => m.ADMIN_ROUTES),
}
```

## Khmer

Lazy Loading មានន័យថា៖

```text
User មិនទាន់ចូល Admin
        ↓
មិនទាន់ Load Admin code
        ↓
User ចូល Admin
        ↓
Load Admin code
```

វាជួយ performance។

---

# 31. Forms

Angular supports multiple form approaches.

Main approaches:

```text
Template-driven Forms
Reactive Forms
Signal Forms
```

For traditional Angular applications, Reactive Forms are widely useful for complex forms.

---

# 32. Reactive Forms

```typescript
import {
  Component,
  inject,
} from '@angular/core';

import {
  FormBuilder,
  ReactiveFormsModule,
} from '@angular/forms';

@Component({
  selector: 'app-login',
  imports: [ReactiveFormsModule],
  template: `
    <form [formGroup]="form" (ngSubmit)="submit()">

      <input
        type="email"
        formControlName="email"
      />

      <input
        type="password"
        formControlName="password"
      />

      <button type="submit">
        Login
      </button>

    </form>
  `,
})
export class LoginComponent {

  private fb = inject(FormBuilder);

  form = this.fb.nonNullable.group({
    email: [''],
    password: [''],
  });

  submit(): void {
    console.log(this.form.value);
  }
}
```

---

# 33. Form Validation

```typescript
import {
  Validators,
} from '@angular/forms';

form = this.fb.nonNullable.group({
  email: [
    '',
    [
      Validators.required,
      Validators.email,
    ],
  ],

  password: [
    '',
    [
      Validators.required,
      Validators.minLength(6),
    ],
  ],
});
```

HTML:

```html
<form
  [formGroup]="form"
  (ngSubmit)="submit()"
>

  <input
    type="email"
    formControlName="email"
  >

  @if (
    form.controls.email.touched &&
    form.controls.email.invalid
  ) {
    <p>Email is invalid.</p>
  }

  <input
    type="password"
    formControlName="password"
  >

  @if (
    form.controls.password.touched &&
    form.controls.password.invalid
  ) {
    <p>Password must be at least 6 characters.</p>
  }

  <button
    type="submit"
    [disabled]="form.invalid"
  >
    Login
  </button>

</form>
```

---

# 34. HTTP Client

Angular provides `HttpClient` for communicating with backend services.

Configure:

```typescript
import {
  ApplicationConfig,
} from '@angular/core';

import {
  provideHttpClient,
} from '@angular/common/http';

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient(),
  ],
};
```

Service:

```typescript
import {
  Injectable,
  inject,
} from '@angular/core';

import {
  HttpClient,
} from '@angular/common/http';

import {
  Observable,
} from 'rxjs';

export interface User {
  id: number;
  name: string;
  email: string;
}

@Injectable({
  providedIn: 'root',
})
export class UserService {

  private http = inject(HttpClient);

  private apiUrl =
    'https://api.example.com/users';

  getUsers(): Observable<User[]> {
    return this.http.get<User[]>(
      this.apiUrl
    );
  }
}
```

---

# 35. CRUD API

## GET

```typescript
getUsers() {
  return this.http.get<User[]>(
    this.apiUrl
  );
}
```

## GET by ID

```typescript
getUser(id: number) {
  return this.http.get<User>(
    `${this.apiUrl}/${id}`
  );
}
```

## POST

```typescript
createUser(user: User) {
  return this.http.post<User>(
    this.apiUrl,
    user
  );
}
```

## PUT

```typescript
updateUser(
  id: number,
  user: User
) {
  return this.http.put<User>(
    `${this.apiUrl}/${id}`,
    user
  );
}
```

## DELETE

```typescript
deleteUser(id: number) {
  return this.http.delete<void>(
    `${this.apiUrl}/${id}`
  );
}
```

Angular `HttpClient` methods return RxJS Observables, and a request is made when the Observable is subscribed to.

---

# 36. HTTP Interceptors

Functional interceptors are recommended for modern Angular applications.

Example authentication interceptor:

```typescript
import {
  HttpInterceptorFn,
} from '@angular/common/http';

export const authInterceptor: HttpInterceptorFn =
  (req, next) => {

    const token =
      localStorage.getItem('token');

    if (!token) {
      return next(req);
    }

    const clonedRequest = req.clone({
      setHeaders: {
        Authorization: `Bearer ${token}`,
      },
    });

    return next(clonedRequest);
  };
```

Register:

```typescript
import {
  provideHttpClient,
  withInterceptors,
} from '@angular/common/http';

import {
  authInterceptor,
} from './interceptors/auth.interceptor';

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient(
      withInterceptors([
        authInterceptor,
      ])
    ),
  ],
};
```

Angular's current HTTP documentation recommends functional interceptors because their ordering is more predictable.

---

# 37. RxJS

RxJS means:

```text
Reactive Extensions for JavaScript
```

Angular uses RxJS heavily for asynchronous programming.

Common concepts:

```text
Observable
Observer
Subscription
Subject
BehaviorSubject
Operators
```

---

# 38. Observable

Example:

```typescript
import {
  Observable,
} from 'rxjs';

const numbers$ =
  new Observable<number>(subscriber => {

    subscriber.next(1);
    subscriber.next(2);
    subscriber.next(3);

    subscriber.complete();
  });

numbers$.subscribe({
  next: value => {
    console.log(value);
  },

  complete: () => {
    console.log('Done');
  },
});
```

Output:

```text
1
2
3
Done
```

---

# 39. RxJS Operators

Common operators:

```text
map
filter
tap
switchMap
mergeMap
concatMap
catchError
debounceTime
distinctUntilChanged
forkJoin
combineLatest
```

Example:

```typescript
import {
  map,
  filter,
} from 'rxjs/operators';

this.userService
  .getUsers()
  .pipe(
    filter(users => users.length > 0),
    map(users =>
      users.map(user => ({
        ...user,
        name: user.name.toUpperCase(),
      }))
    )
  )
  .subscribe(users => {
    console.log(users);
  });
```

---

# 40. Error Handling

Use `catchError`.

```typescript
import {
  catchError,
} from 'rxjs/operators';

import {
  throwError,
} from 'rxjs';

getUsers() {
  return this.http
    .get<User[]>(this.apiUrl)
    .pipe(
      catchError(error => {
        console.error(
          'API Error:',
          error
        );

        return throwError(
          () => error
        );
      })
    );
}
```

## Khmer

Error handling សំខាន់សម្រាប់៖

* API error
* Network error
* Authentication error
* Validation error
* Server error

---

# 41. Loading State

Using signals:

```typescript
loading = signal(false);
users = signal<User[]>([]);
error = signal<string | null>(null);
```

Load:

```typescript
loadUsers(): void {

  this.loading.set(true);
  this.error.set(null);

  this.userService
    .getUsers()
    .subscribe({
      next: users => {
        this.users.set(users);
        this.loading.set(false);
      },

      error: () => {
        this.error.set(
          'Failed to load users'
        );

        this.loading.set(false);
      },
    });
}
```

HTML:

```html
@if (loading()) {
  <p>Loading...</p>
}

@if (error()) {
  <p>{{ error() }}</p>
}

@if (!loading()) {
  @for (user of users(); track user.id) {
    <p>{{ user.name }}</p>
  }
}
```

---

# 42. Authentication

Typical authentication flow:

```text
User
 ↓
Login Form
 ↓
POST /login
 ↓
Backend
 ↓
JWT Token
 ↓
Frontend stores token
 ↓
Interceptor
 ↓
Authorization: Bearer TOKEN
 ↓
Protected API
```

Login service:

```typescript
login(email: string, password: string) {

  return this.http.post<{
    token: string;
  }>(
    `${this.apiUrl}/login`,
    {
      email,
      password,
    }
  );
}
```

---

# 43. JWT Authentication

Example:

```typescript
login(): void {

  const { email, password } =
    this.form.getRawValue();

  this.authService
    .login(email, password)
    .subscribe({
      next: response => {

        localStorage.setItem(
          'token',
          response.token
        );

        this.router.navigate([
          '/dashboard',
        ]);
      },
    });
}
```

Interceptor:

```typescript
const token =
  localStorage.getItem('token');

const request = req.clone({
  setHeaders: {
    Authorization: `Bearer ${token}`,
  },
});

return next(request);
```

> Production applications should carefully consider token storage and XSS/CSRF risks rather than blindly copying this example.

---

# 44. State Management

There are different levels of state management.

## Local state

```typescript
count = signal(0);
```

## Component state

```typescript
users = signal<User[]>([]);
```

## Shared state

```text
Service
 +
Signals
```

## Large application

Possible options include:

```text
Signal-based store pattern
NgRx
Other state libraries
```

Do not introduce a large state-management library unless the application's complexity actually needs it.

---

# 45. Signal Store Pattern

Simple shared store:

```typescript
import {
  Injectable,
  computed,
  signal,
} from '@angular/core';

export interface User {
  id: number;
  name: string;
}

@Injectable({
  providedIn: 'root',
})
export class UserStore {

  private _users =
    signal<User[]>([]);

  readonly users =
    this._users.asReadonly();

  readonly count =
    computed(() => this._users().length);

  setUsers(users: User[]): void {
    this._users.set(users);
  }

  addUser(user: User): void {
    this._users.update(users => [
      ...users,
      user,
    ]);
  }

  removeUser(id: number): void {
    this._users.update(users =>
      users.filter(user => user.id !== id)
    );
  }
}
```

Component:

```typescript
private userStore =
  inject(UserStore);

users =
  this.userStore.users;

count =
  this.userStore.count;
```

HTML:

```html
<p>Total users: {{ count() }}</p>

@for (user of users(); track user.id) {
  <p>{{ user.name }}</p>
}
```

---

# 46. Environment Configuration

Development:

```typescript
export const environment = {
  production: false,
  apiUrl: 'http://localhost:3000/api',
};
```

Production:

```typescript
export const environment = {
  production: true,
  apiUrl: 'https://api.example.com',
};
```

Use:

```typescript
import {
  environment,
} from '../environments/environment';

const apiUrl =
  environment.apiUrl;
```

Never put secrets such as:

```text
Database passwords
Private API keys
JWT signing secrets
Cloud credentials
```

inside frontend environment files.

---

# 47. Angular Lifecycle

Common lifecycle hooks:

```text
constructor
ngOnChanges
ngOnInit
ngDoCheck
ngAfterContentInit
ngAfterContentChecked
ngAfterViewInit
ngAfterViewChecked
ngOnDestroy
```

Example:

```typescript
import {
  Component,
  OnInit,
  OnDestroy,
} from '@angular/core';

@Component({
  selector: 'app-example',
  template: `<p>Hello</p>`,
})
export class ExampleComponent
  implements OnInit, OnDestroy {

  ngOnInit(): void {
    console.log('Component initialized');
  }

  ngOnDestroy(): void {
    console.log('Component destroyed');
  }
}
```

---

# 48. Change Detection

Angular must determine when the UI needs updating.

Example:

```typescript
count = signal(0);
```

When:

```typescript
this.count.set(10);
```

Angular updates places where the signal is consumed.

Signals are designed for granular reactive tracking.

---

# 49. OnPush

For component-level optimization:

```typescript
import {
  ChangeDetectionStrategy,
  Component,
} from '@angular/core';

@Component({
  selector: 'app-product',
  changeDetection:
    ChangeDetectionStrategy.OnPush,

  template: `
    <h1>{{ title }}</h1>
  `,
})
export class ProductComponent {
  title = 'Products';
}
```

Use immutable data:

```typescript
const updatedUsers = [
  ...users,
  newUser,
];
```

Instead of mutating:

```typescript
users.push(newUser);
```

---

# 50. ViewChild

`ViewChild` accesses something inside the component view.

Example:

```typescript
import {
  Component,
  ElementRef,
  ViewChild,
} from '@angular/core';

@Component({
  selector: 'app-example',
  template: `
    <input #username>

    <button (click)="focusInput()">
      Focus
    </button>
  `,
})
export class ExampleComponent {

  @ViewChild('username')
  username!: ElementRef<HTMLInputElement>;

  focusInput(): void {
    this.username.nativeElement.focus();
  }
}
```

## Khmer

`ViewChild` ប្រើសម្រាប់ access element/component នៅក្នុង view របស់ component។

---

# 51. ContentChild

Content projection:

```html
<app-card>
  <p>Hello from parent</p>
</app-card>
```

Card:

```html
<div class="card">
  <ng-content />
</div>
```

This allows the parent to provide content to the child.

---

# 52. Dynamic Components

Angular can create components dynamically.

Example concept:

```typescript
import {
  ViewContainerRef,
} from '@angular/core';

export class DashboardComponent {

  constructor(
    private container:
      ViewContainerRef
  ) {}

  load(): void {
    // Dynamic component creation
  }
}
```

A common modern pattern is to use `ViewContainerRef` with `createComponent()`.

```typescript
const componentRef =
  this.container.createComponent(
    UserCardComponent
  );
```

---

# 53. HTTP Resource

Modern Angular provides reactive resource APIs for asynchronous data.

Example concept:

```typescript
import {
  httpResource,
} from '@angular/common/http';

userResource =
  httpResource<User>(
    () => '/api/user'
  );
```

The exact resource API should be used according to the Angular version and project requirements.

Angular's current documentation lists `httpResource()` among its modern reactive APIs.

---

# 54. SSR

SSR means:

```text
Server-Side Rendering
```

Normal SPA:

```text
Browser
 ↓
JavaScript
 ↓
Angular
 ↓
HTML
```

SSR:

```text
Browser
 ↓
Server
 ↓
Angular renders HTML
 ↓
Browser
 ↓
Hydration
```

Create project with SSR:

```bash
ng new my-app --ssr
```

Benefits:

* Better initial rendering
* SEO improvements
* Better perceived performance

Angular supports SSR and static site generation.

---

# 55. Security

Important Angular security practices:

## 1. Never trust frontend validation

Frontend:

```typescript
Validators.required
```

Backend must also validate.

## 2. Avoid unsafe HTML

Do not blindly bypass Angular sanitization.

Avoid:

```typescript
bypassSecurityTrustHtml()
```

unless you fully understand the security implications.

## 3. Protect APIs

Frontend guards are not enough.

Backend must verify:

```text
Authentication
Authorization
Role
Permission
Token
```

## 4. Avoid secrets

Never put:

```text
DB_PASSWORD
JWT_SECRET
PRIVATE_KEY
```

in frontend code.

---

# 56. Testing

Angular supports unit testing.

Example:

```typescript
describe('CounterComponent', () => {

  it('should increase count', () => {

    let count = 0;

    count++;

    expect(count).toBe(1);
  });

});
```

Component testing can use Angular's testing utilities.

Current Angular tooling uses Vitest as the primary test runner in modern Angular versions.

Run tests:

```bash
ng test
```

---

# 57. Performance

Important performance techniques:

## Lazy Loading

```typescript
loadComponent()
```

## Track Lists

```html
@for (
  user of users();
  track user.id
) {
  ...
}
```

## Signals

```typescript
users = signal<User[]>([]);
```

## OnPush

```typescript
changeDetection:
  ChangeDetectionStrategy.OnPush
```

## Avoid unnecessary subscriptions

Prefer:

```text
async pipe
signals
toSignal()
```

when appropriate.

## Production build

```bash
ng build
```

---

# 58. Project Architecture

For a real-world application:

```text
src/
│
└── app/
    │
    ├── core/
    │   ├── guards/
    │   ├── interceptors/
    │   ├── services/
    │   └── models/
    │
    ├── shared/
    │   ├── components/
    │   ├── directives/
    │   └── pipes/
    │
    ├── features/
    │   │
    │   ├── auth/
    │   │   ├── pages/
    │   │   ├── components/
    │   │   └── services/
    │   │
    │   ├── users/
    │   │   ├── pages/
    │   │   ├── components/
    │   │   └── services/
    │   │
    │   └── products/
    │       ├── pages/
    │       ├── components/
    │       └── services/
    │
    ├── app.component.ts
    ├── app.config.ts
    └── app.routes.ts
```

## Explanation

### `core`

Application-wide services.

```text
Auth
Guards
Interceptors
Global services
```

### `shared`

Reusable UI.

```text
Button
Modal
Table
Pipe
Directive
```

### `features`

Business features.

```text
Auth
Users
Products
Orders
Reports
```

## Khmer

Architecture ល្អជួយឱ្យ project ធំមិនច្របូកច្របល់។

គោលការណ៍៖

```text
Core
 ↓
Global application logic

Shared
 ↓
Reusable UI

Features
 ↓
Business modules
```

---

# 59. Best Practices

## 1. Use TypeScript types

Bad:

```typescript
user: any;
```

Better:

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

user: User;
```

---

## 2. Keep components small

Bad:

```text
One component
 ├── API
 ├── Authentication
 ├── Validation
 ├── Business logic
 ├── 1000 lines HTML
 └── 1000 lines TypeScript
```

Better:

```text
Component
 ↓
Service
 ↓
API
```

---

## 3. Keep API logic in services

Bad:

```typescript
this.http.get('/api/users');
```

inside many components.

Better:

```typescript
userService.getUsers();
```

Angular's HTTP documentation recommends reusable injectable services to isolate and encapsulate data access logic.

---

## 4. Use interfaces

```typescript
export interface Product {
  id: number;
  name: string;
  price: number;
  stock: number;
}
```

---

## 5. Use meaningful names

Bad:

```typescript
x
data
foo
abc
```

Good:

```typescript
products
selectedProduct
totalPrice
isLoading
```

---

## 6. Avoid unnecessary state

Bad:

```typescript
price = signal(100);
quantity = signal(2);
total = signal(200);
```

Better:

```typescript
price = signal(100);
quantity = signal(2);

total = computed(() =>
  this.price() * this.quantity()
);
```

---

# 60. Final Project

After learning the above topics, build a complete project.

## 🛒 E-Commerce Admin System

Features:

```text
Authentication
│
├── Login
├── Logout
└── Authorization
```

Products:

```text
Products
├── List
├── Create
├── Edit
├── Delete
└── Search
```

Orders:

```text
Orders
├── Order List
├── Order Detail
├── Update Status
└── Cancel Order
```

Users:

```text
Users
├── User List
├── User Detail
├── Create
├── Edit
└── Delete
```

Dashboard:

```text
Dashboard
├── Total Sales
├── Total Orders
├── Total Customers
├── Products
└── Reports
```

---

# Example Final Architecture

```text
Angular Application
│
├── Authentication
│
├── Router
│
├── Guards
│
├── Interceptors
│
├── Components
│
├── Services
│
├── Signals
│
├── RxJS
│
├── Forms
│
├── HTTP Client
│
├── State Management
│
└── Backend API
```

---

# Complete Example: User Management

## Model

```typescript
export interface User {
  id: number;
  name: string;
  email: string;
}
```

---

## Service

```typescript
import {
  Injectable,
  inject,
} from '@angular/core';

import {
  HttpClient,
} from '@angular/common/http';

import {
  Observable,
} from 'rxjs';

import {
  User,
} from '../models/user';

@Injectable({
  providedIn: 'root',
})
export class UserService {

  private http = inject(HttpClient);

  private readonly apiUrl =
    'https://api.example.com/users';

  getUsers(): Observable<User[]> {
    return this.http.get<User[]>(
      this.apiUrl
    );
  }

  getUser(id: number): Observable<User> {
    return this.http.get<User>(
      `${this.apiUrl}/${id}`
    );
  }

  createUser(
    user: Omit<User, 'id'>
  ): Observable<User> {

    return this.http.post<User>(
      this.apiUrl,
      user
    );
  }

  updateUser(
    id: number,
    user: Partial<User>
  ): Observable<User> {

    return this.http.patch<User>(
      `${this.apiUrl}/${id}`,
      user
    );
  }

  deleteUser(id: number): Observable<void> {

    return this.http.delete<void>(
      `${this.apiUrl}/${id}`
    );
  }
}
```

---

## Component

```typescript
import {
  Component,
  inject,
  signal,
} from '@angular/core';

import {
  UserService,
} from '../../services/user.service';

import {
  User,
} from '../../models/user';

@Component({
  selector: 'app-user-list',
  templateUrl: './user-list.component.html',
})
export class UserListComponent {

  private userService =
    inject(UserService);

  users = signal<User[]>([]);

  loading = signal(false);

  error = signal<string | null>(null);

  ngOnInit(): void {
    this.loadUsers();
  }

  loadUsers(): void {

    this.loading.set(true);
    this.error.set(null);

    this.userService
      .getUsers()
      .subscribe({
        next: users => {
          this.users.set(users);
          this.loading.set(false);
        },

        error: error => {
          console.error(error);

          this.error.set(
            'Unable to load users.'
          );

          this.loading.set(false);
        },
      });
  }

  deleteUser(id: number): void {

    this.userService
      .deleteUser(id)
      .subscribe({
        next: () => {
          this.users.update(users =>
            users.filter(
              user => user.id !== id
            )
          );
        },

        error: error => {
          console.error(error);
        },
      });
  }
}
```

---

## HTML

```html
<h1>Users</h1>

@if (loading()) {

  <p>Loading users...</p>

} @else if (error()) {

  <p>{{ error() }}</p>

} @else {

  @if (users().length === 0) {

    <p>No users found.</p>

  } @else {

    <table>

      <thead>
        <tr>
          <th>ID</th>
          <th>Name</th>
          <th>Email</th>
          <th>Action</th>
        </tr>
      </thead>

      <tbody>

        @for (
          user of users();
          track user.id
        ) {

          <tr>

            <td>
              {{ user.id }}
            </td>

            <td>
              {{ user.name }}
            </td>

            <td>
              {{ user.email }}
            </td>

            <td>

              <button
                (click)="deleteUser(user.id)"
              >
                Delete
              </button>

            </td>

          </tr>

        }

      </tbody>

    </table>

  }

}
```

---

# 61. Learning Roadmap

## 🟢 Beginner

Learn in this order:

```text
1. HTML
2. CSS
3. JavaScript
4. TypeScript
5. Angular CLI
6. Components
7. Templates
8. Interpolation
9. Property Binding
10. Event Binding
11. Two-Way Binding
12. Control Flow
13. Pipes
14. Directives
```

---

# 🟡 Intermediate

Then learn:

```text
15. Services
16. Dependency Injection
17. Signals
18. Computed
19. Effects
20. Input
21. Output
22. Component Communication
23. Routing
24. Route Parameters
25. Query Parameters
26. Guards
27. Lazy Loading
28. Reactive Forms
29. Validation
30. HTTP Client
31. CRUD
32. RxJS
33. Observable
34. RxJS Operators
35. Error Handling
```

---

# 🔴 Advanced

Then learn:

```text
36. Authentication
37. JWT
38. Interceptors
39. State Management
40. Signal Store Pattern
41. Advanced RxJS
42. Performance
43. Change Detection
44. OnPush
45. Dynamic Components
46. SSR
47. SSG
48. Hydration
49. Security
50. Testing
51. Architecture
52. Deployment
```

---

# 🧠 Angular Mental Model

The most important concept is understanding how the pieces connect.

```text
                    Angular
                       │
        ┌──────────────┼──────────────┐
        ↓              ↓              ↓
    Component        Service        Router
        │              │              │
        ↓              ↓              ↓
    Template         HTTP/API       Pages
        │              │
        ↓              ↓
     Signals         RxJS
        │              │
        └───────┬──────┘
                ↓
             State
                │
                ↓
             UI Update
```

---

# 🔥 Real Angular Application Flow

For example, when a user opens:

```text
/dashboard
```

The flow can be:

```text
Browser
   ↓
Angular Router
   ↓
Auth Guard
   ↓
Dashboard Component
   ↓
Dashboard Service
   ↓
HttpClient
   ↓
Interceptor
   ↓
Backend API
   ↓
JSON Response
   ↓
Observable
   ↓
Signal / State
   ↓
Angular Template
   ↓
User sees dashboard
```

---

# 🇰🇭 Explanation in Khmer

Angular Application មួយធម្មតាដំណើរការប្រហែលជា៖

```text
User
 ↓
Router
 ↓
Guard
 ↓
Component
 ↓
Service
 ↓
HttpClient
 ↓
Backend API
 ↓
Response
 ↓
Signal / RxJS
 ↓
Template
 ↓
UI
```

ឧទាហរណ៍ User ចូល៖

```text
/dashboard
```

Angular Router ពិនិត្យថា route នោះត្រូវបង្ហាញ Component មួយណា។

បន្ទាប់មក Guard ពិនិត្យ៖

```text
User Login ហើយឬនៅ?
```

បើ login ហើយ៖

```text
DashboardComponent
```

ត្រូវបានបង្ហាញ។

Component អាចប្រើ Service ដើម្បី request API៖

```typescript
this.dashboardService.getData();
```

Service ប្រើ HttpClient៖

```typescript
this.http.get('/api/dashboard');
```

Backend បញ្ជូន JSON ត្រឡប់មកវិញ៖

```json
{
  "sales": 5000,
  "orders": 120,
  "customers": 80
}
```

Angular បង្ហាញ data ទៅ UI។

---

# 🎯 What You Should Build

To become good at Angular, don't only read documentation.

Build projects.

## Project 1 — Beginner

### Todo App

Features:

```text
Add Todo
Delete Todo
Complete Todo
Filter Todo
```

Concepts:

```text
Component
Signal
Event Binding
@if
@for
```

---

## Project 2 — Intermediate

### User Management

Features:

```text
Login
Users
Create User
Edit User
Delete User
Search
Pagination
```

Concepts:

```text
Routing
Forms
Services
HTTP
CRUD
Signals
RxJS
Guards
```

---

## Project 3 — Advanced

### E-Commerce

Features:

```text
Authentication
Products
Categories
Cart
Orders
Customers
Payments
Dashboard
Reports
```

Concepts:

```text
Authentication
JWT
Interceptor
Guards
Lazy Loading
State Management
Signals
RxJS
HTTP
Forms
Performance
Testing
```

---

# 📌 Important Angular Commands

Create application:

```bash
ng new my-app
```

Start:

```bash
ng serve
```

Build:

```bash
ng build
```

Test:

```bash
ng test
```

Generate component:

```bash
ng g c components/user
```

Generate service:

```bash
ng g s services/user
```

Generate guard:

```bash
ng g guard guards/auth
```

Generate pipe:

```bash
ng g pipe pipes/currency
```

Generate directive:

```bash
ng g directive directives/highlight
```

Generate interface:

```bash
ng g interface models/user
```

Generate class:

```bash
ng g class models/product
```

---

# 📖 Important Concepts to Memorize

If you want to become an Angular developer, understand these deeply:

```text
TypeScript
   ↓
Components
   ↓
Templates
   ↓
Signals
   ↓
Services
   ↓
Dependency Injection
   ↓
Routing
   ↓
Forms
   ↓
HTTP
   ↓
RxJS
   ↓
Authentication
   ↓
State Management
   ↓
Performance
   ↓
Testing
   ↓
Architecture
```

---

# ✅ Final Checklist

## Beginner

* [ ] HTML
* [ ] CSS
* [ ] JavaScript
* [ ] TypeScript
* [ ] Angular CLI
* [ ] Components
* [ ] Templates
* [ ] Interpolation
* [ ] Property Binding
* [ ] Event Binding
* [ ] Two-Way Binding
* [ ] Control Flow
* [ ] Pipes
* [ ] Directives

## Intermediate

* [ ] Services
* [ ] Dependency Injection
* [ ] Signals
* [ ] Computed
* [ ] Effects
* [ ] Input
* [ ] Output
* [ ] Routing
* [ ] Guards
* [ ] Lazy Loading
* [ ] Forms
* [ ] Validation
* [ ] HTTP Client
* [ ] CRUD
* [ ] RxJS
* [ ] Error Handling

## Advanced

* [ ] Authentication
* [ ] JWT
* [ ] Interceptors
* [ ] State Management
* [ ] Advanced RxJS
* [ ] Change Detection
* [ ] OnPush
* [ ] Dynamic Components
* [ ] SSR
* [ ] SSG
* [ ] Hydration
* [ ] Security
* [ ] Testing
* [ ] Performance
* [ ] Architecture
* [ ] Deployment

---

# 🚀 Final Goal

After completing this roadmap, you should be able to build applications such as:

```text
                    Angular
                       │
       ┌───────────────┼────────────────┐
       ↓               ↓                ↓
      POS           E-Commerce       Dashboard
       │               │                │
       ├─ Products     ├─ Products      ├─ Charts
       ├─ Orders       ├─ Cart          ├─ Reports
       ├─ Tables       ├─ Orders        ├─ Users
       ├─ Customers    ├─ Payment       └─ Analytics
       └─ Reports      └─ Users
```

The goal is not only to memorize Angular syntax.

The goal is to understand:

```text
How components work
How data flows
How state changes
How APIs communicate
How authentication works
How routing works
How applications are structured
How to optimize performance
How to test applications
How to build production systems
```

---

# 📚 Official Angular Resources

* Angular Documentation: https://angular.dev/
* Angular Installation: https://angular.dev/installation
* Angular Components: https://angular.dev/guide/components
* Angular Signals: https://angular.dev/guide/signals
* Angular Routing: https://angular.dev/guide/routing
* Angular HTTP Client: https://angular.dev/guide/http
* Angular CLI: https://angular.dev/tools/cli

---

# ⭐ Conclusion

Angular is much larger than simply writing components.

A professional Angular developer should understand:

```text
TypeScript
+
Angular Components
+
Signals
+
Services
+
Dependency Injection
+
Routing
+
Forms
+
HTTP
+
RxJS
+
Authentication
+
State Management
+
Testing
+
Security
+
Performance
+
Architecture
```

Learn each topic individually, then combine them into real projects.

**Beginner → Build small apps**

**Intermediate → Build CRUD applications**

**Advanced → Build complete production applications**

**Professional → Focus on architecture, performance, security, testing, and maintainability.**

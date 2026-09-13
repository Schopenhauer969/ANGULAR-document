# Angular — Beginner to Advanced

> A complete Angular learning guide from beginner to advanced with practical examples.
> **English + Khmer explanations 🇬🇧 🇰🇭**

---

## 📚 Table of Contents

* [1. What is Angular?](#1-what-is-angular)
* [2. Why Angular?](#2-why-angular)
* [3. Requirements](#3-requirements)
* [4. Install Angular](#4-install-angular)
* [5. Create Your First Project](#5-create-your-first-project)
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
* [19. Services](#19-services)
* [20. Dependency Injection](#20-dependency-injection)
* [21. Routing](#21-routing)
* [22. Route Parameters](#22-route-parameters)
* [23. Query Parameters](#23-query-parameters)
* [24. Route Guards](#24-route-guards)
* [25. Lazy Loading](#25-lazy-loading)
* [26. Forms](#26-forms)
* [27. Reactive Forms](#27-reactive-forms)
* [28. Form Validation](#28-form-validation)
* [29. HttpClient](#29-httpclient)
* [30. HTTP Services](#30-http-services)
* [31. HTTP Interceptors](#31-http-interceptors)
* [32. Error Handling](#32-error-handling)
* [33. Custom Directives](#33-custom-directives)
* [34. Pipes](#34-pipes)
* [35. Custom Pipes](#35-custom-pipes)
* [36. Lifecycle](#36-lifecycle)
* [37. Content Projection](#37-content-projection)
* [38. View Queries](#38-view-queries)
* [39. RxJS](#39-rxjs)
* [40. Observable + HttpClient](#40-observable--httpclient)
* [41. Signal + Observable](#41-signal--observable)
* [42. State Management](#42-state-management)
* [43. Component Store Pattern](#43-component-store-pattern)
* [44. Authentication](#44-authentication)
* [45. JWT Authentication](#45-jwt-authentication)
* [46. Environment Configuration](#46-environment-configuration)
* [47. Standalone Architecture](#47-standalone-architecture)
* [48. Feature-Based Architecture](#48-feature-based-architecture)
* [49. Deferrable Views](#49-deferrable-views)
* [50. SSR / SSG](#50-ssr--ssg)
* [51. Performance](#51-performance)
* [52. Testing](#52-testing)
* [53. HTTP Testing](#53-http-testing)
* [54. Security](#54-security)
* [55. Production Build](#55-production-build)
* [56. Deployment](#56-deployment)
* [57. Best Practices](#57-best-practices)
* [58. Advanced Project Structure](#58-advanced-project-structure)
* [59. Complete CRUD Example](#59-complete-crud-example)
* [60. Learning Roadmap](#60-learning-roadmap)

---

# 1. What is Angular?

## English

Angular is a TypeScript-based web framework for building scalable web applications.

Angular provides:

* Components
* Signals
* Dependency Injection
* Routing
* Forms
* HTTP Client
* Testing tools
* Server-side rendering
* Static generation
* Hydration
* Lazy loading
* CLI tooling

Angular is maintained by Google.

## ខ្មែរ

Angular គឺជា web framework ដែលប្រើ **TypeScript** សម្រាប់បង្កើត web application ដែលមានទំហំធំ និងមានរចនាសម្ព័ន្ធច្បាស់លាស់។

Angular មាន៖

* Component
* Signal
* Dependency Injection
* Routing
* Form
* HTTP Client
* Testing
* SSR
* SSG
* Hydration
* Lazy Loading
* Angular CLI

---

# 2. Why Angular?

## English

Angular is useful when you want a structured framework for large applications.

Advantages:

```text
Angular
│
├── TypeScript
├── Components
├── Signals
├── Routing
├── Forms
├── HTTP
├── Dependency Injection
├── Testing
├── SSR
└── CLI
```

## ខ្មែរ

Angular សមស្របសម្រាប់ project ដែលត្រូវការ architecture ច្បាស់ និងអាចពង្រីកបាន។

ឧទាហរណ៍៖

* Admin dashboard
* E-commerce
* Banking applications
* Enterprise applications
* Management systems
* SaaS applications

---

# 3. Requirements

Angular requires Node.js.

Check Node.js:

```bash
node --version
```

Check npm:

```bash
npm --version
```

Install Angular CLI:

```bash
npm install -g @angular/cli
```

Angular's official setup documentation recommends using an active LTS or maintenance LTS Node.js release, and the CLI is installed through npm.

---

# 4. Install Angular

```bash
npm install -g @angular/cli
```

Check Angular:

```bash
ng version
```

You should see information similar to:

```text
Angular CLI
Node
Package Manager
OS
Angular
```

## Khmer

`ng` គឺជា Angular CLI command ដែលយើងប្រើសម្រាប់បង្កើត project និង generate code។

---

# 5. Create Your First Project

Create:

```bash
ng new angular-learning
```

Go inside:

```bash
cd angular-learning
```

Start development server:

```bash
ng serve
```

Or:

```bash
npm start
```

Open:

```text
http://localhost:4200
```

Angular CLI provides commands such as `new`, `generate`, `serve`, `build`, `test`, and `update`.

---

# 6. Angular Project Structure

A modern Angular project can look like:

```text
angular-learning/
│
├── src/
│   ├── app/
│   │   ├── app.component.ts
│   │   ├── app.component.html
│   │   ├── app.component.css
│   │   ├── app.config.ts
│   │   └── app.routes.ts
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

## Khmer

`src/app` គឺជាកន្លែងសំខាន់ដែលយើងសរសេរ Angular application។

---

# 7. Components

A component contains:

```text
Component
├── TypeScript
├── HTML
└── CSS
```

Create:

```bash
ng generate component users
```

Short version:

```bash
ng g c users
```

Example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-user',
  template: `
    <h1>Hello Angular</h1>
    <p>Welcome to Angular.</p>
  `,
})
export class UserComponent {}
```

## Khmer

Component គឺជា UI building block របស់ Angular។

---

# 8. Templates

Template គឺជា HTML ដែល Angular ប្រើដើម្បីបង្ហាញ UI។

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-home',
  template: `
    <h1>Home Page</h1>
    <p>Welcome!</p>
  `,
})
export class HomeComponent {}
```

---

# 9. Interpolation

Interpolation ប្រើ `{{ }}`។

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-profile',
  template: `
    <h1>{{ name }}</h1>
    <p>Age: {{ age }}</p>
  `,
})
export class ProfileComponent {
  name = 'Heng';
  age = 20;
}
```

Output:

```text
Heng
Age: 20
```

## Khmer

Interpolation គឺយក value ពី TypeScript ទៅបង្ហាញក្នុង HTML។

---

# 10. Property Binding

Use:

```html
[property]="value"
```

Example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-button',
  template: `
    <button [disabled]="isDisabled">
      Submit
    </button>
  `,
})
export class ButtonComponent {
  isDisabled = true;
}
```

---

# 11. Event Binding

Use:

```html
(event)="method()"
```

Example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-counter',
  template: `
    <button (click)="increment()">
      Count: {{ count }}
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

Event Binding ប្រើសម្រាប់ទទួល event ពី user ដូចជា:

* click
* input
* submit
* change
* keyup

---

# 12. Two-Way Binding

Two-way binding ប្រើ `[(ngModel)]`។

First import:

```typescript
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-form',
  imports: [FormsModule],
  template: `
    <input [(ngModel)]="name">

    <p>Hello {{ name }}</p>
  `,
})
export class FormComponent {
  name = '';
}
```

## Khmer

`[(ngModel)]` មានន័យថា data អាចទៅមករវាង input និង TypeScript។

---

# 13. Control Flow

Modern Angular supports built-in control flow syntax.

## @if

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-example',
  template: `
    @if (isLoggedIn) {
      <p>Welcome back!</p>
    } @else {
      <p>Please login.</p>
    }
  `,
})
export class ExampleComponent {
  isLoggedIn = true;
}
```

## @for

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-users',
  template: `
    <ul>
      @for (user of users; track user.id) {
        <li>{{ user.name }}</li>
      }
    </ul>
  `,
})
export class UsersComponent {
  users = [
    { id: 1, name: 'Dara' },
    { id: 2, name: 'Sokha' },
    { id: 3, name: 'Vanna' },
  ];
}
```

## @switch

```html
@switch (role) {
  @case ('admin') {
    <p>Administrator</p>
  }

  @case ('user') {
    <p>Normal User</p>
  }

  @default {
    <p>Unknown role</p>
  }
}
```

Angular's migration documentation describes built-in control flow as the modern replacement for older `*ngIf`, `*ngFor`, and `*ngSwitch` patterns.

---

# 14. Signals

Signals provide reactive state.

```typescript
import { Component, signal } from '@angular/core';

@Component({
  selector: 'app-counter',
  template: `
    <h1>{{ count() }}</h1>

    <button (click)="increment()">
      Increment
    </button>
  `,
})
export class CounterComponent {
  count = signal(0);

  increment(): void {
    this.count.update(value => value + 1);
  }
}
```

Important:

```typescript
count()
```

Read the signal.

```typescript
count.set(10);
```

Set a value.

```typescript
count.update(value => value + 1);
```

Update based on previous value.

## Khmer

Signal គឺជា reactive state របស់ Angular។

```text
Signal
  ↓
State changes
  ↓
Angular knows
  ↓
UI updates
```

Angular describes Signals as its fine-grained reactivity model.

---

# 15. Computed Signals

Use `computed()` for derived state.

```typescript
import {
  Component,
  signal,
  computed
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

  total = computed(() => {
    return this.price() * this.quantity();
  });
}
```

Result:

```text
Price: $10
Quantity: 3
Total: $30
```

---

# 16. Effects

`effect()` runs when signals it reads change.

```typescript
import {
  Component,
  effect,
  signal
} from '@angular/core';

@Component({
  selector: 'app-example',
  template: `
    <button (click)="changeName()">
      Change Name
    </button>
  `,
})
export class ExampleComponent {
  name = signal('Heng');

  constructor() {
    effect(() => {
      console.log('Name:', this.name());
    });
  }

  changeName(): void {
    this.name.set('Dara');
  }
}
```

## Important

Do not use effects for ordinary derived values.

Prefer:

```typescript
computed()
```

for derived state.

---

# 17. Inputs

Modern Angular supports signal inputs.

Parent:

```typescript
import { Component } from '@angular/core';
import { UserComponent } from './user.component';

@Component({
  selector: 'app-parent',
  imports: [UserComponent],
  template: `
    <app-user [name]="userName" />
  `,
})
export class ParentComponent {
  userName = 'Heng';
}
```

Child:

```typescript
import { Component, input } from '@angular/core';

@Component({
  selector: 'app-user',
  template: `
    <h2>{{ name() }}</h2>
  `,
})
export class UserComponent {
  name = input.required<string>();
}
```

---

# 18. Outputs

Child:

```typescript
import {
  Component,
  output
} from '@angular/core';

@Component({
  selector: 'app-button',
  template: `
    <button (click)="save()">
      Save
    </button>
  `,
})
export class ButtonComponent {
  saved = output<string>();

  save(): void {
    this.saved.emit('Saved successfully');
  }
}
```

Parent:

```typescript
@Component({
  selector: 'app-parent',
  imports: [ButtonComponent],
  template: `
    <app-button
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

---

# 19. Services

Create:

```bash
ng generate service services/user
```

Example:

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class UserService {

  getUsers(): string[] {
    return [
      'Dara',
      'Sokha',
      'Vanna',
    ];
  }
}
```

Component:

```typescript
import { Component, inject } from '@angular/core';
import { UserService } from './services/user.service';

@Component({
  selector: 'app-users',
  template: `
    @for (user of users; track user) {
      <p>{{ user }}</p>
    }
  `,
})
export class UsersComponent {

  private userService = inject(UserService);

  users = this.userService.getUsers();
}
```

---

# 20. Dependency Injection

Angular has built-in Dependency Injection.

```typescript
import { Injectable } from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class LoggerService {

  log(message: string): void {
    console.log(`[LOG] ${message}`);
  }
}
```

Use:

```typescript
import { Component, inject } from '@angular/core';
import { LoggerService } from './logger.service';

@Component({
  selector: 'app-home',
  template: `<button (click)="run()">Run</button>`,
})
export class HomeComponent {

  private logger = inject(LoggerService);

  run(): void {
    this.logger.log('Button clicked');
  }
}
```

## Khmer

Dependency Injection ជួយឱ្យ component មិនចាំបាច់បង្កើត service ដោយខ្លួនឯង។

---

# 21. Routing

Angular Router manages navigation in Angular applications.

`app.routes.ts`:

```typescript
import { Routes } from '@angular/router';

export const routes: Routes = [
  {
    path: '',
    title: 'Home',
    loadComponent: () =>
      import('./pages/home/home.component')
        .then(m => m.HomeComponent),
  },

  {
    path: 'about',
    title: 'About',
    loadComponent: () =>
      import('./pages/about/about.component')
        .then(m => m.AboutComponent),
  },

  {
    path: '**',
    redirectTo: '',
  },
];
```

`app.config.ts`:

```typescript
import {
  ApplicationConfig
} from '@angular/core';

import {
  provideRouter
} from '@angular/router';

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

# 22. Route Parameters

Routes:

```typescript
export const routes: Routes = [
  {
    path: 'users/:id',
    loadComponent: () =>
      import('./pages/user/user.component')
        .then(m => m.UserComponent),
  },
];
```

Component:

```typescript
import {
  Component,
  inject
} from '@angular/core';

import {
  ActivatedRoute
} from '@angular/router';

@Component({
  selector: 'app-user',
  template: `
    <h1>User ID: {{ userId }}</h1>
  `,
})
export class UserComponent {

  private route = inject(ActivatedRoute);

  userId =
    this.route.snapshot.paramMap.get('id');
}
```

URL:

```text
/users/123
```

Result:

```text
User ID: 123
```

---

# 23. Query Parameters

Navigate:

```typescript
import {
  Router
} from '@angular/router';

import {
  Component,
  inject
} from '@angular/core';

@Component({
  selector: 'app-search',
  template: `
    <button (click)="search()">
      Search
    </button>
  `,
})
export class SearchComponent {

  private router = inject(Router);

  search(): void {
    this.router.navigate(
      ['/products'],
      {
        queryParams: {
          search: 'phone',
          page: 1,
        },
      }
    );
  }
}
```

URL:

```text
/products?search=phone&page=1
```

---

# 24. Route Guards

Create guard:

```bash
ng generate guard guards/auth
```

Example functional guard:

```typescript
import {
  inject
} from '@angular/core';

import {
  CanActivateFn,
  Router
} from '@angular/router';

export const authGuard: CanActivateFn = () => {

  const router = inject(Router);

  const isLoggedIn = localStorage.getItem(
    'token'
  );

  if (isLoggedIn) {
    return true;
  }

  return router.createUrlTree(['/login']);
};
```

Use:

```typescript
export const routes: Routes = [
  {
    path: 'dashboard',
    canActivate: [authGuard],
    loadComponent: () =>
      import('./pages/dashboard/dashboard.component')
        .then(m => m.DashboardComponent),
  },
];
```

## Khmer

Guard គឺប្រើដើម្បីការពារ route។

ឧទាហរណ៍:

```text
User
 ↓
/dashboard
 ↓
Auth Guard
 ↓
Logged in?
 ├── Yes → Dashboard
 └── No  → Login
```

---

# 25. Lazy Loading

Lazy loading means loading code only when needed.

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

For feature routes:

```typescript
export const routes: Routes = [
  {
    path: 'products',
    loadChildren: () =>
      import('./features/products/products.routes')
        .then(m => m.PRODUCT_ROUTES),
  },
];
```

Benefits:

* Smaller initial bundle
* Faster startup
* Better scalability

---

# 26. Forms

Angular supports template-driven and reactive forms.

Simple form:

```typescript
import {
  Component
} from '@angular/core';

import {
  FormsModule
} from '@angular/forms';

@Component({
  selector: 'app-login',
  imports: [FormsModule],
  template: `
    <form #form="ngForm"
          (ngSubmit)="submit(form)">

      <input
        name="email"
        ngModel
        placeholder="Email"
      />

      <input
        name="password"
        type="password"
        ngModel
        placeholder="Password"
      />

      <button type="submit">
        Login
      </button>

    </form>
  `,
})
export class LoginComponent {

  submit(form: any): void {
    console.log(form.value);
  }
}
```

---

# 27. Reactive Forms

Reactive forms are useful for complex forms.

```typescript
import {
  Component,
  inject
} from '@angular/core';

import {
  FormBuilder,
  ReactiveFormsModule
} from '@angular/forms';

@Component({
  selector: 'app-register',
  imports: [ReactiveFormsModule],
  template: `
    <form
      [formGroup]="form"
      (ngSubmit)="submit()"
    >

      <input
        formControlName="name"
        placeholder="Name"
      />

      <input
        formControlName="email"
        placeholder="Email"
      />

      <button type="submit">
        Register
      </button>

    </form>
  `,
})
export class RegisterComponent {

  private fb = inject(FormBuilder);

  form = this.fb.nonNullable.group({
    name: '',
    email: '',
  });

  submit(): void {
    console.log(this.form.getRawValue());
  }
}
```

---

# 28. Form Validation

```typescript
import {
  Component,
  inject
} from '@angular/core';

import {
  FormBuilder,
  ReactiveFormsModule,
  Validators
} from '@angular/forms';

@Component({
  selector: 'app-register',
  imports: [ReactiveFormsModule],
  template: `
    <form
      [formGroup]="form"
      (ngSubmit)="submit()"
    >

      <input
        formControlName="email"
        placeholder="Email"
      />

      @if (
        form.controls.email.touched &&
        form.controls.email.invalid
      ) {
        <p>Email is required and must be valid.</p>
      }

      <button
        type="submit"
        [disabled]="form.invalid"
      >
        Submit
      </button>

    </form>
  `,
})
export class RegisterComponent {

  private fb = inject(FormBuilder);

  form = this.fb.nonNullable.group({
    email: [
      '',
      [
        Validators.required,
        Validators.email,
      ],
    ],
  });

  submit(): void {
    if (this.form.invalid) {
      return;
    }

    console.log(this.form.getRawValue());
  }
}
```

---

# 29. HttpClient

Configure HttpClient:

```typescript
import {
  ApplicationConfig
} from '@angular/core';

import {
  provideHttpClient
} from '@angular/common/http';

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient(),
  ],
};
```

Component/service can then inject `HttpClient`.

---

# 30. HTTP Services

Create:

```bash
ng generate service services/product
```

Example:

```typescript
import {
  Injectable,
  inject
} from '@angular/core';

import {
  HttpClient
} from '@angular/common/http';

import {
  Observable
} from 'rxjs';

export interface Product {
  id: number;
  title: string;
  price: number;
}

@Injectable({
  providedIn: 'root',
})
export class ProductService {

  private http = inject(HttpClient);

  private apiUrl =
    'https://api.example.com/products';

  getProducts(): Observable<Product[]> {
    return this.http.get<Product[]>(
      this.apiUrl
    );
  }

  getProduct(
    id: number
  ): Observable<Product> {
    return this.http.get<Product>(
      `${this.apiUrl}/${id}`
    );
  }

  createProduct(
    product: Omit<Product, 'id'>
  ): Observable<Product> {
    return this.http.post<Product>(
      this.apiUrl,
      product
    );
  }

  updateProduct(
    id: number,
    product: Partial<Product>
  ): Observable<Product> {
    return this.http.patch<Product>(
      `${this.apiUrl}/${id}`,
      product
    );
  }

  deleteProduct(
    id: number
  ): Observable<void> {
    return this.http.delete<void>(
      `${this.apiUrl}/${id}`
    );
  }
}
```

---

# 31. HTTP Interceptors

Interceptors are useful for:

* Authentication
* Headers
* Logging
* Error handling
* Loading indicators

Example:

```typescript
import {
  HttpInterceptorFn
} from '@angular/common/http';

export const authInterceptor:
  HttpInterceptorFn = (req, next) => {

  const token =
    localStorage.getItem('token');

  if (!token) {
    return next(req);
  }

  const authReq = req.clone({
    setHeaders: {
      Authorization: `Bearer ${token}`,
    },
  });

  return next(authReq);
};
```

Register:

```typescript
import {
  provideHttpClient,
  withInterceptors
} from '@angular/common/http';

import {
  authInterceptor
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

---

# 32. Error Handling

Using RxJS:

```typescript
import {
  catchError,
  throwError
} from 'rxjs';

getProducts(): Observable<Product[]> {
  return this.http
    .get<Product[]>(this.apiUrl)
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

Component:

```typescript
this.productService
  .getProducts()
  .subscribe({
    next: products => {
      console.log(products);
    },

    error: error => {
      console.error(error);
    },
  });
```

---

# 33. Custom Directives

Create:

```bash
ng generate directive directives/highlight
```

Example:

```typescript
import {
  Directive,
  ElementRef,
  HostListener
} from '@angular/core';

@Directive({
  selector: '[appHighlight]',
})
export class HighlightDirective {

  constructor(
    private element: ElementRef
  ) {}

  @HostListener('mouseenter')
  onMouseEnter(): void {
    this.element.nativeElement.style.backgroundColor =
      'yellow';
  }

  @HostListener('mouseleave')
  onMouseLeave(): void {
    this.element.nativeElement.style.backgroundColor =
      '';
  }
}
```

Use:

```html
<p appHighlight>
  Hover over me
</p>
```

---

# 34. Pipes

Built-in pipes:

```html
<p>{{ name | uppercase }}</p>

<p>{{ name | lowercase }}</p>

<p>{{ price | currency }}</p>

<p>{{ today | date }}</p>
```

Example:

```typescript
import {
  Component
} from '@angular/core';

import {
  CurrencyPipe,
  DatePipe,
  UpperCasePipe
} from '@angular/common';

@Component({
  selector: 'app-example',
  imports: [
    CurrencyPipe,
    DatePipe,
    UpperCasePipe,
  ],
  template: `
    <p>{{ name | uppercase }}</p>
    <p>{{ price | currency }}</p>
    <p>{{ today | date }}</p>
  `,
})
export class ExampleComponent {

  name = 'angular';

  price = 100;

  today = new Date();
}
```

---

# 35. Custom Pipes

Create:

```bash
ng generate pipe pipes/truncate
```

Example:

```typescript
import {
  Pipe,
  PipeTransform
} from '@angular/core';

@Pipe({
  name: 'truncate',
})
export class TruncatePipe
  implements PipeTransform {

  transform(
    value: string,
    length = 20
  ): string {

    if (value.length <= length) {
      return value;
    }

    return value.slice(0, length) + '...';
  }
}
```

Use:

```html
<p>
  {{ description | truncate:30 }}
</p>
```

---

# 36. Lifecycle

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
  OnDestroy
} from '@angular/core';

@Component({
  selector: 'app-example',
  template: `<h1>Hello</h1>`,
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

# 37. Content Projection

Use `<ng-content>`.

Child:

```typescript
import {
  Component
} from '@angular/core';

@Component({
  selector: 'app-card',
  template: `
    <div class="card">
      <ng-content />
    </div>
  `,
})
export class CardComponent {}
```

Parent:

```html
<app-card>
  <h2>Product</h2>
  <p>This is a product.</p>
</app-card>
```

---

# 38. View Queries

Modern Angular provides query APIs such as `viewChild`.

Example:

```typescript
import {
  Component,
  ElementRef,
  viewChild
} from '@angular/core';

@Component({
  selector: 'app-example',
  template: `
    <input #nameInput>

    <button (click)="focus()">
      Focus
    </button>
  `,
})
export class ExampleComponent {

  nameInput =
    viewChild.required<ElementRef>('nameInput');

  focus(): void {
    this.nameInput()
      .nativeElement
      .focus();
  }
}
```

---

# 39. RxJS

Angular uses RxJS extensively for asynchronous streams.

Example:

```typescript
import {
  Observable,
  interval
} from 'rxjs';

const counter$: Observable<number> =
  interval(1000);
```

Subscribe:

```typescript
const subscription =
  counter$.subscribe(value => {
    console.log(value);
  });
```

Always clean up subscriptions when needed.

---

# 40. Observable + HttpClient

```typescript
import {
  Component,
  inject
} from '@angular/core';

import {
  ProductService
} from './product.service';

@Component({
  selector: 'app-products',
  template: `
    @for (
      product of products;
      track product.id
    ) {
      <p>
        {{ product.title }}
      </p>
    }
  `,
})
export class ProductsComponent {

  private service =
    inject(ProductService);

  products: Product[] = [];

  ngOnInit(): void {
    this.service
      .getProducts()
      .subscribe(products => {
        this.products = products;
      });
  }
}
```

---

# 41. Signal + Observable

Angular provides interop between Signals and RxJS.

Example:

```typescript
import {
  Component
} from '@angular/core';

import {
  toSignal
} from '@angular/core/rxjs-interop';

import {
  interval
} from 'rxjs';

@Component({
  selector: 'app-counter',
  template: `
    <p>{{ counter() }}</p>
  `,
})
export class CounterComponent {

  counter = toSignal(
    interval(1000),
    {
      initialValue: 0,
    }
  );
}
```

Now:

```typescript
counter()
```

is a signal.

---

# 42. State Management

For small applications, Signals can provide simple state management.

Example:

```typescript
import {
  Injectable,
  signal,
  computed
} from '@angular/core';

export interface User {
  id: number;
  name: string;
}

@Injectable({
  providedIn: 'root',
})
export class UserState {

  private users =
    signal<User[]>([]);

  readonly userList =
    this.users.asReadonly();

  readonly userCount =
    computed(() => this.users().length);

  setUsers(users: User[]): void {
    this.users.set(users);
  }

  addUser(user: User): void {
    this.users.update(users => [
      ...users,
      user,
    ]);
  }

  removeUser(id: number): void {
    this.users.update(users =>
      users.filter(user => user.id !== id)
    );
  }
}
```

---

# 43. Component Store Pattern

For a larger application, separate:

```text
UI
 ↓
Component
 ↓
State
 ↓
Service
 ↓
API
```

Example:

```text
products/
├── data-access/
│   ├── product.service.ts
│   └── product.state.ts
│
├── pages/
│   ├── product-list/
│   └── product-detail/
│
└── ui/
    ├── product-card/
    └── product-table/
```

This makes applications easier to maintain.

---

# 44. Authentication

A basic authentication architecture:

```text
Login Page
    ↓
Auth Service
    ↓
POST /login
    ↓
Backend
    ↓
JWT
    ↓
Store token
    ↓
Interceptor
    ↓
Authorization Header
    ↓
Protected API
```

Auth service:

```typescript
import {
  Injectable,
  signal
} from '@angular/core';

@Injectable({
  providedIn: 'root',
})
export class AuthService {

  private token =
    signal<string | null>(
      localStorage.getItem('token')
    );

  isAuthenticated(): boolean {
    return !!this.token();
  }

  login(token: string): void {
    localStorage.setItem(
      'token',
      token
    );

    this.token.set(token);
  }

  logout(): void {
    localStorage.removeItem('token');

    this.token.set(null);
  }

  getToken(): string | null {
    return this.token();
  }
}
```

> For production authentication, carefully consider token storage and browser security. Do not blindly store sensitive credentials in browser storage.

---

# 45. JWT Authentication

Login:

```typescript
login(
  email: string,
  password: string
) {
  return this.http.post<{
    accessToken: string;
  }>(
    '/api/auth/login',
    {
      email,
      password,
    }
  );
}
```

Then:

```typescript
this.authService
  .login(email, password)
  .subscribe(response => {
    this.authService.login(
      response.accessToken
    );
  });
```

Interceptor:

```typescript
export const authInterceptor:
  HttpInterceptorFn = (req, next) => {

  const token =
    inject(AuthService).getToken();

  if (!token) {
    return next(req);
  }

  return next(
    req.clone({
      setHeaders: {
        Authorization:
          `Bearer ${token}`,
      },
    })
  );
};
```

---

# 46. Environment Configuration

Example:

```text
src/
├── environments/
│   ├── environment.ts
│   └── environment.development.ts
```

`environment.ts`:

```typescript
export const environment = {
  production: true,
  apiUrl: 'https://api.example.com',
};
```

Development:

```typescript
export const environment = {
  production: false,
  apiUrl: 'http://localhost:3000',
};
```

Use:

```typescript
import {
  environment
} from '../environments/environment';

console.log(environment.apiUrl);
```

> Never put real passwords, private keys, database credentials, or other secrets into frontend environment files. Frontend values are ultimately delivered to the browser.

---

# 47. Standalone Architecture

Modern Angular applications commonly use standalone components.

Example:

```typescript
import {
  Component
} from '@angular/core';

@Component({
  selector: 'app-home',
  standalone: true,
  template: `
    <h1>Hello Angular</h1>
  `,
})
export class HomeComponent {}
```

A standalone component can directly import its template dependencies.

Modern applications generally do not need to create a large `NgModule` hierarchy.

---

# 48. Feature-Based Architecture

Recommended structure:

```text
src/app/
│
├── core/
│   ├── auth/
│   ├── guards/
│   ├── interceptors/
│   └── services/
│
├── shared/
│   ├── components/
│   ├── directives/
│   └── pipes/
│
├── features/
│   ├── auth/
│   │   ├── pages/
│   │   ├── services/
│   │   └── auth.routes.ts
│   │
│   ├── products/
│   │   ├── pages/
│   │   ├── components/
│   │   ├── services/
│   │   ├── models/
│   │   └── products.routes.ts
│   │
│   └── orders/
│       ├── pages/
│       ├── components/
│       ├── services/
│       └── orders.routes.ts
│
├── app.component.ts
├── app.config.ts
└── app.routes.ts
```

## Khmer

Feature-based architecture គឺរៀបចំ code តាម business feature ជំនួសឱ្យរៀបចំតាម file type តែប៉ុណ្ណោះ។

---

# 49. Deferrable Views

Angular supports `@defer` for deferring parts of a template.

```html
@defer {
  <app-heavy-chart />
} @placeholder {
  <p>Loading chart...</p>
} @loading {
  <p>Loading...</p>
}
```

This can help delay expensive UI until it is needed.

Angular's current documentation lists deferrable views as a performance feature for lazy-loading parts of templates.

---

# 50. SSR / SSG

Angular supports:

```text
CSR
SSR
SSG / Prerender
Hydration
Hybrid Rendering
```

Create an SSR project:

```bash
ng new my-app --ssr
```

Or add SSR:

```bash
ng add @angular/ssr
```

Angular's current SSR documentation describes CSR, SSR, and prerendering as selectable rendering modes in hybrid applications.

---

# 51. Performance

Important performance techniques:

## 1. Lazy loading

```typescript
{
  path: 'admin',
  loadChildren: () =>
    import('./admin/admin.routes')
      .then(m => m.ADMIN_ROUTES)
}
```

## 2. Signals

```typescript
count = signal(0);
```

## 3. Computed state

```typescript
total = computed(
  () => this.price() * this.quantity()
);
```

## 4. Track items

```html
@for (user of users; track user.id) {
  <p>{{ user.name }}</p>
}
```

## 5. Deferrable views

```html
@defer {
  <app-chart />
}
```

## 6. Avoid unnecessary work

Bad:

```typescript
getTotal(): number {
  return this.price * this.quantity;
}
```

Prefer derived state when appropriate:

```typescript
total = computed(
  () => this.price() * this.quantity()
);
```

---

# 52. Testing

Angular projects include testing support.

Run:

```bash
ng test
```

A simple test:

```typescript
import {
  TestBed
} from '@angular/core/testing';

describe('Calculator', () => {

  it('should add numbers', () => {

    const result = 2 + 3;

    expect(result).toBe(5);
  });

});
```

---

# 53. HTTP Testing

Angular provides HTTP testing utilities for mocking HTTP requests.

Example:

```typescript
import {
  TestBed
} from '@angular/core/testing';

import {
  provideHttpClient
} from '@angular/common/http';

import {
  provideHttpClientTesting,
  HttpTestingController
} from '@angular/common/http/testing';

describe('ProductService', () => {

  let httpTesting:
    HttpTestingController;

  beforeEach(() => {

    TestBed.configureTestingModule({
      providers: [
        provideHttpClient(),
        provideHttpClientTesting(),
      ],
    });

    httpTesting =
      TestBed.inject(
        HttpTestingController
      );
  });

  afterEach(() => {
    httpTesting.verify();
  });

});
```

Important:

```typescript
provideHttpClient()
```

should come before:

```typescript
provideHttpClientTesting()
```

when both are needed.

---

# 54. Security

Important Angular security rules:

## Never trust user input

Bad:

```typescript
element.innerHTML = userInput;
```

Avoid bypassing Angular security without a strong reason.

Be careful with:

```typescript
DomSanitizer
```

Never put secrets in:

```text
environment.ts
localStorage
frontend source code
```

Use HTTPS.

Validate data on the backend too.

Use authentication and authorization on the server.

## Khmer

Frontend security មិនអាចជំនួស backend security បានទេ។

Backend ត្រូវ validate:

```text
Authentication
Authorization
Validation
Rate limiting
Database permissions
```

---

# 55. Production Build

Build:

```bash
ng build
```

Production configuration:

```bash
ng build --configuration production
```

Output normally goes into:

```text
dist/
```

Preview with an appropriate static server or deployment platform.

---

# 56. Deployment

Angular can be deployed to many hosting platforms.

Common options:

```text
Vercel
Netlify
Firebase Hosting
Cloudflare Pages
AWS
Azure
Google Cloud
Nginx
Docker
```

Typical workflow:

```bash
npm install
ng build
```

Then deploy the generated production output according to your hosting configuration.

For SSR/hybrid applications, deployment differs because a server runtime may be required depending on the rendering configuration.

---

# 57. Best Practices

## Naming

Good:

```text
user-profile.component.ts
product.service.ts
auth.guard.ts
auth.interceptor.ts
```

Avoid:

```text
abc.ts
test2.ts
newfile.ts
```

---

## Components

Keep components focused.

Bad:

```text
Component
 ├── API
 ├── Database logic
 ├── Authentication
 ├── 1000 lines UI
 └── Business logic
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

## Services

Use services for shared business/data logic.

```typescript
@Injectable({
  providedIn: 'root',
})
export class ProductService {}
```

---

## Signals

Use Signals for local and simple reactive state.

```typescript
users = signal<User[]>([]);
```

Use:

```typescript
computed()
```

for derived state.

---

## Routing

Prefer lazy loading for large features.

```typescript
loadChildren
loadComponent
```

---

## HTTP

Keep API calls in services.

Good:

```text
Component
   ↓
ProductService
   ↓
HttpClient
   ↓
API
```

Avoid:

```text
Component
   ↓
Many HTTP calls
```

---

# 58. Advanced Project Structure

For a large enterprise application:

```text
src/
└── app/
    │
    ├── core/
    │   ├── auth/
    │   ├── guards/
    │   ├── interceptors/
    │   ├── services/
    │   └── layout/
    │
    ├── shared/
    │   ├── ui/
    │   ├── directives/
    │   ├── pipes/
    │   └── utils/
    │
    ├── features/
    │   │
    │   ├── dashboard/
    │   │   ├── components/
    │   │   ├── pages/
    │   │   ├── services/
    │   │   ├── models/
    │   │   └── dashboard.routes.ts
    │   │
    │   ├── users/
    │   │   ├── components/
    │   │   ├── pages/
    │   │   ├── services/
    │   │   ├── models/
    │   │   └── users.routes.ts
    │   │
    │   ├── products/
    │   │   ├── components/
    │   │   ├── pages/
    │   │   ├── services/
    │   │   ├── models/
    │   │   └── products.routes.ts
    │   │
    │   └── orders/
    │       ├── components/
    │       ├── pages/
    │       ├── services/
    │       ├── models/
    │       └── orders.routes.ts
    │
    ├── app.component.ts
    ├── app.config.ts
    └── app.routes.ts
```

---

# 59. Complete CRUD Example

Let's create a simple Product CRUD architecture.

## Model

```typescript
export interface Product {
  id: number;
  name: string;
  price: number;
}
```

---

## Service

```typescript
import {
  Injectable,
  inject
} from '@angular/core';

import {
  HttpClient
} from '@angular/common/http';

import {
  Observable
} from 'rxjs';

import {
  Product
} from '../models/product';

@Injectable({
  providedIn: 'root',
})
export class ProductService {

  private http =
    inject(HttpClient);

  private apiUrl =
    'http://localhost:3000/products';

  getAll(): Observable<Product[]> {
    return this.http.get<Product[]>(
      this.apiUrl
    );
  }

  getById(
    id: number
  ): Observable<Product> {

    return this.http.get<Product>(
      `${this.apiUrl}/${id}`
    );
  }

  create(
    product: Omit<Product, 'id'>
  ): Observable<Product> {

    return this.http.post<Product>(
      this.apiUrl,
      product
    );
  }

  update(
    id: number,
    product: Partial<Product>
  ): Observable<Product> {

    return this.http.patch<Product>(
      `${this.apiUrl}/${id}`,
      product
    );
  }

  delete(
    id: number
  ): Observable<void> {

    return this.http.delete<void>(
      `${this.apiUrl}/${id}`
    );
  }
}
```

---

## List Component

```typescript
import {
  Component,
  inject,
  signal
} from '@angular/core';

import {
  Product
} from '../../models/product';

import {
  ProductService
} from '../../services/product.service';

@Component({
  selector: 'app-product-list',
  template: `

    <h1>Products</h1>

    @if (loading()) {
      <p>Loading...</p>
    }

    @if (error()) {
      <p>{{ error() }}</p>
    }

    <ul>
      @for (
        product of products();
        track product.id
      ) {

        <li>
          <strong>
            {{ product.name }}
          </strong>

          -

          ${{ product.price }}

          <button
            (click)="deleteProduct(product.id)"
          >
            Delete
          </button>
        </li>
      }
    </ul>

  `,
})
export class ProductListComponent {

  private productService =
    inject(ProductService);

  products =
    signal<Product[]>([]);

  loading =
    signal(false);

  error =
    signal<string | null>(null);

  constructor() {
    this.loadProducts();
  }

  loadProducts(): void {

    this.loading.set(true);

    this.productService
      .getAll()
      .subscribe({

        next: products => {
          this.products.set(products);
          this.loading.set(false);
        },

        error: () => {
          this.error.set(
            'Failed to load products.'
          );

          this.loading.set(false);
        },

      });
  }

  deleteProduct(id: number): void {

    this.productService
      .delete(id)
      .subscribe({
        next: () => {
          this.products.update(
            products =>
              products.filter(
                product =>
                  product.id !== id
              )
          );
        },

        error: () => {
          this.error.set(
            'Failed to delete product.'
          );
        },
      });
  }
}
```

---

# 60. Learning Roadmap

## Beginner

Learn these first:

```text
1. TypeScript
2. Angular CLI
3. Components
4. Templates
5. Interpolation
6. Property Binding
7. Event Binding
8. Forms
9. Services
10. Dependency Injection
```

---

## Intermediate

Then learn:

```text
11. Signals
12. Computed
13. Effects
14. Inputs
15. Outputs
16. Routing
17. Route Parameters
18. Guards
19. Lazy Loading
20. Reactive Forms
21. HttpClient
22. RxJS
23. Pipes
24. Directives
```

---

## Advanced

Then:

```text
25. State Management
26. Interceptors
27. Authentication
28. JWT
29. Advanced Routing
30. Feature Architecture
31. Deferrable Views
32. SSR
33. SSG
34. Hydration
35. Performance
36. Testing
37. Security
38. CI/CD
39. Docker
40. Production Deployment
```

---

# Angular Mental Model

The most important concept is understanding how the pieces connect:

```text
                    ANGULAR APPLICATION
                           │
                           ▼
                     Components
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
          Template       Signal       Events
             │             │             │
             └─────────────┼─────────────┘
                           ▼
                       Services
                           │
                           ▼
                     HttpClient
                           │
                           ▼
                          API
                           │
                           ▼
                       Database
```

For routing:

```text
Browser URL
     │
     ▼
Angular Router
     │
     ▼
Route
     │
     ▼
Component
     │
     ▼
Template
```

For authentication:

```text
Login
  │
  ▼
Auth Service
  │
  ▼
Backend
  │
  ▼
Access Token
  │
  ▼
Interceptor
  │
  ▼
Protected API
```

For application state:

```text
User Action
    │
    ▼
Signal
    │
    ▼
Computed State
    │
    ▼
Component
    │
    ▼
UI
```

---

# Useful Angular CLI Commands

Create project:

```bash
ng new my-app
```

Start server:

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
ng generate component users
```

Short:

```bash
ng g c users
```

Generate service:

```bash
ng generate service services/user
```

Generate directive:

```bash
ng generate directive directives/highlight
```

Generate pipe:

```bash
ng generate pipe pipes/truncate
```

Generate guard:

```bash
ng generate guard guards/auth
```

Add package/library:

```bash
ng add <package>
```

Update Angular:

```bash
ng update
```

Show version:

```bash
ng version
```

---

# Recommended Learning Order

```text
TypeScript
    ↓
Angular CLI
    ↓
Components
    ↓
Templates
    ↓
Bindings
    ↓
Control Flow
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
HttpClient
    ↓
RxJS
    ↓
Authentication
    ↓
Guards + Interceptors
    ↓
State Management
    ↓
Lazy Loading
    ↓
Testing
    ↓
Performance
    ↓
SSR / SSG
    ↓
Production
```

---

# Final Angular Checklist

Before calling yourself comfortable with Angular, you should be able to build:

* [ ] Login page
* [ ] Register page
* [ ] Dashboard
* [ ] Sidebar
* [ ] Navbar
* [ ] CRUD
* [ ] Search
* [ ] Pagination
* [ ] Sorting
* [ ] Filtering
* [ ] Reactive forms
* [ ] Validation
* [ ] API integration
* [ ] Authentication
* [ ] JWT
* [ ] Route guards
* [ ] HTTP interceptor
* [ ] Error handling
* [ ] Loading states
* [ ] Signals
* [ ] RxJS
* [ ] Lazy loading
* [ ] Unit tests
* [ ] HTTP tests
* [ ] Production build
* [ ] Deployment
* [ ] SSR/SSG where appropriate

---

# Official Angular Resources

* Angular Documentation: https://angular.dev/
* Angular CLI: https://angular.dev/cli
* Angular Tutorial: https://angular.dev/tutorials
* Angular Components: https://angular.dev/guide/components
* Angular Signals: https://angular.dev/guide/signals
* Angular Routing: https://angular.dev/guide/routing
* Angular Forms: https://angular.dev/guide/forms
* Angular HTTP: https://angular.dev/guide/http
* Angular Testing: https://angular.dev/guide/testing

---

# Conclusion

Angular is more than a UI library. It is a complete web application framework.

The most important concepts to master are:

```text
Components
     +
Templates
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
HttpClient
     +
RxJS
     +
Authentication
     +
Testing
     +
Performance
     +
SSR
```

Start small.

Build projects.

Do not try to memorize every Angular API.

Instead, understand how the pieces work together:

```text
Component
   ↓
State
   ↓
Service
   ↓
API
   ↓
Database
```

Once you understand this architecture, you can build small Angular applications and gradually scale them into large production systems.

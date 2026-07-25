# Angular — Writing Data, Beginner to Advanced

A complete, practical guide to **writing data in Angular** — from your first `HttpClient.post()` call to production-grade reactive forms, optimistic updates, interceptors, and error handling.

Examples target **Angular 17+** with standalone components and TypeScript.

```bash
npm install -g @angular/cli
ng new my-app --standalone
cd my-app
```

---

## Table of Contents

1. [Setup](#1-setup)
2. [Beginner: HttpClient POST Requests](#2-beginner-httpclient-post-requests)
3. [Beginner: A Basic Write Service](#3-beginner-a-basic-write-service)
4. [Beginner: Template-Driven Forms](#4-beginner-template-driven-forms)
5. [Intermediate: Reactive Forms](#5-intermediate-reactive-forms)
6. [Intermediate: Form Validation](#6-intermediate-form-validation)
7. [Intermediate: PUT, PATCH & DELETE](#7-intermediate-put-patch--delete)
8. [Intermediate: Dynamic Form Arrays](#8-intermediate-dynamic-form-arrays)
9. [Advanced: Optimistic Updates with Signals](#9-advanced-optimistic-updates-with-signals)
10. [Advanced: HTTP Interceptors for Writes](#10-advanced-http-interceptors-for-writes)
11. [Advanced: File Uploads](#11-advanced-file-uploads)
12. [Advanced: State Management Writes (NgRx)](#12-advanced-state-management-writes-ngrx)
13. [Advanced: Error Handling Patterns](#13-advanced-error-handling-patterns)
14. [Advanced: Testing Writes](#14-advanced-testing-writes)
15. [Best Practices Cheat Sheet](#15-best-practices-cheat-sheet)

---

## 1. Setup

```typescript
// app.config.ts
import { ApplicationConfig } from "@angular/core";
import { provideHttpClient, withInterceptors } from "@angular/common/http";
import { authInterceptor } from "./interceptors/auth.interceptor";

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient(withInterceptors([authInterceptor]))
  ]
};
```

```typescript
// models/post.model.ts
export interface Post {
  id?: number;
  title: string;
  body: string;
  published: boolean;
}
```

---

## 2. Beginner: HttpClient POST Requests

```typescript
// services/post.service.ts
import { Injectable, inject } from "@angular/core";
import { HttpClient } from "@angular/common/http";
import { Observable } from "rxjs";
import { Post } from "../models/post.model";

@Injectable({ providedIn: "root" })
export class PostService {
  private http = inject(HttpClient);
  private apiUrl = "https://api.example.com/posts";

  createPost(post: Post): Observable<Post> {
    return this.http.post<Post>(this.apiUrl, post);
  }
}
```

### Calling it from a Component

```typescript
// components/create-post/create-post.component.ts
import { Component, inject } from "@angular/core";
import { PostService } from "../../services/post.service";

@Component({
  selector: "app-create-post",
  standalone: true,
  template: `<button (click)="createPost()">Create Post</button>`
})
export class CreatePostComponent {
  private postService = inject(PostService);

  createPost() {
    this.postService.createPost({
      title: "Hello World",
      body: "My first post",
      published: false
    }).subscribe({
      next: (post) => console.log("Created post:", post),
      error: (err) => console.error("Failed to create post:", err)
    });
  }
}
```

---

## 3. Beginner: A Basic Write Service

A single service centralizes all write logic — components stay thin and focused on display.

```typescript
// services/post.service.ts
import { Injectable, inject } from "@angular/core";
import { HttpClient } from "@angular/common/http";
import { Observable } from "rxjs";
import { Post } from "../models/post.model";

@Injectable({ providedIn: "root" })
export class PostService {
  private http = inject(HttpClient);
  private apiUrl = "https://api.example.com/posts";

  create(post: Post): Observable<Post> {
    return this.http.post<Post>(this.apiUrl, post);
  }

  update(id: number, post: Partial<Post>): Observable<Post> {
    return this.http.put<Post>(`${this.apiUrl}/${id}`, post);
  }

  patch(id: number, changes: Partial<Post>): Observable<Post> {
    return this.http.patch<Post>(`${this.apiUrl}/${id}`, changes);
  }

  delete(id: number): Observable<void> {
    return this.http.delete<void>(`${this.apiUrl}/${id}`);
  }
}
```

---

## 4. Beginner: Template-Driven Forms

Good for simple forms where you don't need fine-grained programmatic control.

```typescript
// components/create-post/create-post.component.ts
import { Component, inject } from "@angular/core";
import { FormsModule, NgForm } from "@angular/forms";
import { PostService } from "../../services/post.service";
import { Post } from "../../models/post.model";

@Component({
  selector: "app-create-post",
  standalone: true,
  imports: [FormsModule],
  template: `
    <form #postForm="ngForm" (ngSubmit)="onSubmit(postForm)">
      <input name="title" [(ngModel)]="model.title" required minlength="3" placeholder="Title" />
      <textarea name="body" [(ngModel)]="model.body" required placeholder="Body"></textarea>
      <button type="submit" [disabled]="postForm.invalid || submitting">
        {{ submitting ? 'Saving...' : 'Create Post' }}
      </button>
    </form>
  `
})
export class CreatePostComponent {
  private postService = inject(PostService);

  model: Post = { title: "", body: "", published: false };
  submitting = false;

  onSubmit(form: NgForm) {
    if (form.invalid) return;

    this.submitting = true;
    this.postService.create(this.model).subscribe({
      next: () => {
        this.submitting = false;
        form.resetForm();
      },
      error: (err) => {
        this.submitting = false;
        console.error("Failed to create post:", err);
      }
    });
  }
}
```

---

## 5. Intermediate: Reactive Forms

The recommended approach for anything beyond trivial forms — testable, composable, and type-safe.

```typescript
// components/create-post/create-post.component.ts
import { Component, inject } from "@angular/core";
import { ReactiveFormsModule, FormBuilder, Validators } from "@angular/forms";
import { PostService } from "../../services/post.service";

@Component({
  selector: "app-create-post",
  standalone: true,
  imports: [ReactiveFormsModule],
  template: `
    <form [formGroup]="postForm" (ngSubmit)="onSubmit()">
      <input formControlName="title" placeholder="Title" />
      <textarea formControlName="body" placeholder="Body"></textarea>

      <label>
        <input type="checkbox" formControlName="published" />
        Publish immediately
      </label>

      <button type="submit" [disabled]="postForm.invalid || submitting()">
        {{ submitting() ? 'Saving...' : 'Create Post' }}
      </button>
    </form>
  `
})
export class CreatePostComponent {
  private fb = inject(FormBuilder);
  private postService = inject(PostService);

  submitting = signal(false);

  postForm = this.fb.group({
    title: ["", [Validators.required, Validators.minLength(3)]],
    body: ["", [Validators.required, Validators.minLength(10)]],
    published: [false]
  });

  onSubmit() {
    if (this.postForm.invalid) {
      this.postForm.markAllAsTouched();
      return;
    }

    this.submitting.set(true);

    this.postService.create(this.postForm.getRawValue() as any).subscribe({
      next: () => {
        this.submitting.set(false);
        this.postForm.reset({ published: false });
      },
      error: () => this.submitting.set(false)
    });
  }
}
```

```typescript
import { signal } from "@angular/core"; // add to imports above
```

---

## 6. Intermediate: Form Validation

### Built-in and Custom Synchronous Validators

```typescript
// validators/no-profanity.validator.ts
import { AbstractControl, ValidationErrors } from "@angular/forms";

const BLOCKED_WORDS = ["spam", "scam"];

export function noProfanityValidator(control: AbstractControl): ValidationErrors | null {
  const value = (control.value || "").toLowerCase();
  const found = BLOCKED_WORDS.find(word => value.includes(word));
  return found ? { profanity: { word: found } } : null;
}
```

```typescript
this.postForm = this.fb.group({
  title: ["", [Validators.required, Validators.minLength(3), noProfanityValidator]],
  body: ["", [Validators.required, Validators.minLength(10)]]
});
```

### Async Validator (e.g. checking a title isn't already taken)

```typescript
// validators/unique-title.validator.ts
import { AbstractControl } from "@angular/forms";
import { HttpClient } from "@angular/common/http";
import { map, catchError, of, debounceTime, switchMap, first } from "rxjs";

export function uniqueTitleValidator(http: HttpClient) {
  return (control: AbstractControl) => {
    return of(control.value).pipe(
      debounceTime(400),
      switchMap(title =>
        http.get<{ exists: boolean }>(`/api/posts/check-title?title=${encodeURIComponent(title)}`)
      ),
      map(res => (res.exists ? { titleTaken: true } : null)),
      catchError(() => of(null)), // don't block the form if the check fails
      first()
    );
  };
}
```

```typescript
title: ["", [Validators.required], [uniqueTitleValidator(this.http)]]
```

### Displaying Validation Errors in the Template

```html
<input formControlName="title" placeholder="Title" />
@if (postForm.get('title')?.invalid && postForm.get('title')?.touched) {
  <p class="error">
    @if (postForm.get('title')?.hasError('required')) { Title is required. }
    @if (postForm.get('title')?.hasError('minlength')) { Title is too short. }
    @if (postForm.get('title')?.hasError('titleTaken')) { This title is already used. }
  </p>
}
```

---

## 7. Intermediate: PUT, PATCH & DELETE

```typescript
// components/edit-post/edit-post.component.ts
import { Component, inject, input } from "@angular/core";
import { PostService } from "../../services/post.service";

@Component({
  selector: "app-edit-post",
  standalone: true,
  template: `
    <button (click)="publish()">Publish</button>
    <button (click)="remove()">Delete</button>
  `
})
export class EditPostComponent {
  private postService = inject(PostService);
  postId = input.required<number>();

  publish() {
    // PATCH — partial update, only sends what changed
    this.postService.patch(this.postId(), { published: true }).subscribe({
      next: (post) => console.log("Published:", post),
      error: (err) => console.error("Failed to publish:", err)
    });
  }

  replaceEntirePost() {
    // PUT — full replacement, sends the complete object
    this.postService.update(this.postId(), {
      title: "Fully Updated Title",
      body: "Fully updated body",
      published: true
    }).subscribe();
  }

  remove() {
    if (!confirm("Delete this post?")) return;

    this.postService.delete(this.postId()).subscribe({
      next: () => console.log("Deleted"),
      error: (err) => console.error("Failed to delete:", err)
    });
  }
}
```

---

## 8. Intermediate: Dynamic Form Arrays

For writing documents with variable-length nested data — e.g. an order with multiple line items.

```typescript
import { Component, inject } from "@angular/core";
import { ReactiveFormsModule, FormBuilder, Validators } from "@angular/forms";

@Component({
  selector: "app-order-form",
  standalone: true,
  imports: [ReactiveFormsModule],
  template: `
    <form [formGroup]="orderForm" (ngSubmit)="onSubmit()">
      <div formArrayName="items">
        @for (item of items.controls; track $index; let i = $index) {
          <div [formGroupName]="i">
            <input formControlName="sku" placeholder="SKU" />
            <input formControlName="qty" type="number" placeholder="Qty" />
            <button type="button" (click)="removeItem(i)">Remove</button>
          </div>
        }
      </div>

      <button type="button" (click)="addItem()">Add Item</button>
      <button type="submit" [disabled]="orderForm.invalid">Place Order</button>
    </form>
  `
})
export class OrderFormComponent {
  private fb = inject(FormBuilder);

  orderForm = this.fb.group({
    items: this.fb.array([this.createItem()])
  });

  get items() {
    return this.orderForm.get("items") as import("@angular/forms").FormArray;
  }

  createItem() {
    return this.fb.group({
      sku: ["", Validators.required],
      qty: [1, [Validators.required, Validators.min(1)]]
    });
  }

  addItem() {
    this.items.push(this.createItem());
  }

  removeItem(index: number) {
    this.items.removeAt(index);
  }

  onSubmit() {
    if (this.orderForm.invalid) return;
    console.log("Order payload:", this.orderForm.getRawValue());
    // POST this.orderForm.getRawValue() via your service
  }
}
```

---

## 9. Advanced: Optimistic Updates with Signals

Update the UI instantly, then roll back if the server write fails.

```typescript
// services/post.service.ts
import { Injectable, inject, signal } from "@angular/core";
import { HttpClient } from "@angular/common/http";
import { Post } from "../models/post.model";
import { catchError, tap, throwError } from "rxjs";

@Injectable({ providedIn: "root" })
export class PostService {
  private http = inject(HttpClient);
  private apiUrl = "https://api.example.com/posts";

  posts = signal<Post[]>([]);

  toggleLike(postId: number) {
    const previous = this.posts();

    // 1. Optimistically update local state immediately
    this.posts.set(
      previous.map(p => (p.id === postId ? { ...p, likes: (p as any).likes + 1 } : p))
    );

    // 2. Fire the real write; roll back on failure
    return this.http.post<Post>(`${this.apiUrl}/${postId}/like`, {}).pipe(
      tap((updated) => {
        this.posts.set(
          this.posts().map(p => (p.id === postId ? updated : p))
        );
      }),
      catchError((err) => {
        this.posts.set(previous); // rollback
        return throwError(() => err);
      })
    );
  }
}
```

```typescript
// component usage
this.postService.toggleLike(post.id!).subscribe({
  error: () => console.warn("Like failed, UI rolled back")
});
```

---

## 10. Advanced: HTTP Interceptors for Writes

### Auth Token Interceptor

```typescript
// interceptors/auth.interceptor.ts
import { HttpInterceptorFn } from "@angular/common/http";
import { inject } from "@angular/core";
import { AuthService } from "../services/auth.service";

export const authInterceptor: HttpInterceptorFn = (req, next) => {
  const auth = inject(AuthService);
  const token = auth.getToken();

  if (!token) return next(req);

  const cloned = req.clone({
    setHeaders: { Authorization: `Bearer ${token}` }
  });

  return next(cloned);
};
```

### Retry-on-Failure Interceptor for Idempotent Writes

```typescript
// interceptors/retry.interceptor.ts
import { HttpInterceptorFn } from "@angular/common/http";
import { retry, timer } from "rxjs";

export const retryInterceptor: HttpInterceptorFn = (req, next) => {
  // Only retry safe, idempotent methods — never retry POST blindly
  if (req.method !== "PUT" && req.method !== "DELETE") {
    return next(req);
  }

  return next(req).pipe(
    retry({
      count: 2,
      delay: (error, retryCount) => timer(retryCount * 500)
    })
  );
};
```

```typescript
// app.config.ts
providers: [
  provideHttpClient(withInterceptors([authInterceptor, retryInterceptor]))
]
```

---

## 11. Advanced: File Uploads

```typescript
// services/upload.service.ts
import { Injectable, inject } from "@angular/core";
import { HttpClient, HttpEvent, HttpEventType } from "@angular/common/http";
import { Observable } from "rxjs";

@Injectable({ providedIn: "root" })
export class UploadService {
  private http = inject(HttpClient);

  uploadAvatar(file: File): Observable<HttpEvent<{ url: string }>> {
    const formData = new FormData();
    formData.append("avatar", file, file.name);

    return this.http.post<{ url: string }>("/api/upload", formData, {
      reportProgress: true,
      observe: "events"
    });
  }
}
```

```typescript
// components/upload/upload.component.ts
import { Component, inject, signal } from "@angular/core";
import { HttpEventType } from "@angular/common/http";
import { UploadService } from "../../services/upload.service";

@Component({
  selector: "app-upload",
  standalone: true,
  template: `
    <input type="file" (change)="onFileSelected($event)" accept="image/*" />
    @if (progress() > 0) {
      <progress [value]="progress()" max="100"></progress>
    }
  `
})
export class UploadComponent {
  private uploadService = inject(UploadService);
  progress = signal(0);

  onFileSelected(event: Event) {
    const input = event.target as HTMLInputElement;
    const file = input.files?.[0];
    if (!file) return;

    if (file.size > 5 * 1024 * 1024) {
      console.error("File too large (max 5MB)");
      return;
    }

    this.uploadService.uploadAvatar(file).subscribe({
      next: (event) => {
        if (event.type === HttpEventType.UploadProgress && event.total) {
          this.progress.set(Math.round((100 * event.loaded) / event.total));
        } else if (event.type === HttpEventType.Response) {
          console.log("Uploaded:", event.body?.url);
          this.progress.set(0);
        }
      },
      error: (err) => {
        console.error("Upload failed:", err);
        this.progress.set(0);
      }
    });
  }
}
```

---

## 12. Advanced: State Management Writes (NgRx)

```bash
ng add @ngrx/store @ngrx/effects
```

```typescript
// store/post.actions.ts
import { createAction, props } from "@ngrx/store";
import { Post } from "../models/post.model";

export const createPost = createAction("[Post] Create", props<{ post: Post }>());
export const createPostSuccess = createAction("[Post] Create Success", props<{ post: Post }>());
export const createPostFailure = createAction("[Post] Create Failure", props<{ error: string }>());
```

```typescript
// store/post.effects.ts
import { Injectable, inject } from "@angular/core";
import { Actions, createEffect, ofType } from "@ngrx/effects";
import { catchError, map, mergeMap, of } from "rxjs";
import { PostService } from "../services/post.service";
import * as PostActions from "./post.actions";

@Injectable()
export class PostEffects {
  private actions$ = inject(Actions);
  private postService = inject(PostService);

  createPost$ = createEffect(() =>
    this.actions$.pipe(
      ofType(PostActions.createPost),
      mergeMap(({ post }) =>
        this.postService.create(post).pipe(
          map((created) => PostActions.createPostSuccess({ post: created })),
          catchError((err) => of(PostActions.createPostFailure({ error: err.message })))
        )
      )
    )
  );
}
```

```typescript
// store/post.reducer.ts
import { createReducer, on } from "@ngrx/store";
import { Post } from "../models/post.model";
import * as PostActions from "./post.actions";

export interface PostState {
  posts: Post[];
  saving: boolean;
  error: string | null;
}

const initialState: PostState = { posts: [], saving: false, error: null };

export const postReducer = createReducer(
  initialState,
  on(PostActions.createPost, (state) => ({ ...state, saving: true, error: null })),
  on(PostActions.createPostSuccess, (state, { post }) => ({
    ...state,
    posts: [...state.posts, post],
    saving: false
  })),
  on(PostActions.createPostFailure, (state, { error }) => ({
    ...state,
    saving: false,
    error
  }))
);
```

```typescript
// component usage
this.store.dispatch(PostActions.createPost({ post: this.postForm.getRawValue() as Post }));
```

---

## 13. Advanced: Error Handling Patterns

### Global HTTP Error Interceptor

```typescript
// interceptors/error.interceptor.ts
import { HttpInterceptorFn, HttpErrorResponse } from "@angular/common/http";
import { inject } from "@angular/core";
import { catchError, throwError } from "rxjs";
import { NotificationService } from "../services/notification.service";

export const errorInterceptor: HttpInterceptorFn = (req, next) => {
  const notifications = inject(NotificationService);

  return next(req).pipe(
    catchError((error: HttpErrorResponse) => {
      if (error.status === 0) {
        notifications.show("Network error — check your connection.");
      } else if (error.status === 409) {
        notifications.show("This item was changed by someone else. Please refresh.");
      } else if (error.status === 422) {
        notifications.show("Some fields are invalid — please review the form.");
      } else if (error.status >= 500) {
        notifications.show("Server error — please try again shortly.");
      }
      return throwError(() => error);
    })
  );
};
```

### Component-Level Handling with a Typed Result

```typescript
import { Component, inject, signal } from "@angular/core";
import { PostService } from "../../services/post.service";

@Component({ selector: "app-create-post", standalone: true, template: `...` })
export class CreatePostComponent {
  private postService = inject(PostService);
  errorMessage = signal<string | null>(null);
  submitting = signal(false);

  submit(post: any) {
    this.submitting.set(true);
    this.errorMessage.set(null);

    this.postService.create(post).subscribe({
      next: () => this.submitting.set(false),
      error: (err) => {
        this.submitting.set(false);
        this.errorMessage.set(
          err.status === 422
            ? "Please fix the highlighted fields."
            : "Something went wrong. Please try again."
        );
      }
    });
  }
}
```

---

## 14. Advanced: Testing Writes

```bash
ng generate service services/post --skip-tests=false
```

```typescript
// services/post.service.spec.ts
import { TestBed } from "@angular/core/testing";
import { HttpClientTestingModule, HttpTestingController } from "@angular/common/http/testing";
import { PostService } from "./post.service";
import { Post } from "../models/post.model";

describe("PostService", () => {
  let service: PostService;
  let httpMock: HttpTestingController;

  beforeEach(() => {
    TestBed.configureTestingModule({
      imports: [HttpClientTestingModule],
      providers: [PostService]
    });

    service = TestBed.inject(PostService);
    httpMock = TestBed.inject(HttpTestingController);
  });

  afterEach(() => httpMock.verify());

  it("sends a POST request with the post payload", () => {
    const newPost: Post = { title: "Test Post", body: "Test body", published: false };

    service.create(newPost).subscribe((result) => {
      expect(result.id).toBe(1);
    });

    const req = httpMock.expectOne("https://api.example.com/posts");
    expect(req.request.method).toBe("POST");
    expect(req.request.body).toEqual(newPost);

    req.flush({ id: 1, ...newPost });
  });

  it("propagates an error when the server returns 500", () => {
    const newPost: Post = { title: "Test Post", body: "Test body", published: false };

    service.create(newPost).subscribe({
      next: () => fail("expected an error"),
      error: (err) => expect(err.status).toBe(500)
    });

    const req = httpMock.expectOne("https://api.example.com/posts");
    req.flush("Server error", { status: 500, statusText: "Internal Server Error" });
  });
});
```

---

## 15. Best Practices Cheat Sheet

- ✅ Centralize writes in **services**, not components — keeps components focused on presentation and makes writes reusable/testable.
- ✅ Prefer **Reactive Forms** over template-driven forms for anything beyond a trivial form — better type safety and testability.
- ✅ Use `PATCH` for partial updates and `PUT` only when replacing the entire resource.
- ✅ Debounce async validators (e.g. uniqueness checks) to avoid firing a request on every keystroke.
- ✅ Use interceptors for cross-cutting write concerns (auth headers, retries, global error toasts) instead of repeating logic per service call.
- ✅ Roll back optimistic UI updates in a `catchError` if the underlying write fails.
- ✅ Only retry **idempotent** methods (`PUT`, `DELETE`) automatically — never blindly retry `POST`, which can create duplicates.
- ✅ Validate file size/type client-side before upload, but always re-validate server-side too.
- ✅ Use `HttpClientTestingModule`/`HttpTestingController` to test writes without hitting a real network.
- ❌ Don't subscribe to write `Observable`s without an `error` handler — unhandled errors fail silently in the console.
- ❌ Don't forget to unsubscribe from long-lived streams tied to writes (or use `takeUntilDestroyed()`) to avoid memory leaks.
- ❌ Don't put business/validation logic directly in components — keep it in services or dedicated validator functions so it's testable in isolation.

---

## License

Free to use in any project — copy, adapt, and drop straight into your own `README.md`.

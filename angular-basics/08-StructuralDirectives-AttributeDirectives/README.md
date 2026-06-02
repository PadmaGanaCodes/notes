# Structural Directives & Attribute Directives 🚀

## Overview

Today we explored how Angular can dynamically control what gets displayed on the screen and how elements are styled using Structural Directives and Attribute Directives.

Using Angular's modern control flow syntax, we can conditionally render content, display lists, and apply styles based on application data.

As part of the Employee Management Dashboard project, we enhanced the Employee Profile Card by:

* Conditionally displaying employee status
* Rendering employee skills dynamically
* Applying styles based on employee status

---

# Project Used

```bash
angular-dashboard-app
```

---

# Step 1 - Update Component Class

Open:

```text
src/app/components/user-card/user-card.ts
```

Update the component:

```ts
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { NgClass, NgStyle } from '@angular/common';

@Component({
  selector: 'app-user-card',
  standalone: true,
  imports: [FormsModule, NgClass, NgStyle],
  templateUrl: './user-card.html',
  styleUrl: './user-card.css'
})
export class UserCardComponent {

  employeeName = 'Padma Gana';

  designation = 'Senior Frontend Developer';

  experience = 7;

  isActive = true;

  profileImage =
    'https://img.magnific.com/premium-vector/young-man-avatar-character-due-avatar-man-vector-icon-cartoon-illustration_1186924-4438.jpg?semt=ais_hybrid&w=740&q=80';

  skills = [
    'Angular',
    'TypeScript',
    'Java',
    'SQL'
  ];

  updateDesignation() {
    this.designation = 'Lead Frontend Developer';
  }
}
```

---

# Step 2 - Use @if for Conditional Rendering

Display employee status conditionally.

```html
@if(isActive) {
  <p class="active-status">
    Active Employee
  </p>
} @else {
  <p class="inactive-status">
    Inactive Employee
  </p>
}
```

### What does this do?

* Displays "Active Employee" when `isActive` is true
* Displays "Inactive Employee" when `isActive` is false

---

# Step 3 - Use @for for Dynamic List Rendering

Render employee skills dynamically.

```html
<h3>Skills</h3>

<ul>
  @for(skill of skills; track skill) {
    <li>{{ skill }}</li>
  }
</ul>
```

### Output

```text
Angular
TypeScript
Java
SQL
```

Angular automatically creates the list based on the array.

---

# Step 4 - Use ngClass

Apply different CSS classes based on employee status.

```html
<p
  [ngClass]="{
    'active-status': isActive,
    'inactive-status': !isActive
  }"
>
  Employee Status
</p>
```

### What does this do?

* Applies `active-status` class when employee is active
* Applies `inactive-status` class when employee is inactive

---

# Step 5 - Use ngStyle

Apply styles dynamically.

```html
<p
  [ngStyle]="{
    'font-weight': 'bold',
    'font-size': '18px'
  }"
>
  Experience: {{ experience }} Years
</p>
```

### What does this do?

Styles are applied dynamically using Angular bindings.

---

# Step 6 - Update Template

File:

```text
src/app/components/user-card/user-card.html
```

```html
<div class="card">

  <div class="employee-header">

    <img [src]="profileImage" alt="Employee Profile" />

    <div class="employee-info">
      <h2>{{ employeeName }}</h2>
      <p>{{ designation }}</p>
    </div>

  </div>

  @if(isActive) {
    <p class="active-status">
      Active Employee
    </p>
  } @else {
    <p class="inactive-status">
      Inactive Employee
    </p>
  }

  <p
    [ngStyle]="{
      'font-weight': 'bold',
      'font-size': '18px'
    }"
  >
    Experience: {{ experience }} Years
  </p>

  <h3>Skills</h3>

  <ul>
    @for(skill of skills; track skill) {
      <li>{{ skill }}</li>
    }
  </ul>

</div>
```

---

# Step 7 - Add Styling

File:

```text
src/app/components/user-card/user-card.css
```

Add:

```css
.active-status {
  color: green;
  font-weight: bold;
}

.inactive-status {
  color: red;
  font-weight: bold;
}
```

---

# Concepts Covered

## Structural Directives

Structural Directives change the DOM structure.

### @if

```html
@if(isActive) {
  ...
}
```

Used for conditional rendering.

---

### @for

```html
@for(skill of skills; track skill) {
  ...
}
```

Used for rendering collections.

---

## Attribute Directives

Attribute Directives modify existing elements.

### ngClass

```html
[ngClass]="..."
```

Used for dynamic CSS classes.

---

### ngStyle

```html
[ngStyle]="..."
```

Used for dynamic styling.

---

# Final Output

✅ Conditional Rendering using @if

✅ Dynamic List Rendering using @for

✅ Dynamic Styling using ngClass

✅ Dynamic CSS using ngStyle

✅ Modern Angular Control Flow

---

# Next Topic

➡️ Pipes

➡️ Custom Pipes

---

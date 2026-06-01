# Property Binding, Event Binding & Two-Way Binding 🚀

## Overview

Today the Employee Management Dashboard became interactive using Angular's binding mechanisms.

Angular provides different types of bindings to connect component data with the UI and handle user interactions efficiently.

In this exercise, we implemented:

* Property Binding
* Event Binding
* Two-Way Binding

These concepts form the foundation of dynamic Angular applications.

---

# Project Used

```bash
angular-dashboard-app
```

---

# What Was Built

A simple Employee Profile Card that demonstrates:

✅ Dynamic image rendering using Property Binding

✅ Button click handling using Event Binding

✅ Real-time input updates using Two-Way Binding

✅ Automatic UI updates when component data changes

---

# Step 1 - Update Component Class

File:

```text
src/app/components/user-card/user-card.ts
```

```ts
import { Component } from '@angular/core';
import { FormsModule } from '@angular/forms';

@Component({
  selector: 'app-user-card',
  standalone: true,
  imports: [FormsModule],
  templateUrl: './user-card.html',
  styleUrl: './user-card.css'
})
export class UserCard {

  employeeName = 'Padma Gana';

  designation = 'Frontend Developer';

  experience = 7;

  profileImage =
    'https://img.magnific.com/premium-vector/young-man-avatar-character-due-avatar-man-vector-icon-cartoon-illustration_1186924-4438.jpg?semt=ais_hybrid&w=740&q=80';

  updateDesignation() {
    this.designation = 'Senior Frontend Developer';
  }
}
```

---

# Step 2 - Implement Property Binding

Property Binding allows data from the component to be passed to HTML elements.

Example:

```html
<img [src]="profileImage" alt="Employee Profile" />
```

Angular dynamically assigns the value of `profileImage` to the image source.

---

# Step 3 - Implement Event Binding

Event Binding allows the component to respond to user actions.

Example:

```html
<button (click)="updateDesignation()">
  Promote Employee
</button>
```

When the button is clicked, Angular executes the `updateDesignation()` method.

---

# Step 4 - Implement Two-Way Binding

Two-Way Binding keeps the UI and component synchronized.

Example:

```html
<input
  type="text"
  [(ngModel)]="employeeName"
  placeholder="Update Employee Name"
/>
```

When:

* User updates the input field → Component value updates
* Component value changes → UI updates automatically

---

# Step 5 - Update Employee Card Template

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

  <p>Experience: {{ experience }} Years</p>

  <input
    type="text"
    [(ngModel)]="employeeName"
    placeholder="Update Employee Name"
  />

  <br /><br />

  <button (click)="updateDesignation()">
    Promote Employee
  </button>

</div>
```

---

# Step 6 - Add Styling

File:

```text
src/app/components/user-card/user-card.css
```

```css
.card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 20px;
  width: 450px;
  background: #fff;
}

.employee-header {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 16px;
}

.employee-header img {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  object-fit: cover;
}

.employee-info h2 {
  margin: 0;
}

.employee-info p {
  margin: 4px 0 0;
  color: #666;
}

input {
  width: 100%;
  padding: 8px;
  box-sizing: border-box;
}

button {
  padding: 8px 16px;
  cursor: pointer;
}
```

---

# Concepts Covered

## Property Binding

Used to send data from the component to the UI.

Example:

```html
[src]="profileImage"
```

---

## Event Binding

Used to handle user interactions.

Example:

```html
(click)="updateDesignation()"
```

---

## Two-Way Binding

Used to synchronize component data and UI.

Example:

```html
[(ngModel)]="employeeName"
```

---

# Application Behavior

### Property Binding

The employee profile image is rendered dynamically.

### Event Binding

Clicking **Promote Employee** updates:

```text
Frontend Developer
```

to

```text
Senior Frontend Developer
```

### Two-Way Binding

Updating the employee name in the textbox immediately updates the name displayed in the profile card.

---

# Screenshots

## Initial Employee Profile Card

Add screenshot here:


<img width="843" height="796" alt="image" src="https://github.com/user-attachments/assets/6c1f4611-d941-4f7f-bc48-0ce925d42fdb" />



---

## Updating Employee Name Using Two-Way Binding

Add screenshot here:


<img width="763" height="778" alt="image" src="https://github.com/user-attachments/assets/14fcf4bf-0130-49fc-aed1-f46d746d1aa4" />



---

## After Clicking Promote Employee Button

Add screenshot here:


<img width="787" height="789" alt="image" src="https://github.com/user-attachments/assets/0951d6a4-f163-4681-bf82-050c0afcc7fc" />



---

# Folder Structure

```text
src/
 └── app/
      └── components/
           └── user-card/
                ├── user-card.ts
                ├── user-card.html
                └── user-card.css
```

---

# Progress So Far

✅ Angular Setup

✅ Angular Project Structure

✅ Components & Component Creation

✅ Standalone Components

✅ Templates & Interpolation

✅ Property Binding

✅ Event Binding

✅ Two-Way Binding

---

# Next Topic

➡️ Structural Directives

➡️ Attribute Directives

---

# Source Code

You can refer the code present at: You can refer the code present at: https://github.com/PadmaGanaCodes/angular-enterprise-series/tree/main/angular-dashboard-app/src/app


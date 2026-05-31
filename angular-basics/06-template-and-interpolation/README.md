# Day 6 - Templates & Interpolation 🚀

## Overview

After creating components, the next step is understanding how data is displayed inside them using Templates and Interpolation.

A **Template** defines the UI that Angular renders in the browser. It determines what users see on the screen.

**Interpolation** allows values from a component's TypeScript class to be displayed dynamically in the template using double curly braces:

```html
{{ value }}
```

Instead of hardcoding content directly in HTML, Angular allows data to be maintained in the component and rendered dynamically in the UI.

---

# Project Used

```bash
angular-dashboard-app
```

---

# Step 1 - Run the Application

Start the Angular development server.

```bash
ng serve
```

Open the application:

```text
http://localhost:4200
```

---

# Step 2 - Update User Card Component

Open:

```text
src/app/components/user-card/user-card.ts
```

Add properties to the component:

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-user-card',
  standalone: true,
  templateUrl: './user-card.html',
  styleUrl: './user-card.css'
})
export class UserCardComponent {

  employeeName = 'Padma Gana';

  designation = 'Frontend Developer';

  experience = 7;

}
```

---

# Step 3 - Use Interpolation in Template

Open:

```text
src/app/components/user-card/user-card.html
```

Update the template:

```html
<div class="card">
  <h2>{{ employeeName }}</h2>

  <p>Designation: {{ designation }}</p>

  <p>Experience: {{ experience }} Years</p>
</div>
```

---

# Step 4 - Understand Interpolation

Angular reads the values from the component class and displays them inside the HTML.

Examples:

```html
{{ employeeName }}
```

Displays:

```text
Padma Gana
```

---

```html
{{ designation }}
```

Displays:

```text
Frontend Developer
```

---

```html
{{ experience }}
```

Displays:

```text
7
```

Whenever these values change in the component, Angular automatically updates the UI.

---

# Step 5 - Add Styling

Open:

```text
src/app/components/user-card/user-card.css
```

Add:

```css
.card {
  border: 1px solid #ddd;
  padding: 16px;
  width: 300px;
  border-radius: 8px;
}

h2 {
  margin-top: 0;
}
```

---

# Step 6 - Verify Output

The application should display:

```text
Padma Gana

Designation: Frontend Developer

Experience: 7 Years
```

All values are rendered dynamically using interpolation.

---

# Key Concepts Covered

## Templates

Templates define the structure and layout of the UI.

Example:

```html
<h1>Employee Information</h1>
```

---

## Interpolation

Interpolation displays data from the component inside the template.

Example:

```html
{{ employeeName }}
```

---

## Benefits

* Dynamic UI rendering
* Clear separation of logic and presentation
* Easier maintenance
* Better readability
* Automatic UI updates

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

# Final Output

✅ Displayed data from component to template

✅ Used Angular Interpolation

✅ Created dynamic UI content

✅ Separated component logic from presentation

---

# Source Code

You can refer the code present at: https://github.com/PadmaGanaCodes/angular-enterprise-series/tree/main/angular-dashboard-app/src/app

---

# Currently we have this on UI at http://localhost:4200/

<img width="1561" height="840" alt="image" src="https://github.com/user-attachments/assets/bea74220-9abf-4cac-a35e-c1e3748b9a33" />


# Components & Creating Components 🚀

## Overview

In this step, we introduced Components in Angular and started structuring the application into smaller UI sections.

Components are one of the core building blocks of Angular applications.

Instead of building everything inside a single page, Angular allows applications to be divided into smaller manageable sections such as:

- Header
- Footer
- Sidebar
- User Cards
- Dashboard Widgets

This helps make applications:

- Cleaner
- Easier to maintain
- More scalable
- Better organized

---

# Project Used

```bash
angular-dashboard-app
```

---

# Step 1 - Navigate to Project

Open terminal inside the Angular project.

```bash
cd angular-dashboard-app
```

---

# Step 2 - Run the Application

Start Angular development server.

```bash
ng serve
```

Application runs on:

```text
http://localhost:4200
```

---

# Step 3 - Create Components

Navigate to 
```bash
cd angular-dashboard-app/src/app 
```
and then create components

## Create Header Component

```bash
ng generate component components/header
```

Short version:

```bash
ng g c components/header
```

---

## Create Footer Component

```bash
ng g c components/footer
```

---

## Create User Card Component

```bash
ng g c components/user-card
```

---

# Step 4 - Understand Generated Files

Angular automatically creates:

```text
component-name.ts
component-name.html
component-name.css
component-name.spec.ts
```

Each component contains:

- Logic → TypeScript
- UI → HTML
- Styling → CSS/SCSS

---

# Step 5 - Add Content to Components

## Header Component

### header.html

```html
<header>
  <h2>Angular Enterprise Series</h2>
</header>
```

### header.css

```css
header {
  background-color: #1976d2;
  color: white;
  padding: 15px;
}
```

---

## Footer Component

### footer.html

```html
<footer>
  <p>Learning Angular Components</p>
</footer>
```

### footer.css

```css
footer {
  background-color: #eeeeee;
  padding: 12px;
  margin-top: 20px;
}
```

---

## User Card Component

### user-card.ts

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-user-card',
  standalone: true,
  templateUrl: './user-card.html',
  styleUrls: ['./user-card.css']
})
export class UserCardComponent {
  name = 'Your Name';
  role = 'Angular Developer';
}
```

---

### user-card.html

```html
<div class="card">
  <h3>{{ name }}</h3>
  <p>{{ role }}</p>
</div>
```

---

### user-card.css

```css
.card {
  border: 1px solid #ccc;
  padding: 15px;
  width: 250px;
  border-radius: 8px;
}
```

---

# Step 6 — Use Components in App Component

Update:

```text
src/app/app.html
```

Add:

```html
<app-header></app-header>

<h1>Components in Angular</h1>

<app-user-card></app-user-card>

<app-footer></app-footer>
```

---

# Final Output

Application now displays:

- Header
- User Card
- Footer

This demonstrates how Angular combines multiple smaller UI sections to build a complete application page.

---

# Folder Structure

```text
src/
 └── app/
      └── components/
           ├── header/
           ├── footer/
           └── user-card/
```
---

# Source Code

You can refer the code present at : 
https://github.com/PadmaGanaCodes/angular-enterprise-series/tree/main/angular-dashboard-app/src/app

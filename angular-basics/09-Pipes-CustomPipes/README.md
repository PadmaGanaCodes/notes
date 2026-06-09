# Day 9 - Pipes & Custom Pipes 🚀

## Overview

Today we explored Pipes and Custom Pipes in Angular.

Pipes are used to transform data directly in templates without modifying the original value.

They help keep templates clean and improve readability by separating formatting logic from component logic.

Angular provides several built-in pipes, and it also allows us to create custom pipes for application-specific transformations.

---

# Project Used

```bash
angular-dashboard-app
```

---

# What Was Built

Enhanced the Employee Profile Card by:

- Formatting employee name
- Formatting joining date
- Formatting salary
- Creating a custom Employee ID Pipe

---

# Step 1 - Update Employee Data

Open:

```text
src/app/components/user-card/user-card.ts
```

Update:

```ts
employeeName = 'padma gana';

designation = 'Senior Frontend Developer';

experience = 7;

salary = 1200000;

joiningDate = new Date('2022-06-15');

employeeId = 101;
```

---

# Step 2 - Use Built-in Pipes

Open:

```text
src/app/components/user-card/user-card.html
```

Update:

```html
<h2>{{ employeeName | titlecase }}</h2>

<p>{{ designation | uppercase }}</p>

<p>Joining Date: {{ joiningDate | date:'dd MMM yyyy' }}</p>

<p>Salary: {{ salary | currency:'INR' }}</p>
```

---

# Output

```text
Padma Gana

SENIOR FRONTEND DEVELOPER

Joining Date: 15 Jun 2022

Salary: ₹12,00,000.00
```

---

# Common Built-in Pipes

## Uppercase Pipe

```html
{{ designation | uppercase }}
```

Output:

```text
SENIOR FRONTEND DEVELOPER
```

---

## Lowercase Pipe

```html
{{ designation | lowercase }}
```

Output:

```text
senior frontend developer
```

---

## Titlecase Pipe

```html
{{ employeeName | titlecase }}
```

Output:

```text
Padma Gana
```

---

## Date Pipe

```html
{{ joiningDate | date:'dd MMM yyyy' }}
```

Output:

```text
15 Jun 2022
```

---

## Currency Pipe

```html
{{ salary | currency:'INR' }}
```

Output:

```text
₹12,00,000.00
```

---

# Step 3 - Create Custom Pipe

Generate a pipe:

```bash
ng g p shared/pipes/employee-id
```

Angular creates:

```text
employee-id.pipe.ts
```

---

# Step 4 - Implement Custom Pipe

Open:

```text
src/app/shared/pipes/employee-id.pipe.ts
```

Update:

```ts
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'employeeId',
  standalone: true
})
export class EmployeeIdPipe implements PipeTransform {

  transform(value: number): string {
    return `EMP-${value}`;
  }

}
```

---

# Step 5 - Import Pipe

Open:

```text
user-card.ts
```

Import:

```ts
import { EmployeeIdPipe } from '../../shared/pipes/employee-id.pipe';
```

Add to imports:

```ts
imports: [
  FormsModule,
  NgClass,
  NgStyle,
  EmployeeIdPipe
]
```

---

# Step 6 - Use Custom Pipe

Update template:

```html
<p>Employee ID: {{ employeeId | employeeId }}</p>
```

---

# Output

```text
Employee ID: EMP-101
```

---

# Why Use Custom Pipes?

Custom Pipes are useful when:

- Formatting IDs
- Formatting phone numbers
- Formatting account numbers
- Displaying business-specific values
- Reusing transformation logic across multiple components

---

# Concepts Covered

## Built-in Pipes

### Titlecase Pipe

```html
{{ employeeName | titlecase }}
```

### Uppercase Pipe

```html
{{ designation | uppercase }}
```

### Date Pipe

```html
{{ joiningDate | date:'dd MMM yyyy' }}
```

### Currency Pipe

```html
{{ salary | currency:'INR' }}
```

---

## Custom Pipe

```html
{{ employeeId | employeeId }}
```

Transforms:

```text
101
```

to:

```text
EMP-101
```

---

# Final Output

✅ Built-in Pipes

✅ Text Formatting

✅ Date Formatting

✅ Currency Formatting

✅ Custom Pipe Creation

✅ Reusable Data Transformation

---

# Progress So Far

✅ Components

✅ Standalone Components

✅ Templates & Interpolation

✅ Property Binding

✅ Event Binding

✅ Two-Way Binding

✅ Structural Directives

✅ Attribute Directives

✅ Pipes

✅ Custom Pipes

---

# Next Topic

➡️ Services

➡️ Dependency Injection

# Day 10 - Services & Dependency Injection 🚀

## Overview

Today we explored Services and Dependency Injection (DI) in Angular.

As applications grow, placing all logic inside components can make them difficult to maintain and reuse. Angular encourages moving business logic and data management into Services, allowing components to focus on rendering the UI.

Dependency Injection allows Angular to automatically provide required dependencies wherever they are needed.

---

# Project Used

```bash
angular-dashboard-app
```

---

# What Was Built

Created an Employee Service responsible for providing employee data and consumed it inside the Employee Profile component.

Benefits:

- Better separation of concerns
- Reusable business logic
- Cleaner components
- Improved maintainability

---

# Step 1 - Generate a Service

```bash
ng generate service services/employee
```

Short version:

```bash
ng g s services/employee
```

Angular creates:

```text
src/app/services/
└── employee.service.ts
```

---

# Step 2 - Create an Employee Model

Create:

```text
src/app/models/employee.ts
```

```ts
export interface Employee {
  id: number;
  name: string;
  designation: string;
  experience: number;
  salary: number;
}
```

Using an interface provides type safety and improves code readability.

---

# Step 3 - Create Employee Service

Open:

```text
src/app/services/employee.service.ts
```

```ts
import { Injectable } from '@angular/core';
import { Employee } from '../models/employee';

@Injectable({
  providedIn: 'root'
})
export class EmployeeService {

  getEmployee(): Employee {
    return {
      id: 101,
      name: 'Padma Gana',
      designation: 'Senior Frontend Developer',
      experience: 7,
      salary: 1200000
    };
  }

}
```

---

# Understanding @Injectable

```ts
@Injectable({
  providedIn: 'root'
})
```

This tells Angular to:

- Create a single instance of the service
- Make it available application-wide
- Manage the service lifecycle automatically

---

# Step 4 - Inject Service Using inject()

Open:

```text
src/app/components/user-card/user-card.ts
```

Import:

```ts
import { inject } from '@angular/core';
import { EmployeeService } from '../../services/employee.service';
import { Employee } from '../../models/employee';
```

Inject the service:

```ts
private readonly employeeService = inject(EmployeeService);
```

---

# Step 5 - Load Data from Service

```ts
import { Component, inject, OnInit } from '@angular/core';

export class UserCardComponent implements OnInit {

  private readonly employeeService = inject(EmployeeService);

  employee!: Employee;

  ngOnInit(): void {
    this.employee = this.employeeService.getEmployee();
  }

}
```

---

# Step 6 - Display Data

Open:

```text
src/app/components/user-card/user-card.html
```

```html
<div class="card">

  <h2>{{ employee.name }}</h2>

  <p>{{ employee.designation }}</p>

  <p>
    Experience:
    {{ employee.experience }} Years
  </p>

  <p>
    Salary:
    {{ employee.salary | currency:'INR' }}
  </p>

</div>
```

---

# Application Flow

```text
Employee Service
       │
       ▼
Provides Employee Data
       │
       ▼
Component Consumes Service
       │
       ▼
Template Displays Data
```

---

# Why Use Services?

Without Services:

```text
Component
 ├── UI Logic
 ├── Business Logic
 ├── Data Handling
 └── API Calls
```

Components become difficult to maintain.

With Services:

```text
Component
 └── UI Logic

Service
 ├── Business Logic
 ├── Data Handling
 └── API Calls
```

Responsibilities remain clearly separated.

---

# Understanding Dependency Injection

Modern Angular allows dependencies to be injected using:

```ts
private readonly employeeService =
  inject(EmployeeService);
```

instead of:

```ts
constructor(
  private employeeService: EmployeeService
) {}
```

Benefits:

- Cleaner code
- Less boilerplate
- Better readability
- Recommended in modern Angular applications

---

# Concepts Covered

## Service

```ts
EmployeeService
```

A reusable class that manages business logic and data.

---

## Dependency Injection

```ts
inject(EmployeeService)
```

Angular automatically provides the service instance.

---

## Type Safety

```ts
Employee
```

Using interfaces ensures data consistency and better developer experience.

---

# Final Output

✅ Generated Service using Angular CLI

✅ Created Employee Service

✅ Created Employee Model

✅ Used Dependency Injection

✅ Used inject() API

✅ Loaded Data from Service

✅ Separated Business Logic from UI

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

✅ Services

✅ Dependency Injection

---

# Next Topic

➡️ Routing Basics

➡️ Route Parameters

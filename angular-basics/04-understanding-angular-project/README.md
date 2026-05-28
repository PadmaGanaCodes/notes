# Understanding Angular Project Structure

After creating an Angular application using Angular CLI, several files and folders are generated automatically.

Initially, the structure may look confusing, but each file has a specific purpose that helps organize applications efficiently.

Angular follows a scalable and maintainable architecture, which is one of the biggest reasons it is widely used in enterprise applications.

---

# Angular Project Structure

```text
angular-dashboard-app/
│
├── src/
├── node_modules/
├── angular.json
├── package.json
├── tsconfig.json
```

---

# Important Folders & Files

## 1. src/

The main source code of the application exists inside the `src` folder.

Most application development happens here.

---

## 2. app/

Path:

```text
src/app/
```

Contains:
- components
- services
- routing
- business logic

This is the core application folder.

---

## 3. main.ts

The entry point of the Angular application.

Angular starts bootstrapping the application from this file.

---

## 4. index.html

Main HTML page loaded in the browser.

Angular components get rendered inside this page.

---

## 5. angular.json

Contains Angular project configuration such as:
- build setup
- assets
- styles
- scripts

---

## 6. package.json

Contains:
- dependencies
- scripts
- Angular package versions

Example:

```json
"dependencies": {
  "@angular/core": "^21.2.0"
}
```

---

## 7. node_modules/

Contains all installed dependencies and packages.

Automatically generated after running:

```bash
npm install
```

---

# Why Angular Project Structure Matters

Angular’s structured architecture helps with:
- scalability
- maintainability
- reusable code
- team collaboration
- enterprise application development

---

# Current Progress

✅ Angular Introduction  
✅ Angular Architecture  
✅ Angular Environment Setup  
✅ Angular Project Structure  

We are now ready to start building actual Angular components 🚀

---

# Next Topic

Creating Components in Angular 🔥

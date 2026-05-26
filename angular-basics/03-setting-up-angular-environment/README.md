# Setting Up Angular Environment 🚀

Before building Angular applications, the first step is setting up the development environment properly.

Angular provides a powerful CLI (Command Line Interface) that helps developers create, manage, and run applications much more efficiently.

With Angular CLI, many configurations are handled automatically, making development faster and smoother.

---

# 📌 Prerequisites

## 1. Install Node.js

Angular requires **Node.js** and **npm** to run.

Download and install Node.js from the official website:

https://nodejs.org/

After installation, verify it using:

```bash
node -v
npm -v
```

---

## 2. Install Angular CLI

Angular CLI is the official tool used to create and manage Angular projects.

Install Angular CLI globally using:

```bash
npm install -g @angular/cli
```

Verify the installation:

```bash
ng version
```

---

## 3. Recommended Code Editor

The recommended IDE for Angular development is:

- VS Code

Useful VS Code extensions:

- Angular Language Service
- ESLint
- Prettier
- GitLens

---

# 🚀 Creating Your First Angular Application

Create a new Angular project using:

```bash
ng new angular-dashboard-app
```

During setup, Angular CLI will ask a few questions like:

- Do you want routing?
- Which stylesheet format would you like to use?

### Recommended Options

- Routing → Yes
- Stylesheet → CSS

---

# 📂 Navigate Into the Project

```bash
cd angular-dashboard-app
```

---

# ▶️ Run the Angular Application

Start the development server:

```bash
ng serve
```

Once the server starts, open the application in your browser:

```text
http://localhost:4200
```

---

# ⚡ Why Angular CLI Is Powerful

Angular CLI automatically configures many important things for us, including:

- Project structure
- TypeScript setup
- Routing configuration
- Build configuration
- Environment setup
- Testing support
- Development server

This saves a lot of manual setup time and allows developers to focus more on building features.

---

# 📖 What’s Next?

In the upcoming topics, we’ll learn:

- Angular project structure
- Creating components
- Setting up routing
- Building reusable UI components
- Developing a real-world Angular dashboard application step by step

---
Next Topic

Creating Your First Angular Application 🚀

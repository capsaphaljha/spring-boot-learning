# Installation to first program in angluar


## installation in windows:

1. install the node js first
2. run below command to install the angular
   ```cmd
   npm install -g @angular/cli
   ```
4. run below to check the version and confirm the isntallation
  ```cmd
 ng version
```
6. if it will not shop the version or ng not found the run the install again and run the below command:
  ```cmd
[Environment]::SetEnvironmentVariable("Path", [Environment]::GetEnvironmentVariable("Path", "User") + ";" + (npm config get prefix), "User")

```

7. then again check the version, it will work and output will be like this:
![Uploading image.png…]()


## Before start the program lets some interesting facts about the spring boot:

Angular is preferred alongside Spring Boot for enterprise applications because both enforce strict architectural conventions, static typing, and built-in dependency injection, making large, multi-team codebases predictable and easy to maintain.
While React works well with Spring Boot and is widely used in enterprises, Angular mirrors Java and Spring Boot’s design philosophy much more closely.

1. Why Angular Pairs Naturally with Spring Boot (Java)

Java developers transitioning to or collaborating on the frontend find Angular familiar because both ecosystems share core engineering patterns:
• TypeScript vs. Java: Angular requires TypeScript, which brings static typing, interfaces, classes, and decorators (like @Component and @Injectable). This closely mirrors Java’s object-oriented structure and Spring Boot’s annotations (@RestController, @Service). React allows JavaScript or TypeScript, making typing optional.
• Built-in Dependency Injection (DI): Spring Boot is built around Inversion of Control (IoC) and Dependency Injection. Angular is the only major frontend framework with a native, hierarchical DI system built in, allowing developers to inject services into components the exact same way they inject repositories into Spring services.
• Consistent Mental Model: Because both frontend and backend follow OOP and modular patterns, full-stack Java/Angular teams can switch between layers without changing how they structure code.

# Why Enterprises Favor Angular Over React

| Feature | Angular (Full Framework) | React (UI Library) | Enterprise Impact |
| :--- | :--- | :--- | :--- |
| **Architecture & Structure** | **Opinionated:** Enforces a standard folder layout, CLI, and coding patterns across all apps. | **Flexible:** Teams must choose their own folder structure and state patterns. | New developers can join any Angular project and immediately understand where everything lives. |
| **Core Tooling** | **Batteries-included:** Routing, HTTP client, form validation, and testing tools come built in. | **Ecosystem-dependent:** Requires picking and maintaining third-party libraries (e.g., React Router, Axios, Redux). | Eliminates "decision fatigue" and prevents third-party library abandonment over a 5–10 year lifespan. |
| **Upgrades & Maintenance** | Synchronized major releases every 6 months with automated migration tools (`ng update`). | Core library updates are smooth, but third-party ecosystem packages often break or fall out of sync. | Predictable long-term maintenance and security patching for large enterprise systems. |
| **Complex Forms & Data** | Built-in **Reactive Forms** and **RxJS** for handling heavy data streams, complex validation, and real-time updates. | Requires external libraries (like React Hook Form + Zod + TanStack Query) to match the same capabilities. | Banking, insurance, and ERP apps rely heavily on massive, multi-step forms where Angular excels out of the box. |



## Start with the first program

- lets build a project first:

  ```cmd
  ng new auth-app
  ```

- run the project

```cmd
ng serve --open
```

### Now for features we have to build the components like modular system, command for creating auth component, this is custom component we are creating:
```cmd
ng generate component auth

```
this is a short command of this: "ng g c"

This will create a new custom module name "auth"

What just happened?
Angular created a folder src/app/terms/ with 4 files inside it:
• terms.component.html → Your HTML layout (what the user sees)
• terms.component.css → Your styling for this page
• terms.component.ts → The TypeScript class that controls this page
• terms.component.spec.ts → Automated tests (we can ignore this for now)


 

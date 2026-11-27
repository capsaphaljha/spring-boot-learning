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


## Start with the first program

- 


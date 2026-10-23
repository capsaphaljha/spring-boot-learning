# Spring boot

- Spring Boot is an extension of the Spring Framework that eliminates the boilerplate configuration of traditional Spring applications.
- It introduces 'starter' dependencies for quick setup, automatic configuration based on the classpath, and an embedded Tomcat server, enabling developers to build stand-alone, production-ready applications with minimal effort.

```java
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

// 1. Main class jahan se application start hoti hai
@SpringBootApplication
public class SpringBootBasicApplication {

    public static void main(String[] args) {
        // Embedded Tomcat server ko start karta hai aur Spring IoC container banata hai
        SpringApplication.run(SpringBootBasicApplication.class, args);
    }
}

// 2. Controller class jo HTTP requests ko handle karegi (Jaise Magento controllers)
@RestController
class WelcomeController {

    @GetMapping("/welcome")
    public String welcomeMessage() {
        return "Hello! Successfully transitioned from Magento to Spring Boot.";
    }
}
```

# What is springboot?	"
- Is a framwork for building java applications.
- It provid tools to make standalone production ready website
- Make application development easy
- less effors to setup and configurations
- No additional tomcat server required its inbuild in Springboot app"

# Annotation
IOC will conect object 
Wher to write: @component - this create beans
- Class
- Interphase
- Methods
- Fields"


# Application Context

Will provide exiting object i.e. bean - is the way to implement IOC contrainer
- ""Eager"" by default (creates all singleton beans at startup)."

# automatic component scanning	

# Embedded server configurations	

# Beans
Bean similar to Objeact creation - if any IOC container have the object information then that object called bean

# Maven	
maven is build tool, Make build

- manage dependencies
- Build life cycle defined - https://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html
- Install Maven to system and set env variable
- Spring boot also have mnnw same as Maven

# pom.xml

is the file to manage dependencies"

# Diff between  - JAR and WAR

Java Archive , Web Application Archive - 
JAR can run easly, WAR need deployment"

# IOC container - inversan of control	

"instead of self create object IOC container will create object for us:
car car = new car; // without spring
but in SB we ask IOC for objects lik below:
Externlise the object create, instead of creating ourself SB (IOC contrainer) will create the object 
if class content @component then IOC will keep this class object
Can be ""Lazy"" (only creates objects when requested)."

# IOC container - inversan of control	"Conbination for 2 annotation: - That folder will work as we close package so that beans will not work outside of that folder
- @configuration
- @AutoConfiguration
- @ConponentScan - Finding add component (@component) - scan beans"


<img width="344" height="256" alt="image" src="https://github.com/user-attachments/assets/baee2eb5-9107-4cdc-bde4-a02ff881f897" />

@Autowiring
- Is the way to call the object without create object using traditional method, this annotation will do it itself.
-
- In above screenshot example we did field injection (mainly dependy injectioin)
- As that Dog method has Component anntation so that it bean will be created for it


### @Configuration
### @AutoConfiguration
### @ConponentScan	
### @been	This annotation only work on function
### DI - dependency Injection
### HTTP Verv

REST API	Represantational (RE) state transfer - Application programming interphase
GET	View
PUT	Modify
POST	Create
DELETE	Delete


### POJO
Plan Old Java Object (geter seter enitity class)

# @restController	All endpoints auto return json type (even convert sttring type return to json)
# @RequestMapping("/customer"	path defining for a class, so all the rest methods will be access by using that class
# @GetMapping	For methods
# @PostMapping	
# @RequestBody	Its creating json data to java object from rest
"@RequestMapping(""/customer"") - CLASS
@GetMapping(""/getDAta"") - METHOD"	path - customer/getData

### @Autowiring
- Is the way to call the object without create object using traditional method, this annotation will do it itself.

### Inversion of Control\
- Inversion of Control is a design principle where the control of object creation and lifecycle is transferred from the application code to a container (the Spring IoC Container). Instead of a class creating its dependencies using new, the container injects them.

### Dependency Injection
- Dependency Injection is the actual mechanism used to implement IoC. It allows dependent objects to be passed into a class (via constructors, setters, or fields) rather than the class constructing them internally.

### Spring Bean
- A Spring Bean is simply an object that is instantiated, assembled, and managed by the Spring IoC Container. Beans are annotated with stereotypic annotations like @Component, @Service, @Repository, or @Bean, and the container handles their entire lifecycle.


### AOP (Aspect-Oriented Programming)
- AOP is a programming paradigm that allows developers to modularize Cross-Cutting Concerns—functionality that spans multiple layers of an application, such as security, logging, transaction management, and performance monitoring—without cluttering the core business logic.

### Spring Data JPA
- Spring Data JPA is an abstraction layer built on top of JPA. It significantly reduces boilerplate data-access code by providing ready-to-use repository interfaces like JpaRepository, supporting built-in pagination, and automatically generating SQL queries based on method name conventions.

### Spring Security Filter Chain
- The Spring Security Filter Chain is a sequence of servlet filters that intercepts every incoming HTTP request. Each filter in the chain performs a specific security task—such as CSRF protection, session management, or validating a custom JWT token—before passing the request to the next filter or controller.

### "HikariCP 
- is a high-performance, lightweight JDBC connection pool that comes as the default connection manager in Spring Boot. It minimizes the overhead of opening and closing database connections by maintaining a pool of active, reusable connections ready to serve incoming requests instantly.

### Spring Boot Actuator
- Spring Boot Actuator is a sub-project that brings production-ready monitoring and management features to your application. It exposes built-in HTTP endpoints (such as /health, /metrics, and /env) that allow developers to inspect application health, memory usage, and database connectivity in real-time.

### Lombok Library
- Project Lombok is a Java library that plugs into your build tool and editor to automatically generate boilerplate code through annotations. Annotations like @Getter, @Setter, @ToString, and @Data reduce code verbosity by auto-generating accessors, constructors, and utility methods at compile time.

### Mockito
For mock the classes for testing

### Log
Log Back
SLF 4J 

### external api calling 
Rest template

### bean
banane k liye hamne ye 3 annotation abou tak use kiya hai	

"Component
Controller
rest controller"


### Cron
@schedules annotation


###

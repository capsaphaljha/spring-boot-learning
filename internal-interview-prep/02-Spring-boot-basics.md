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





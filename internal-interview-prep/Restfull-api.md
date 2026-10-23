
# RESTful API

- A RESTful API in Spring Boot is built using @RestController which automatically serializes Java objects into JSON using Jackson.
- We map HTTP methods using annotations like @GetMapping, @PostMapping,
- Extract request data using @PathVariable for URL segments,
- @RequestParam for query parameters, and @RequestBody for JSON payloads.
- Proper exception handling is typically managed globally using @RestControllerAdvice to ensure uniform error responses.

```java
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/api/products") // Base URL for all methods in this controller
public class ProductController {

    // 1. GET Request: Saare products ya query param se filter karna
    // URL: GET /api/products?category=electronics
    @GetMapping
    public ResponseEntity<List<String>> getAllProducts(@RequestParam(required = false) String category) {
        List<String> products = List.of("Laptop", "Smartphone", "Headphones");
        // ResponseEntity se hum HTTP status code (200 OK) ke sath response bhejte hain
        return new ResponseEntity<>(products, HttpStatus.OK);
    }

    // 2. GET Request with Path Variable
    // URL: GET /api/products/5
    @GetMapping("/{id}")
    public ResponseEntity<String> getProductById(@PathVariable Long id) {
        String product = "Laptop with ID: " + id;
        return ResponseEntity.ok(product); // ResponseEntity.ok() returns 200 OK
    }

    // 3. POST Request: Naya resource create karna
    // URL: POST /api/products
    @PostMapping
    public ResponseEntity<String> createProduct(@RequestBody ProductDto newProduct) {
        // Database save logic here...
        // Successfully create hone par 201 Created status code return karte hain
        return new ResponseEntity<>("Product created successfully!", HttpStatus.CREATED);
    }
}

// Simple Data Transfer Object (DTO) for request body
class ProductDto {
    private String name;
    private double price;

    // Getters and Setters
    public String getName() { return name; }
    public double getPrice() { return price; }
}

```



- @RestController will use to create rest apis

- Stateless Communication - no session used in this request

HTTP Methods: Sahi action ke liye sahi method use karna:
GET: Data fetch karne ke liye (e.g., get product details).
POST: Naya data create karne ke liye (e.g., create a new product).
PUT / PATCH: Existing data update karne ke liye.
DELETE: Data delete karne ke liye.

- Standard HTTP Status Codes:

200 OK: Success (GET/PUT)
201 Created: Naya resource successfully ban gaya (POST)
400 Bad Request: Client ki taraf se bheja gaya data galat hai.
401 Unauthorized: Token missing ya invalid hai.
403 Forbidden: User authenticated hai par uske paas permission nahi hai.
404 Not Found: Resource nahi mila.
500 Internal Server Error: Server par unexpected error aa gaya.

# Spring Security & Authentication (Auth)

Spring Security is a powerful framework that provides authentication, authorization, and protection against common vulnerabilities. For RESTful APIs, we typically implement stateless authentication using JSON Web Tokens (JWT). The architecture relies on a custom OncePerRequestFilter that intercepts incoming requests, validates the JWT from the Authorization header, and populates the SecurityContext so that Spring knows the user is authenticated.

```java

import jakarta.servlet.FilterChain;
import jakarta.servlet.ServletException;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.security.web.authentication.WebAuthenticationDetailsSource;
import org.springframework.web.filter.OncePerRequestFilter;
import java.io.IOException;

public class JwtAuthenticationFilter extends OncePerRequestFilter {

    @Override
    protected void doFilterInternal(HttpServletRequest request, 
                                    HttpServletResponse response, 
                                    FilterChain filterChain) throws ServletException, IOException {
        
        // 1. Authorization header nikalna
        String authHeader = request.getHeader("Authorization");
        String token = null;
        String username = null;

        // 2. Check karna ki header 'Bearer ' se shuru ho raha hai ya nahi
        if (authHeader != null && authHeader.startsWith("Bearer ")) {
            token = authHeader.substring(7); // "Bearer " ke baad ka token part
            // username = jwtService.extractUsername(token); (Token se username decode karna)
        }

        // 3. Agar token valid hai aur Security Context abhi empty hai
        if (username != null && SecurityContextHolder.getContext().getAuthentication() == null) {
            
            // User ko authenticate karke Spring Security context mein set karna
            UsernamePasswordAuthenticationToken authToken = 
                new UsernamePasswordAuthenticationToken(username, null, null);
            
            authToken.setDetails(new WebAuthenticationDetailsSource().buildDetails(request));
            
            // Yahan Spring ko pata chal jata hai ki user authenticated hai
            SecurityContextHolder.getContext().setAuthentication(authToken);
        }

        // 4. Aage ke filters par request pass karna
        filterChain.doFilter(request, response);
    }
}

```


Key Interview Points to Remember:
Stateless vs Stateful: Spring Security by default HttpSession use karti hai (Stateful). JWT ke sath humein configuration mein session policy ko SessionCreationPolicy.STATELESS set karna padta hai taaki server koi session store na kare.

Password Encoding: Kabhi bhi plain text passwords database mein store nahi kiye jaate; hamesha BCryptPasswordEncoder ka use kiya jata hai.

## Spring Security
The Filter Chain


## Authentication (Auth)


## JWT (JSON Web Token) - Stateless JWT Authentication

JWT (JSON Web Token) is a compact, URL-safe means of representing claims to be transferred between two parties. 
Because it is digitally signed and self-contained, the server can authenticate requests statelessly without querying the database for session data on every request.

spring boot - Java JWT  library (jjwt)

```java
Jwts.builder()
                .setSubject(username) // User ka naam/email daala
                .setIssuedAt(new Date(System.currentTimeMillis())) // Aaj ka time
                .setExpiration(new Date(System.currentTimeMillis() + 1000 * 60 * 60 * 10)) // 10 ghante baad expire hoga
                .signWith(getSignKey(), SignatureAlgorithm.HS256) // Secret key se sign kiya
                .compact();

```




3 Parts - secret key: 

Header . Payload . Signature

Example 

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiJhbWFuQGV4YW1wbGUuY29tIiwiaWF0IjoxNzM1NzA0MDAwLCJleHAiOjE3MzU3MDc2MDB9.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c

base64 encrypted

{
  "sub": "aman@example.com",
  "iat": 1735704000,
  "exp": 1735707600
}


- sub: Subject (User ka email/username)
- iat: Issued At (Kab token bana)
- exp: Expiration Time (Token kab expire hoga)

JWT Authentication ka Poora Flow
Login: User apna username aur password /api/login par bhejta hai.

Verification: Server database mein check karta hai. Agar details sahi hain, toh server ek JWT token generate karta hai aur user ko waping bhej deta hai.

Storing: Client (Frontend/React/Postman) us token ko LocalStorage ya SessionStorage mein save kar leta hai.

Authorized Request: Jab bhi user koi protected API (jaise /api/profile) call karta hai, toh woh request ke headers mein token bhejta hai:Authorization: Bearer <JWT_TOKEN>

Validation: Server token ka signature check karta hai, dekhta hai ki token expire toh nahi hua, aur user ko data de deta hai. Server ko database mein session save karne ki koi zaroorat nahi padti (Stateless).

--

# Role base 

- Yes, Spring Security provides native support for Role-Based Access Control (RBAC) using GrantedAuthority and annotations like @PreAuthorize.
- However, when using stateless JWT authentication, we customize the flow by embedding the user's roles inside the JWT payload (claims) on login.
- During subsequent requests, our custom filter extracts those roles, converts them into GrantedAuthority objects, and populates the SecurityContext, allowing Spring Security to seamlessly enforce role-based access rules at the URL or method level.

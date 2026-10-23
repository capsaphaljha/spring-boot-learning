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


## Spring Security
The Filter Chain


## Authentication (Auth)


## JWT (JSON Web Token) - Stateless JWT Authentication



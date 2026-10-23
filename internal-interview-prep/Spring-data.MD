#Spring data:

Spring Data JPA provides advanced mechanisms like built-in pagination and sorting using Pageable and Page interfaces to handle large datasets efficiently. For complex business requirements, we can write custom queries using the @Query annotation with either JPQL or native SQL. Additionally, Spring Data supports projections to fetch only required columns, which significantly optimizes database performance.

- JpaRepository - service contract - save/find/delete operations

- Pageable - Interface to get data in chunks

- Page - page object will return total pages

- Custom Queries (@Query Annotation)
JPQL (Java Persistence Query Language): Yeh database-independent hoti hai aur Java classes/entities par kaam karti hai (e.g., SELECT p FROM Product p WHERE p.price > :price).

Native SQL: Agar aapko direct database ki table par SQL query chalani hai, toh aap nativeQuery = true set kar sakte hain.

- Projections (Performance Optimization)

```java

import org.springframework.data.domain.Page;
import org.springframework.data.domain.Pageable;
import org.springframework.data.jpa.repository.JpaRepository;
import org.springframework.data.jpa.repository.Query;
import org.springframework.data.repository.query.Param;
import org.springframework.stereotype.Repository;

import java.util.List;

@Repository
interface ProductRepository extends JpaRepository<Product, Long> {

    // 1. Pagination & Sorting example
    // Yeh method automatically page number, page size, aur sorting handle karega
    Page<Product> findByPriceLessThan(double price, Pageable pageable);

    // 2. Custom JPQL Query example (@Query annotation)
    @Query("SELECT p FROM Product p WHERE p.department = :dept AND p.price > :minPrice")
    List<Product> findExpensiveProductsByDept(@Param("dept") String department, 
                                              @Param("minPrice") double minPrice);
}


```

# Page vs Slice: 

- Page total count bhi nikalta hai (jiske liye extra COUNT query chalani padti hai),
- jabki Slice sirf yeh batata hai ki agla page available hai ya nahi (jo fast hota hai).

# @Transactional: 

- The @Transactional annotation is used to declaratively manage transaction boundaries in Spring applications. It ensures that a group of database operations execute within a single transaction following ACID (Atomicity, Consistency, Isolation, and Durability) properties. 
- If all operations succeed, the transaction is committed; if a runtime exception occurs, Spring automatically rolls back all changes to maintain data integrity.

- Data modifying queries (UPDATE ya DELETE) ke sath repository method par @Transactional lagana zaroori hota hai.

Default Rollback Rule (The Trap ⚠️):

By default, @Transactional sirf RuntimeException (aur uske sub-classes) ya Error par hi rollback karta hai.

Agar aapke method mein koi Checked Exception (jaise IOException ya koi custom checked exception) aa jati hai, toh Spring rollback nahi karega.

Solution: Agar aapko har exception par rollback karwana hai, toh aapko likhna padta hai: @Transactional(rollbackFor = Exception.class)

4. Interview ke 3 Sabse Important Deep-Dive Points (Yeh zaroor sunna chahte hain interviewer):
Default Rollback Rule (The Trap ⚠️):

By default, @Transactional sirf RuntimeException (aur uske sub-classes) ya Error par hi rollback karta hai.

Agar aapke method mein koi Checked Exception (jaise IOException ya koi custom checked exception) aa jati hai, toh Spring rollback nahi karega.

Solution: Agar aapko har exception par rollback karwana hai, toh aapko likhna padta hai: @Transactional(rollbackFor = Exception.class)

readOnly = true (Performance Optimization):

Agar aapka method sirf database se data read kar raha hai (SELECT queries chala raha hai, jaise getUserById), toh aapko likhna chahiye: @Transactional(readOnly = true).

Isse database ko pata chal jata hai ki koi modification nahi hone wali, jisse woh performance ko optimize kar deta hai (locking ki zaroorat nahi padti).

Under the Hood (AOP & Proxies):

Spring @Transactional ko implement karne ke liye AOP (Aspect-Oriented Programming) aur Proxies ka use karta hai. Jab aap kisi transactional method ko call karte hain, toh Spring ka proxy object pehle transaction open karta hai, fir aapka method chalata hai, aur baad mein commit/rollback handle karta hai.



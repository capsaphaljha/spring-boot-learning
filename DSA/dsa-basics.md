# Data Structures

- Data structures are ways to store and organize data so you can use it efficiently.
- An array is an example of a data structure, which allows multiple elements to be stored in a single variable.


Category	Matlab	Main Data Structures
1. Linear Data Structures - Data ek line (sequence) mein ek ke baad ek store hota hai.
- Array, Linked List, Stack, Queue
3. Non-Linear Data Structures	- Data hierarchy ya network ke roop mein store hota hai (ek ke andar kai branches).
- Tree, Graph, HashMap / HashTable



# Java Data Structures & DSA — Complete Study Notes

## 1. Data Structures Ka Overview (Core Categories)

Data Structure ka matlab hai data ko computer ki memory (RAM) mein is tarah organize karna ki usse **search, insert, update, aur delete** karna sabse fast ho.

| Category | Matlab | Main Data Structures |
| :--- | :--- | :--- |
| **Linear** | Data ek sequence (line) mein store hota hai. | Array, ArrayList, LinkedList, Stack, Queue |
| **Non-Linear** | Data hierarchy ya network ke roop mein store hota hai. | HashMap, HashSet, Tree, Graph, Heap |

---

## 2. Java Collections Framework (W3Schools Topics + Internal Details)

Java mein ready-made data structures `java.util` package mein milte hain:

| Data Structure | Kya Store Karta Hai? | Order Maintain Karta Hai? | Duplicates Allowed? | Time Complexity (Search / Access) | Kab Use Karein? |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Array** | Fixed-size elements | Haan (Index based) | Haan | `O(1)` (Index se) | Jab size pehle se fix ho aur fast access chahiye. |
| **ArrayList** | Resizable array | Haan (Insertion order) | Haan | `O(1)` (Get by index) | Jab data baar-baar read karna ho, size fix na ho. |
| **LinkedList** | Nodes (Data + Next pointer) | Haan (Insertion order) | Haan | `O(n)` (Search) / `O(1)` (Insert/Delete) | Jab list ke beech mein baar-baar insert/delete karna ho. |
| **HashSet** | Sirf Unique elements | Nahi (Random order) | **Nahi** | `O(1)` (Average) | Jab duplicates hatane hon aur fast check (`contains`) chahiye. |
| **TreeSet** | Unique + Sorted elements | Haan (Ascending order) | **Nahi** | `O(log n)` | Jab unique data automatically sorted chahiye. |
| **HashMap** | Key-Value pairs (`K, V`) | Nahi | Keys: **Nahi**, Values: Haan | `O(1)` (Average) | Jab kisi unique ID/Key se fast data dhoondhna ho. |
| **TreeMap** | Sorted Key-Value pairs | Haan (Keys ke hisaab se sorted) | Keys: **Nahi**, Values: Haan | `O(log n)` | Jab Key-Value data sorted order mein chahiye. |

---

## 3. Jo W3Schools Ke Java Page Par Missing Hai (Important Core DSA)

Interviews aur asli logic building ke liye ye 4 concepts seekhna bahut zaroori hai:

### A. Time & Space Complexity (Big-O Notation)
Yeh batata hai ki input badhne par code kitna slow hoga:
* **`O(1)` (Constant):** Sabse fast (e.g., Array index access, HashMap `get()`).
* **`O(log n)` (Logarithmic):** Bahut fast, har step mein data aadha hota hai (e.g., Binary Search, TreeMap).
* **`O(n)` (Linear):** Data ke saath time barabar badhta hai (e.g., Ek `for` loop chalana).
* **`O(n²)` (Quadratic):** Slow, nested loops mein hota hai (e.g., Loop ke andar loop).

### B. Stack aur Queue (Linear Structures)
* **Stack (LIFO - Last In, First Out):** Jo sabse aakhir mein gaya, wo sabse pehle bahar aayega (Jaise plates ka dher).
  * *Java Class:* `Stack<Integer>` ya `ArrayDeque<Integer>`
  * *Use Case:* Undo/Redo button, Browser Back button.
* **Queue (FIFO - First In, First Out):** Jo sabse pehle aaya, wo sabse pehle bahar aayega (Jaise ticket line).
  * *Java Class:* `Queue<Integer> q = new LinkedList<>()` ya `PriorityQueue<Integer>`
  * *Use Case:* Printer queue, Order processing.

### C. Non-Linear Data Structures (Trees & Graphs)
* **Binary Tree / BST (Binary Search Tree):** Ek parent node aur uske max 2 child nodes (Left chhota, Right bada). Searching bahut fast hoti hai.
* **Graph:** Nodes (Vertices) aur unhe jodne wale raste (Edges). Google Maps aur Social Media networks isi par chalte hain.

---

## 4. Quick Code Cheat-Sheet (Java Syntax)

```java
import java.util.*;

public class DSACheatSheet {
    public static void main(String[] args) {
        
        // 1. ArrayList (Dynamic Array)
        List<String> list = new ArrayList<>();
        list.add("Java");
        list.get(0); // Index se access

        // 2. HashSet (No Duplicates)
        Set<Integer> set = new HashSet<>();
        set.add(10);
        set.add(10); // Ignore ho jayega
        set.contains(10); // Fast check -> true

        // 3. HashMap (Key-Value)
        Map<String, Integer> map = new HashMap<>();
        map.put("Alice", 95);
        map.get("Alice"); // Output: 95

        // 4. Stack (LIFO)
        Deque<String> stack = new ArrayDeque<>();
        stack.push("Page 1");
        stack.push("Page 2");
        stack.pop(); // "Page 2" bahar aayega

        // 5. Queue (FIFO)
        Queue<String> queue = new LinkedList<>();
        queue.offer("Customer 1");
        queue.offer("Customer 2");
        queue.poll(); // "Customer 1" bahar aayega
    }
}
```

---

### 
```txt
 Big-O Notation ek mathematical tareeka hai jo yeh batata hai ki jab input data (n) bahut bada ho jaaye, toh aapka code kitna time (Time Complexity) aur kitni memory (Space Complexity) lega.
```

# Collections Framework

-  Collections Framework provides a set of interfaces (like List, Set, and Map) and a set of classes (ArrayList, HashSet, HashMap, etc.) that implement those interfaces.
-  All of these are part of the java.util package.
-  They are used to store, search, sort, and organize data more easily - all using standardized methods and patterns.

Core Interfaces in the Collections Framework
Here are some common interfaces, along with their classes:

Interface	Common Classes	Description
List	ArrayList, LinkedList	Ordered collection that allows duplicates
Set	HashSet, TreeSet, LinkedHashSet	Collection of unique elements
Map	HashMap, TreeMap, LinkedHashMap	Stores key-value pairs with unique keys

The table below gives an overview of the common data structure classes and their characteristics:

<img width="1277" height="535" alt="image" src="https://github.com/user-attachments/assets/dda849e4-df64-41a0-bd9d-e585df437285" />


## List Interface

- represents an ordered collection of elements.

Since List is an interface, you cannot create a List object directly.

Instead, you use a class that implements the List interface, such as:

ArrayList - like a resizable array with fast random access
LinkedList - like a train of cars you can easily attach or remove



# Iterator
An Iterator is an object that can be used to loop through collections, like ArrayList and HashSet.

It is called an "iterator" because "iterating" is the technical term for looping.

To use an Iterator, you must import it from the java.util package.

```java
// Import the ArrayList class and the Iterator class
import java.util.ArrayList;
import java.util.Iterator;

public class Main {
  public static void main(String[] args) {

    // Make a collection
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");

    // Get the iterator
    Iterator<String> it = cars.iterator();

    // Print the first item
    System.out.println(it.next());
  }
}
------------
while(it.hasNext()) {
  System.out.println(it.next());
}

```



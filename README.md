# COLLECTIONS-IN-JAVA

In Java, **collections** are data structures that store and manage groups of objects. The Java Collections Framework (JCF) provides a set of classes and interfaces that allow developers to work with different types of collections easily and efficiently. It includes several interfaces, classes, and algorithms to work with groups of objects, such as lists, sets, maps, and queues.

### **Key Interfaces in the Java Collections Framework:**

1. **Collection Interface**:
   - The root of the collections hierarchy. It provides common methods like `add()`, `remove()`, `clear()`, etc. Subinterfaces include `List`, `Set`, and `Queue`.

2. **List Interface**:
   - **List** is an ordered collection that allows duplicates and provides access by index.
   - Implementations: 
     - **ArrayList**: Resizable array implementation.
     - **LinkedList**: Doubly linked list implementation.
     - **Vector**: Synchronized version of `ArrayList`, usually avoided for performance reasons.
   - Example:
     ```java
     List<String> list = new ArrayList<>();
     list.add("Apple");
     list.add("Banana");
     list.add("Orange");
     ```

3. **Set Interface**:
   - **Set** represents an unordered collection that does **not allow duplicates**.
   - Implementations:
     - **HashSet**: Implements a set using a hash table. It is unordered.
     - **LinkedHashSet**: Ordered version of `HashSet` that maintains insertion order.
     - **TreeSet**: A set that stores elements in a sorted (natural or custom) order.
   - Example:
     ```java
     Set<String> set = new HashSet<>();
     set.add("Apple");
     set.add("Banana");
     set.add("Apple");  // Duplicate, won't be added
     ```

4. **Map Interface**:
   - **Map** stores key-value pairs. It doesn’t extend `Collection`, but it is part of the collections framework.
   - Implementations:
     - **HashMap**: Unordered key-value store backed by a hash table.
     - **LinkedHashMap**: Maintains insertion order.
     - **TreeMap**: Sorted map based on natural ordering or a custom comparator.
     - **Hashtable**: Similar to `HashMap` but synchronized.
   - Example:
     ```java
     Map<Integer, String> map = new HashMap<>();
     map.put(1, "One");
     map.put(2, "Two");
     map.put(3, "Three");
     ```

5. **Queue Interface**:
   - **Queue** is a collection that orders elements in a **FIFO (First In, First Out)** manner.
   - Implementations:
     - **PriorityQueue**: Elements are ordered based on their priority, not insertion order.
     - **LinkedList**: Can be used as a queue because it implements both `List` and `Queue`.
   - Example:
     ```java
     Queue<String> queue = new LinkedList<>();
     queue.add("First");
     queue.add("Second");
     queue.add("Third");
     ```

6. **Deque Interface**:
   - **Deque** (Double-Ended Queue) allows adding/removing elements from both ends.
   - Implementations:
     - **ArrayDeque**: Resizable array implementation of `Deque`.
   - Example:
     ```java
     Deque<String> deque = new ArrayDeque<>();
     deque.addFirst("Start");
     deque.addLast("End");
     ```

---

### **Common Classes in the Java Collections Framework:**

- **ArrayList**: Resizable array, allows fast random access but slower for insertions and deletions.
- **LinkedList**: Linked list, provides faster insertions/deletions but slower access by index.
- **HashSet**: Fast, unordered collection of unique elements.
- **TreeSet**: Sorted collection of unique elements.
- **HashMap**: Unordered map of key-value pairs, fast for lookups.
- **TreeMap**: Sorted map of key-value pairs.

### **Utility Class:**

- **Collections Class**:
   - This class contains static methods that operate on collections, like sorting, searching, shuffling, reversing, etc.
   - Example:
     ```java
     Collections.sort(list);  // Sort a list
     ```

---

### **Example Usage**:

Here is an example showing different collections:

```java
import java.util.*;

public class CollectionsExample {
    public static void main(String[] args) {
        // List example (allows duplicates)
        List<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Banana");
        System.out.println("List: " + list);

        // Set example (no duplicates)
        Set<String> set = new HashSet<>(list);
        System.out.println("Set: " + set);

        // Map example (key-value pairs)
        Map<Integer, String> map = new HashMap<>();
        map.put(1, "One");
        map.put(2, "Two");
        System.out.println("Map: " + map);

        // Queue example (FIFO)
        Queue<String> queue = new LinkedList<>();
        queue.add("First");
        queue.add("Second");
        System.out.println("Queue: " + queue);

        // Deque example (Double-Ended Queue)
        Deque<String> deque = new ArrayDeque<>();
        deque.addFirst("Start");
        deque.addLast("End");
        System.out.println("Deque: " + deque);
    }
}
```

### **Advantages of the Java Collections Framework:**
- **Reusable Data Structures**: You can use and extend many standard data structures without writing custom implementations.
- **Reduced Programming Effort**: The framework provides a standard set of classes and interfaces, reducing the need to write complex data structures from scratch.
- **Interoperability**: The standard interfaces (`List`, `Set`, `Map`, etc.) make it easier for different collection types to work together.

---

### **Comparison Between Common Collection Types:**

| Collection Type | Allows Duplicates | Ordered | Key-Value Pair |
|-----------------|-------------------|---------|----------------|
| **List**        | Yes               | Yes     | No             |
| **Set**         | No                | No (HashSet) / Yes (TreeSet) | No             |
| **Map**         | No (for keys)     | No (HashMap) / Yes (TreeMap) | Yes            |
| **Queue**       | Yes               | Yes (FIFO) | No             |





In Java, `ArrayList` is a part of the `java.util` package, which is a resizable array implementation of the `List` interface. It provides various methods for manipulating the size and elements of the list. Below are the most commonly used methods in `ArrayList`:

### **Basic Methods:**

1. **`add(E element)`**  
   Adds the specified element to the end of the list.
   ```java
   ArrayList<String> list = new ArrayList<>();
   list.add("Hello");
   ```

2. **`add(int index, E element)`**  
   Inserts the specified element at the specified position in the list.
   ```java
   list.add(1, "World");
   ```

3. **`get(int index)`**  
   Returns the element at the specified position in the list.
   ```java
   String item = list.get(0);  // "Hello"
   ```

4. **`set(int index, E element)`**  
   Replaces the element at the specified position with the specified element.
   ```java
   list.set(1, "Java");  // Replaces "World" with "Java"
   ```

5. **`remove(int index)`**  
   Removes the element at the specified position in the list.
   ```java
   list.remove(0);  // Removes "Hello"
   ```

6. **`remove(Object o)`**  
   Removes the first occurrence of the specified element from the list.
   ```java
   list.remove("Java");
   ```

7. **`clear()`**  
   Removes all elements from the list.
   ```java
   list.clear();
   ```

8. **`size()`**  
   Returns the number of elements in the list.
   ```java
   int size = list.size();
   ```

9. **`isEmpty()`**  
   Checks if the list is empty.
   ```java
   boolean empty = list.isEmpty();
   ```

10. **`contains(Object o)`**  
    Returns `true` if the list contains the specified element.
    ```java
    boolean contains = list.contains("Java");
    ```

### **Advanced Methods:**

1. **`indexOf(Object o)`**  
   Returns the index of the first occurrence of the specified element in the list, or `-1` if the list does not contain the element.
   ```java
   int index = list.indexOf("Java");
   ```

2. **`lastIndexOf(Object o)`**  
   Returns the index of the last occurrence of the specified element in the list, or `-1` if the list does not contain the element.
   ```java
   int lastIndex = list.lastIndexOf("Java");
   ```

3. **`addAll(Collection<? extends E> c)`**  
   Appends all elements in the specified collection to the end of the list.
   ```java
   ArrayList<String> newList = new ArrayList<>();
   newList.add("Python");
   list.addAll(newList);
   ```

4. **`addAll(int index, Collection<? extends E> c)`**  
   Inserts all elements from the specified collection starting from a specific index.
   ```java
   list.addAll(1, newList);
   ```

5. **`subList(int fromIndex, int toIndex)`**  
   Returns a view of the portion of the list between the specified `fromIndex` (inclusive) and `toIndex` (exclusive).
   ```java
   List<String> subList = list.subList(1, 3);
   ```

6. **`toArray()`**  
   Converts the list into an array.
   ```java
   Object[] array = list.toArray();
   ```

7. **`toArray(T[] a)`**  
   Returns an array containing all elements in the list in the correct order.  
   ```java
   String[] array = list.toArray(new String[0]);
   ```

### **Iterating through an ArrayList:**

1. **Using a `for` loop:**
   ```java
   for (int i = 0; i < list.size(); i++) {
       System.out.println(list.get(i));
   }
   ```

2. **Using an enhanced `for` loop:**
   ```java
   for (String s : list) {
       System.out.println(s);
   }
   ```

3. **Using an `Iterator`:**
   ```java
   Iterator<String> iterator = list.iterator();
   while (iterator.hasNext()) {
       System.out.println(iterator.next());
   }
   ```


   To sort an `ArrayList` in Java, you can use the `Collections.sort()` method or the `List.sort()` method (introduced in Java 8). These methods can sort the `ArrayList` in natural order or according to a custom comparator.

### **1. Sorting in Natural Order**

For an `ArrayList` of elements that implement `Comparable` (like `String`, `Integer`, `Double`, etc.), you can directly use `Collections.sort()` or `List.sort()` to sort the list in ascending order.

#### **Example: Sorting an ArrayList of Strings**
```java
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Banana");
        list.add("Apple");
        list.add("Mango");

        // Sorting in natural (ascending) order
        Collections.sort(list);

        System.out.println(list);  // Output: [Apple, Banana, Mango]
    }
}
```

### **2. Sorting in Reverse Order**

To sort in reverse (descending) order, you can use the `Collections.reverseOrder()` method with `Collections.sort()`.

#### **Example: Sorting an ArrayList of Strings in Reverse Order**
```java
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Banana");
        list.add("Apple");
        list.add("Mango");

        // Sorting in reverse (descending) order
        Collections.sort(list, Collections.reverseOrder());

        System.out.println(list);  // Output: [Mango, Banana, Apple]
    }
}
```

### **3. Sorting with Custom Comparator**

You can also sort an `ArrayList` using a custom comparator if you need a specific order, such as sorting by the length of strings or other properties of objects.

#### **Example: Sorting Strings by Length**
```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Banana");
        list.add("Apple");
        list.add("Mango");

        // Sorting strings by their length
        Collections.sort(list, new Comparator<String>() {
            @Override
            public int compare(String s1, String s2) {
                return Integer.compare(s1.length(), s2.length());
            }
        });

        System.out.println(list);  // Output: [Apple, Mango, Banana]
    }
}
```

### **4. Sorting Using Java 8 `List.sort()` (Lambda Expressions)**

With Java 8 and above, you can use lambda expressions to simplify sorting with a custom comparator.

#### **Example: Sorting Strings by Length Using Lambda**
```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Banana");
        list.add("Apple");
        list.add("Mango");

        // Sorting strings by length using lambda
        list.sort((s1, s2) -> Integer.compare(s1.length(), s2.length()));

        System.out.println(list);  // Output: [Apple, Mango, Banana]
    }
}
```

### **5. Sorting an ArrayList of Custom Objects**

If you have an `ArrayList` of custom objects, you can sort it using a comparator that compares object properties.

#### **Example: Sorting an ArrayList of Custom Objects**

```java
import java.util.ArrayList;
import java.util.Collections;

class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return name + " (" + age + ")";
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Person> people = new ArrayList<>();
        people.add(new Person("Alice", 25));
        people.add(new Person("Bob", 20));
        people.add(new Person("Charlie", 23));

        // Sorting by age
        Collections.sort(people, (p1, p2) -> Integer.compare(p1.age, p2.age));

        System.out.println(people);  // Output: [Bob (20), Charlie (23), Alice (25)]
    }
}
```

### Summary of Sorting Methods:
- **`Collections.sort(list)`**: Sorts in ascending order (natural order).
- **`Collections.sort(list, Collections.reverseOrder())`**: Sorts in descending order.
- **Custom Comparators**: Sort using a comparator based on custom properties.
- **Lambda Expressions (Java 8+)**: A more concise way to sort lists with custom logic.

This should cover most of the ways you'll sort `ArrayList` in Java!

4. **Using Java 8+ `forEach`:**
   ```java
   list.forEach(System.out::println);
   ```

`ArrayList` provides dynamic resizing and ensures the order of elements, making it a flexible data structure for many use cases.



-------------------------------------------------------------------------------------------------


Yes, Saiful! There are multiple ways to sort an `ArrayList` of custom objects in Java. You've already seen how to use `Comparator` with lambdas and anonymous classes. Another common way is by implementing the `Comparable` interface. This allows you to define a "natural" sorting order for your objects. Additionally, you can still use `Streams` (introduced in Java 8) for sorting in a more functional programming style.

### **1. Using `Comparable` Interface**

By implementing the `Comparable` interface in your custom class, you define a natural order for that class. You override the `compareTo` method to specify the sorting logic.

#### **Example: Sorting by Age Using `Comparable`**

```java
class Person implements Comparable<Person> {
    String name;
    int age;

    // Constructor
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Overriding compareTo method to sort by age
    @Override
    public int compareTo(Person other) {
        return Integer.compare(this.age, other.age); // Ascending order by age
    }

    @Override
    public String toString() {
        return name + " (" + age + ")";
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Person> people = new ArrayList<>();
        people.add(new Person("Alice", 25));
        people.add(new Person("Bob", 20));
        people.add(new Person("Charlie", 23));

        // Sorting based on the natural ordering defined in compareTo (by age)
        Collections.sort(people);

        // Print sorted list
        System.out.println("Sorted by age:");
        for (Person person : people) {
            System.out.println(person);
        }
    }
}
```

### **Output:**
```
Sorted by age:
Bob (20)
Charlie (23)
Alice (25)
```

### **Advantages of `Comparable`:**
- The sorting logic is encapsulated within the class itself, meaning any `Person` object will be sorted the same way by default.
- Use `Collections.sort(list)` or `list.sort()` without passing a `Comparator`.

### **2. Sorting Using `Streams` (Java 8+)**

Java 8 introduced the `Stream` API, which allows you to sort an `ArrayList` using a more declarative, functional approach. This can be done using the `sorted()` method.

#### **Example: Sorting Using Streams**

```java
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return name + " (" + age + ")";
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Person> people = new ArrayList<>();
        people.add(new Person("Alice", 25));
        people.add(new Person("Bob", 20));
        people.add(new Person("Charlie", 23));

        // Sorting by age using streams
        List<Person> sortedByAge = people.stream()
                .sorted((p1, p2) -> Integer.compare(p1.age, p2.age))
                .collect(Collectors.toList());

        // Print sorted list by age
        System.out.println("Sorted by age:");
        sortedByAge.forEach(System.out::println);

        // Sorting by name using streams
        List<Person> sortedByName = people.stream()
                .sorted((p1, p2) -> p1.name.compareTo(p2.name))
                .collect(Collectors.toList());

        // Print sorted list by name
        System.out.println("\nSorted by name:");
        sortedByName.forEach(System.out::println);
    }
}
```

### **Output:**
```
Sorted by age:
Bob (20)
Charlie (23)
Alice (25)

Sorted by name:
Alice (25)
Bob (20)
Charlie (23)
```

### **Advantages of Streams:**
- More functional, modern approach.
- Chains multiple operations like filtering, mapping, or sorting, which makes it more expressive for complex tasks.

### **3. Using `Comparator.comparing()` (Java 8+)**

Another clean way to sort using `Comparator` is by using `Comparator.comparing()`. This method is part of the `Comparator` interface and is a shorthand for creating comparators. It's very flexible for sorting by different fields.

#### **Example: Sorting Using `Comparator.comparing()`**

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return name + " (" + age + ")";
    }
}

public class Main {
    public static void main(String[] args) {
        ArrayList<Person> people = new ArrayList<>();
        people.add(new Person("Alice", 25));
        people.add(new Person("Bob", 25));
        people.add(new Person("Charlie", 23));

        // Sorting by age, then by name using Comparator.comparing()
        Collections.sort(people, Comparator
                .comparing(Person::getAge)
                .thenComparing(Person::getName));

        // Print sorted list
        System.out.println("Sorted by age, then by name:");
        for (Person person : people) {
            System.out.println(person);
        }
    }
}
```

### **Advantages of `Comparator.comparing()`**
- More readable and concise.
- You can chain multiple comparisons using `thenComparing()`, making it ideal for multi-field sorting.

### **Summary of Sorting Methods:**
1. **Implementing `Comparable`:**
   - Sorts objects based on their "natural order."
   - Requires modifying the class to implement the `compareTo` method.

2. **Using `Comparator`:**
   - Flexible for multiple comparison strategies without modifying the class.
   - Can use anonymous classes, lambda expressions, or method references (`Comparator.comparing`).

3. **Using Streams**:
   - More functional, modern approach introduced in Java 8.
   - Suitable for chaining multiple operations like filtering and sorting.

### Which method to use?
- **Use `Comparable`** when your class has a single, obvious natural sorting order (e.g., sorting by `age` for a `Person` class).
- **Use `Comparator`** when you need more flexibility, such as sorting by multiple fields or different criteria.
- **Use Streams or `Comparator.comparing()`** if you're working with Java 8+ and prefer a more modern, functional approach to sorting.

Each method has its place, and the right choice depends on your specific use case.

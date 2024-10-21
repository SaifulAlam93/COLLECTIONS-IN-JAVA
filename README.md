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

4. **Using Java 8+ `forEach`:**
   ```java
   list.forEach(System.out::println);
   ```

`ArrayList` provides dynamic resizing and ensures the order of elements, making it a flexible data structure for many use cases.

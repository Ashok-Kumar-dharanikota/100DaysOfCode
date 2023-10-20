# Day - 1 of #100DaysOfCode

In Java, the Collections framework provides a set of classes and interfaces to represent and manipulate groups of objects as a single unit. This framework offers data structures and algorithms for storing, retrieving, querying, and manipulating data.

# Reasons for Introducing the Collections Framework:

**Efficiency**: The framework provides efficient standard implementations for commonly used data structures and algorithms. Without this framework, developers would have to implement these from scratch every time, leading to potential inefficiencies and inconsistencies.

**Standardization**: Before Collections, different developers and organizations had their own way of implementing data structures. The Collections framework offers a standardized way, which makes code more readable and maintainable.

**Reduced Effort**: Implementing data structures from scratch is time-consuming and error-prone. By providing ready-to-use implementations, the framework reduces development effort.

**Interoperability**: Since the Collections framework provides standardized interfaces, it's easier for APIs and libraries to interoperate. They can easily accept or return collections without worrying about the specific implementation used.

**Flexibility**: The Collections framework is designed to be extensible. Developers can use the provided interfaces to create their own data structures and algorithms while still being compatible with the rest of the framework.

**Reduced Bugs**: Implementing data structures and algorithms is tricky. By relying on the well-tested implementations provided by the Java Collections framework, developers reduce the chance of introducing bugs in their applications.



# Java Collections Framework Hierarchy

### 1. Collection Interface
   - **List Interface**
     - ArrayList
     - LinkedList
     - Vector
       - Stack
   - **Set Interface**
     - HashSet
     - LinkedHashSet
     - TreeSet
   - **Queue Interface**
     - PriorityQueue
     - Deque Interface
       - ArrayDeque

   - **Map Interface**
     - HashMap
     - LinkedHashMap
     - Hashtable
     - TreeMap

## Utility Classes

- **Collections:** Provides static methods for various operations on collections.
- **Arrays:** Provides static methods for arrays, acting like a bridge between arrays and collections.


# What exactly means "Group of Objects"

## when i create a integer array list i am actually adding integer values, how can you say it as object ?

When you're working with ArrayList and other generic collections in Java, you're indeed dealing with objects. For primitive data types, like int, Java provides wrapper classes, such as Integer for int, Double for double, etc. These wrapper classes allow primitive data types to be used as objects.

When you feel like you're adding a primitive int to an ArrayList<Integer>, what's happening behind the scenes is "autoboxing." Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes.

Here's an example:
```
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(5);  // Autoboxing: int primitive is converted to an Integer object

```

In the above code, when you're adding the primitive int value 5 to the ArrayList, Java automatically converts (or autoboxes) the int to an Integer object. So, you're actually storing an Integer object in the list, not a primitive int.

Similarly, when you retrieve an item from the ArrayList<Integer>, auto-unboxing will happen:

```
int value = list.get(0);  // Auto-unboxing: Integer object is converted back to int primitive
```

Here, the Integer object is automatically converted (or unboxed) to the primitive int when you try to assign the value to an int variable.

So, even though it might seem like you're directly working with primitives, you're actually working with their wrapper object equivalents due to the autoboxing and auto-unboxing mechanisms provided by Java.

# Here's a simple demonstration of CRUD operations for these collections:

### ArrayList (List implementation):

```
import java.util.ArrayList;
import java.util.List;

public class ArrayListCRUD {
    public static void main(String[] args) {
        // Create
        List<String> list = new ArrayList<>();
        list.add("One");
        list.add("Two");

        // Read
        String firstElement = list.get(0);
        System.out.println("First element: " + firstElement);

        // Update
        list.set(0, "Updated One");
        System.out.println("After update: " + list.get(0));

        // Delete
        list.remove(0);
        System.out.println("After delete: " + list);
    }
}

```

### HashSet (Set implementation):

```
import java.util.HashSet;
import java.util.Set;

public class HashSetCRUD {
    public static void main(String[] args) {
        // Create
        Set<String> set = new HashSet<>();
        set.add("One");
        set.add("Two");

        // Read (Note: Sets do not support access by index)
        System.out.println("Set contents: " + set);

        // Update (HashSet doesn't have a direct update. You remove then add.)
        set.remove("One");
        set.add("Updated One");
        System.out.println("After update: " + set);

        // Delete
        set.remove("Updated One");
        System.out.println("After delete: " + set);
    }
}

```

### HashMap (Map implementation):

```
import java.util.HashMap;
import java.util.Map;

public class HashMapCRUD {
    public static void main(String[] args) {
        // Create
        Map<Integer, String> map = new HashMap<>();
        map.put(1, "One");
        map.put(2, "Two");

        // Read
        String valueForOne = map.get(1);
        System.out.println("Value for 1: " + valueForOne);

        // Update
        map.put(1, "Updated One");
        System.out.println("After update: " + map.get(1));

        // Delete
        map.remove(1);
        System.out.println("After delete: " + map);
    }
}

```

# java.util.Collections

The java.util.Collections class provides a set of utility methods that operate on or return collections. These methods can be applied to various classes and interfaces in the Collections framework, though not every method is applicable to every collection.

Here's a list of commonly used utility methods from the Collections class:

### Sorting and Searching:

```
List<Integer> numbers = new ArrayList<>(Arrays.asList(3, 1, 4, 1, 5, 9));
Collections.sort(numbers);
System.out.println(numbers); // [1, 1, 3, 4, 5, 9]
int index = Collections.binarySearch(numbers, 4);
System.out.println(index); // 3

```

### Minimum and Maximum:

```
int min = Collections.min(numbers);
int max = Collections.max(numbers);
System.out.println("Min: " + min + ", Max: " + max); // Min: 1, Max: 9

```

### Frequency and Disjoint:

```
int frequency = Collections.frequency(numbers, 1);
System.out.println(frequency); // 2
boolean isDisjoint = Collections.disjoint(numbers, Arrays.asList(7, 8, 10));
System.out.println(isDisjoint); // true

```

### Empty, Singleton, and AddAll:

```
List<Integer> emptyList = Collections.emptyList();
System.out.println(emptyList); // []
Set<String> singletonSet = Collections.singleton("singleElement");
System.out.println(singletonSet); // [singleElement]
Collections.addAll(numbers, 6, 2, 8);
System.out.println(numbers); // [1, 1, 3, 4, 5, 9, 6, 2, 8]

```

### Copy

```
List<Integer> dest = new ArrayList<>(Arrays.asList(new Integer[numbers.size()]));
Collections.copy(dest, numbers);
System.out.println(dest); // [1, 1, 3, 4, 5, 9, 6, 2, 8]

```

### Swap

```
Collections.swap(numbers, 0, 1);
System.out.println(numbers); // [1, 1, 3, 4, 5, 9, 6, 2, 8]

```

### Fill

```
Collections.fill(numbers, 0);
System.out.println(numbers); // [0, 0, 0, 0, 0, 0, 0, 0, 0]

```

### Rotate

```
Collections.rotate(numbers, 1);
System.out.println(numbers); // [0, 0, 0, 0, 0, 0, 0, 0, 0]

```

### Replace

```
Collections.replaceAll(numbers, 0, 10);
System.out.println(numbers); // [10, 10, 10, 10, 10, 10, 10, 10, 10]

```

### Reverse

```
Collections.reverse(numbers);
System.out.println(numbers); // [10, 10, 10, 10, 10, 10, 10, 10, 10]

```

### Shuffle: (Output varies as elements are randomized.)

```
Collections.shuffle(numbers);
System.out.println(numbers); // Randomized version of the numbers list

``` 

### nCopies 

```
List<String> copies = Collections.nCopies(5, "example");
System.out.println(copies); // [example, example, example, example, example]

```

Remember that the Collections utility methods operate on the existing collection. As a result, operations like fill, rotate, replaceAll, reverse, and shuffle modify the collection in place. Also, after filling the numbers list with zeros, many subsequent operations produce repetitive output since the list contains identical elements. Adjust the sequence of operations if you want to see more varied results.

# Time and Space Complexity

## ArrayList

- Access: O(1)
- Insertion or Deletion (at the end): O(1)  amortized, but O(n) worst case since the array needs to be resized and copied
- Insertion or Deletion (in the middle): O(n) due to shifting
- Search: O(n) for a linear search

## LinkedList

- Access: O(n)
- Insertion or Deletion (at the beginning or end): O(1)
- Insertion or Deletion (in the middle): O(n) in the worst case, but can be O(1) with a direct node reference
- Search: O(n) for a linear search

## HashSet

- Insertion, Deletion, Access: O(1) average and amortized, but O(n) in the worst case due to hash collisions
- Space: Typically uses more memory than an equivalent ArrayList because of the underlying hash table

## LinkedHashSet

- Similar to HashSet but maintains the order of insertion.


## TreeSet

- Insertion, Deletion, Access: O(logn) because it is implemented as a red-black tree.

## HashMap

- Insertion, Deletion, Access: O(1) average and amortized, but O(n) in the worst case due to hash collisions.
- Space: Uses more memory compared to ArrayList or arrays due to the underlying hash table structure and nodes.

## LinkedHashMap

- Similar to HashMap but maintains the order of insertion.

## TreeMap

- Insertion, Deletion, Access: O(logn) as it is a red-black tree

## Stack (based on Vector):

- Access: O(1)
- Insertion or Deletion: O(1) amortized for push/pop operations


## Queue (e.g., ArrayDeque):

- Access (peek at front or back): O(1)
- Insertion or Deletion (at the front or back): O(1)
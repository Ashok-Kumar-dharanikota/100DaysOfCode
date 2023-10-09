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
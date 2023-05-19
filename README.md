1.	What is the use of the "using" keyword
2.	What is the difference between Tuples and ValueTuples
3.	What is the difference between is and as keywords
4.	What is the purpose of the "dynamic" keyword
5.	What is the difference between Dispose and Finalize methods
6.	What are default implementations in interfaces
7.	What is deconstruction
8.	Why is "catch(Exception)" almost always a bad idea (and when it is not)
9.	What is the difference between "throw" and "throw ex"
10.	What is the difference between typeof and GetType
11.	What is reflection
12.	What are attributes
13.	What is serialization
14.	What are generations
15.	What is the purpose of the "checked" keyword
16.	What is the difference between double and decimal
17.	What is an Array
18.	What is a List
19.	What is an ArrayList
20.	What is the purpose of the GetHashCode method
21.	What is a Dictionary
22.	What are indexers
23.	What is caching
24.	What are immutable types and what's their purpose
25.	What are records and record structs
26.	Why does string behave like a value type even though it is a reference type
27.	What is the difference between string and StringBuilder
28.	What is operator overloading
29.	What are anonymous types
30.	What is cohesion
31.	What is coupling
32.	What is the Strategy design pattern
33.	What is the Dependency Injection design pattern
34.	What is the Template Method design pattern
35.	What is the Decorator design pattern
36.	What is the Observer design pattern
37.	What are events
38.	What is Inversion of Control
39.	What is the "composition over inheritance" principle
40.	What are mocks
41.	What are NuGet packages
42.	What is the difference between Debug and Release builds
43.	What are preprocessor directives
44.	What are nullable reference types
45.	Bonus!
46.	What are expression-bodied members
47.	What are Funcs and lambda expressions
48.	What are delegates
49.	How does the Garbage Collector decide which objects can be removed from memory
















1. What is the use of the "using" keyword?
The using keyword in C# is used for automatic resource management. It ensures that the resources, such as file streams or database connections, are properly disposed of when they are no longer needed. The using statement defines a scope within which the resource is valid, and once the scope is exited, the resource is automatically disposed of, even if an exception occurs.
________________________________________
2. What is the difference between Tuples and ValueTuples?
Tuples and ValueTuples are similar in that they both allow grouping multiple values into a single object. However, there are a few differences between them. Tuples are reference types, while ValueTuples are value types. Tuples can have named fields, whereas ValueTuples have anonymous fields represented by Item1, Item2, etc. ValueTuples are more lightweight and generally perform better in certain scenarios.
________________________________________
3. What is the difference between is and as keywords?
The is keyword is used for type checking in C#. It checks if an object is compatible with a given type and returns a boolean value. If the object is of the specified type or a derived type, is returns true; otherwise, it returns false.
The as keyword is used for safe type casting. It attempts to cast an object to a specified type. If the cast is successful, the as operator returns the object as the specified type; otherwise, it returns null.
________________________________________
4. What is the purpose of the "dynamic" keyword?
The dynamic keyword in C# is used to declare variables whose types are resolved at runtime. It enables late binding, allowing you to call methods and access properties that are not known at compile-time. The dynamic type bypasses compile-time type checking, so it offers more flexibility but may lead to runtime errors if the resolved types do not support the invoked operations.
________________________________________
5. What is the difference between Dispose and Finalize methods?
The Dispose method is used to release unmanaged resources used by an object in C#. It is part of the IDisposable interface and is typically called explicitly by the developer to free resources immediately. It should be implemented to release unmanaged resources, such as file handles or network connections, and can also be used to release managed resources if necessary.
The Finalize method, also known as a destructor, is a special method that is automatically called by the garbage collector during the finalization process. It is used to perform cleanup operations on unmanaged resources before an object is reclaimed by the garbage collector. The Finalize method is invoked implicitly and should be implemented only when dealing with unmanaged resources directly.
________________________________________
6. What are expression-bodied members?
Expression-bodied members are a shorthand syntax introduced in C# 6.0 that allows you to define concise one-liner methods, properties, and indexers. Instead of using the traditional block syntax with curly braces, you can use a lambda-like syntax to define these members. It provides a more compact and expressive way to write simple members, improving readability and reducing code clutter.
________________________________________
7. What are Funcs and lambda expressions?
Funcs and lambda expressions are features in C# that allow you to define and work with anonymous functions. A Func is a predefined delegate type that represents a function with a specific number and type of input parameters and a return type. It can be used to define and invoke anonymous functions.
Lambda expressions, on the other hand, are a concise syntax for defining anonymous functions. They provide a way to create inline functions without explicitly declaring a separate method. Lambda expressions are often used in conjunction with Func delegates to create and pass around lightweight, reusable blocks of code.
________________________________________
8. What are delegates?
Delegates in C# are objects that hold references to methods with a compatible signature. They allow you to treat methods as first-class objects, enabling you to pass methods as arguments, store them in variables, and invoke them dynamically. Delegates provide a way to implement callback mechanisms, event handling, and function pointers in C#.
________________________________________
9. How does the Garbage Collector decide which objects can be removed from memory?
The Garbage Collector (GC) in .NET uses a technique called "mark and sweep" to determine which objects can be removed from memory. It starts by marking all objects that are reachable from the root objects (such as static variables, method parameters, and active stack frames) as "in use." Then, it traverses the object graph, following references from these marked objects to other objects, and marks them as well. Any objects that are not marked during this process are considered unreachable and eligible for garbage collection.
After the marking phase, the GC performs a sweep phase where it reclaims the memory occupied by the unmarked objects. It updates the memory allocation table, making the memory available for future allocations. The process of garbage collection is automatic and transparent to the developer, as the GC manages the memory allocation and deallocation process behind the scenes.
________________________________________
10. What are generations?
In the context of the Garbage Collector in .NET, generations refer to the categorization of objects based on their age and longevity. The Garbage Collector divides the heap into multiple generations to optimize memory management.
By default, the heap is divided into three generations: 0, 1, and 2. Newly allocated objects are placed in Generation 0. If an object survives a garbage collection cycle, it gets promoted to the next generation. Objects in higher generations (1 and 2) have longer lifetimes and are subjected to garbage collection less frequently than objects in Generation 0.
This generational approach allows the Garbage Collector to prioritize garbage collection on younger generations, as they tend to have a higher rate of object allocation and deallocation. It helps improve the efficiency of garbage collection and overall application performance.
________________________________________
11. What is the difference between Dispose and Finalize methods?
The Dispose and Finalize methods are both related to resource cleanup in C#, but they serve different purposes. The Dispose method is part of the IDisposable interface and is used for deterministic cleanup of unmanaged resources. It allows an object to release resources explicitly before it goes out of scope, ensuring timely cleanup. It is typically called explicitly by the consumer of the object using the using statement or by explicitly calling the Dispose method.
On the other hand, the Finalize method is called by the garbage collector during the finalization process of an object. It is used for cleanup of unmanaged resources when an object is being garbage collected. Finalize is non-deterministic, meaning you cannot predict exactly when it will be called. The garbage collector takes care of calling the Finalize method automatically when it determines that an object is no longer reachable.
________________________________________
12. What are default implementations in interfaces?
Default implementations in interfaces were introduced in C# 8.0. They allow you to provide a default implementation for a method in an interface. This means that implementing classes are not required to provide their own implementation of the method if they don't need to customize it. If a class implements an interface with a default implementation, it can choose to override the default implementation with its own implementation if desired.
Default implementations in interfaces are useful when you want to add new methods to an existing interface without breaking existing implementations. It allows you to evolve interfaces over time without introducing breaking changes to the implementing classes.
________________________________________
13. What is deconstruction?
Deconstruction is a feature introduced in C# 7.0 that allows you to extract individual components or properties of an object or tuple into separate variables in a single statement. It provides a convenient way to break down complex data structures into their constituent parts.
Deconstruction works by defining a deconstruct method in a type or pattern matching expression. This method specifies how the object should be deconstructed into its individual components. When deconstructing an object, you can use the var keyword to declare the variables that will hold the deconstructed values.
Deconstruction is particularly useful when working with tuples, allowing you to easily access the elements of a tuple without explicitly accessing them by index.
________________________________________
14. Why is "catch(Exception)" almost always a bad idea (and when it is not)?
Using "catch(Exception)" as a general catch-all in exception handling is generally considered a bad practice. It can lead to hiding and swallowing exceptions, making it harder to diagnose and troubleshoot issues in your code. It is recommended to catch specific exceptions and handle them appropriately, rather than catching all exceptions in a single catch block.
Catching specific exceptions allows you to handle different types of exceptions differently, based on the specific scenario. It enables you to provide more targeted error handling and recovery mechanisms.
There are rare cases where catching all exceptions using "catch(Exception)" might be appropriate, such as in the top-level exception handler of an application, where you want to log and gracefully handle any unhandled exceptions. However, even in such cases, it's important to log the exception details and avoid swallowing the exception without appropriate action.
________________________________________
15. What is the difference between "throw" and "throw ex"?
In C#, "throw" and "throw ex" are used to throw exceptions, but they have a subtle difference in how they preserve the original exception stack trace.
When you use "throw" without an exception object, it rethrows the current exception, preserving its original stack trace. This means that the exception is propagated up the call stack with its original stack trace intact, allowing you to see where the exception was originally thrown.
On the other hand, "throw ex" rethrows the current exception after creating a new exception object. The new exception object is a copy of the original exception, and it discards the original stack trace. This can make it more challenging to identify the original source of the exception, as the stack trace will start from the point where "throw ex" is called.
It is generally recommended to use "throw" without an exception object to maintain the original stack trace unless there is a specific reason to use "throw ex" and create a new exception.
________________________________________
16. What is the difference between typeof and GetType?
•	The typeof keyword is used to obtain the System.Type object of a type at compile time. It is a compile-time operator that allows you to work with types in a static context. For example, you can use typeof(MyClass) to get the Type object representing the MyClass type.
•	The GetType method is called on an instance of a class to obtain the System.Type object representing the actual runtime type of the instance. It is a runtime method that returns the Type object associated with the specific instance. For example, if you have an instance obj of type MyClass, you can use obj.GetType() to get the Type object representing the runtime type of obj.
________________________________________
17. What is reflection?
Reflection is a powerful feature in C# that allows you to inspect and manipulate types, members, and objects at runtime. With reflection, you can dynamically load assemblies, create instances of types, invoke methods, access fields and properties, and perform various other operations on types and objects.
Reflection provides a way to obtain metadata information about types and their members, such as class names, method signatures, property names, and more. It allows you to discover and analyze types and their members dynamically, without knowing them at compile time.
Reflection is commonly used in scenarios such as creating extensible applications, implementing plugins, generating code dynamically, and performing advanced debugging and diagnostics.
________________________________________
18. What are attributes?
Attributes are a way to add metadata or declarative information to types and their members in C#. They allow you to annotate and decorate code elements with additional information that can be used at compile time or at runtime.
Attributes are defined by deriving from the System.Attribute base class or by using built-in attribute types provided by the .NET Framework. They can be applied to various elements such as classes, methods, properties, parameters, and more.
Attributes can be used for various purposes, including:
•	Providing additional information to compilers or tools.
•	Controlling the behavior of code generators or runtime components.
•	Enabling conditional compilation or runtime behaviors.
•	Implementing custom serialization or marshaling logic.
•	Supporting declarative security checks or permissions.
Attributes can be accessed and analyzed at runtime using reflection, allowing you to retrieve the metadata associated with a type or member that has been annotated with attributes.
________________________________________
19. What is serialization?
Serialization is the process of converting an object's state into a format that can be stored, transmitted, or reconstructed at a later time. In C#, serialization allows you to convert objects into a binary format (binary serialization) or a text-based format (XML or JSON serialization).
Serialization is useful in scenarios where you need to persist the state of an object or send it over a network. It enables you to save an object to a file, store it in a database, or transmit it across different systems, and later reconstruct the object from its serialized form.
C# provides built-in mechanisms for serialization, such as the BinaryFormatter for binary serialization and the XmlSerializer or DataContractSerializer for XML serialization. Additionally, third-party libraries like Newtonsoft.Json (JSON.NET) offer powerful JSON serialization capabilities.
Serialization can be customized by using attributes or implementing specific interfaces, such as ISerializable for custom binary serialization or IXmlSerializable for custom XML serialization.
________________________________________
20. What is pattern matching?
Pattern matching is a feature introduced in C# 7.0 that allows you to test whether a value has a certain shape or structure and extract information from it in a concise and readable way. It simplifies common programming scenarios where you need to check the type or shape of an object and take specific actions based on the match.
Pattern matching can be used with various constructs in C#, such as switch statements, if statements, and foreach loops. It enables you to match against different patterns, including type patterns, property patterns, tuple patterns, and more.
For example, in a switch statement, you can use pattern matching to match the value of a variable against different patterns, such as specific values, types, or conditions. Each pattern can include variables that are bound to parts of the matched value, allowing you to extract and use that information within the corresponding case block.
Pattern matching provides a more expressive and readable way to handle different cases and simplify your code when dealing with complex data structures.
________________________________________
21. How does the binary number system work?
The binary number system is a positional numeral system with a base of 2. It uses only two digits, 0 and 1, to represent numbers. In contrast, the decimal number system (base 10) uses ten digits, 0 to 9.
In the binary system, each digit represents a power of 2 based on its position. The rightmost digit represents 2^0 (1), the next digit represents 2^1 (2), the next digit represents 2^2 (4), and so on. By adding up the values of each digit, you can determine the decimal equivalent of a binary number.
For example, the binary number 1011 is equivalent to the decimal number:
(1 * 2^3) + (0 * 2^2) + (1 * 2^1) + (1 * 2^0) = 11
Binary numbers are widely used in computer systems because they can represent the on/off states of electronic components, which are the foundation of digital circuits. Computers use binary numbers internally to represent and process data, with each binary digit (bit) representing a discrete state of information.
________________________________________
22. What is the purpose of the "checked" keyword?
The checked keyword is used in C# to explicitly enable overflow checking for integral arithmetic operations. By default, C# performs arithmetic operations without checking for overflow, which means that if the result of an operation exceeds the range of the data type, it wraps around or produces an undefined value.
The checked keyword can be used to ensure that overflow errors are detected and handled appropriately. When the checked keyword is applied, the compiler generates code that checks for overflow and throws an exception (System.OverflowException) if an overflow occurs during the operation.
For example:
checked
{
    int x = int.MaxValue;
    int y = 1;
    int sum = x + y; // This will throw an OverflowException
}
By using the checked keyword, you can explicitly specify that you want overflow checking to be performed, providing more control and safety in scenarios where overflow errors can lead to unexpected behavior or security vulnerabilities.
________________________________________
23. What is the difference between double and decimal?
In C#, double and decimal are both numeric data types used to represent floating-point numbers, but they have different characteristics and are suited for different purposes.
•	double: double is a 64-bit floating-point type that conforms to the IEEE 754 standard. It is typically used for scientific and engineering calculations where a wide range of values and high precision are required. double has a larger range and can represent very small or very large numbers, but it has limited precision due to the finite number of bits available.
•	decimal: decimal is a 128-bit decimal floating-point type that provides high precision and is suitable for financial and monetary calculations, where accuracy is crucial. decimal can represent a much wider range of values and provides significantly more precision than double. It is particularly useful when working with decimal fractions or when exact decimal representations are required.
The choice between double and decimal depends on the specific requirements of your application. If you need a wide range of values and can tolerate some loss of precision, double is a good choice. If you need precise decimal calculations or are working with monetary values, decimal is the recommended option.
________________________________________
24. What is an Array?
An array in C# is a fixed-size collection of elements of the same type. It provides a way to store and access multiple values of the same data type using a single variable. The elements in an array are ordered and can be accessed by their index, which represents their position in the array.
Arrays have a predetermined length that is specified when they are created. Once the length is set, it cannot be changed. The elements in an array are stored in contiguous memory locations, which allows for efficient access and traversal.
To declare and initialize an array, you can use the following syntax:
dataType[] arrayName = new dataType[length];
For example, to create an array of integers with a length of 5:
int[] numbers = new int[5];
You can then assign values to individual elements and access them using their index:
numbers[0] = 10;
numbers[1] = 20;
// Accessing array elements
Console.WriteLine(numbers[0]); // Output: 10
Console.WriteLine(numbers[1]); // Output: 20
Arrays provide a convenient way to work with collections of data when the number of elements is known in advance.
________________________________________
25. What is a List?
A List in C# is a dynamic, resizable collection that can hold elements of any data type. It is part of the System.Collections.Generic namespace and provides a more flexible alternative to arrays. Unlike arrays, the size of a List can grow or shrink dynamically as elements are added or removed.
To use a List, you need to import the System.Collections.Generic namespace and instantiate it using the following syntax:
using System.Collections.Generic;

List<dataType> listName = new List<dataType>();
For example, to create a List of integers:
List<int> numbers = new List<int>();
You can then add elements to the list using the Add method:
numbers.Add(10);
numbers.Add(20);
You can access elements in a List using their index, just like an array:
Console.WriteLine(numbers[0]); // Output: 10
Console.WriteLine(numbers[1]); // Output: 20
The List class provides a rich set of methods and properties to manipulate and query the collection, such as Count to get the number of elements, Remove to remove an element, Sort to sort the elements, and more.
Using List gives you the flexibility to work with a collection that can dynamically grow or shrink based on your needs.
________________________________________
26. What is an ArrayList?
ArrayList is a class in the System.Collections namespace that represents a dynamically resizable array-like collection in C#. It is similar to the List class but has some key differences.
Unlike List, ArrayList can hold elements of any data type, as it internally stores objects as System.Object. This allows you to store elements of different types in the same ArrayList. However, this flexibility comes at the cost of performance and type safety, as you need to explicitly cast the elements when retrieving them from the ArrayList.
To use ArrayList, you need to import the System.Collections namespace and instantiate it as follows:
using System.Collections;

ArrayList arrayListName = new ArrayList();
You can then add elements to the ArrayList using the Add method:
arrayListName.Add(10);
arrayListName.Add("Hello");
arrayListName.Add(10);
arrayListName.Add("Hello");
arrayListName.Add(true);
To access elements from the ArrayList, you can use the indexer with explicit casting:
int firstElement = (int)arrayListName[0];
string secondElement = (string)arrayListName[1];
bool thirdElement = (bool)arrayListName[2];
It's important to note that ArrayList is not type-safe, and incorrect casting can lead to runtime errors. Therefore, it's recommended to use List<T> when you have a specific type of elements to work with.
________________________________________
27. What is the purpose of the GetHashCode method?
In C#, the GetHashCode method is a member of the System.Object class and is overridden by derived types to provide a hash code value for an object. The hash code is an integer value that is used in hash-based collections such as Dictionary, HashSet, and Hashtable to efficiently store and retrieve objects.
The primary purpose of the GetHashCode method is to generate a hash code based on the contents of an object. Objects that are considered equal should have the same hash code, although objects with the same hash code are not necessarily equal. The hash code is used as an initial index into a hash table, allowing for efficient lookup and retrieval of objects.
When overriding the GetHashCode method in a custom class, it's important to ensure that two objects that are considered equal return the same hash code. This helps maintain the integrity of hash-based collections and ensures proper functionality.
It's worth noting that the GetHashCode method works in conjunction with the Equals method. For two objects that are equal, the hash codes must be the same, and the Equals method should return true. However, objects with the same hash code may or may not be equal, and the Equals method should be used to perform a full comparison.
________________________________________
28. What is a Dictionary?
A Dictionary in C# is a collection type that represents a generic, unordered collection of key-value pairs. It is part of the System.Collections.Generic namespace and provides an efficient way to store and retrieve data based on keys.
To use a Dictionary, you need to import the System.Collections.Generic namespace and instantiate it using the following syntax:
using System.Collections.Generic;

Dictionary<keyType, valueType> dictionaryName = new Dictionary<keyType, valueType>();
For example, to create a dictionary that maps strings to integers:
Dictionary<string, int> ageDictionary = new Dictionary<string, int>();
You can then add key-value pairs to the dictionary using the Add method:
ageDictionary.Add("John", 25);
ageDictionary.Add("Jane", 30);
To retrieve values from the dictionary, you can use the key as an indexer:
int johnAge = ageDictionary["John"];
int janeAge = ageDictionary["Jane"];
The Dictionary class provides various methods and properties to manipulate and query the collection, such as Count to get the number of key-value pairs, Remove to remove a pair, ContainsKey to check if a key exists, and more.
Dictionary is commonly used when you need to associate values with unique keys and perform fast lookups based on those keys.
________________________________________
29. What are indexers?
In C#, an indexer is a special member of a class or struct that enables objects of that type to be indexed just like an array. It allows instances of a class to be treated as an array or a collection and provides a way to access elements or properties using indexing syntax.
Indexers are defined using the this keyword followed by one or more parameters inside the class or struct. The parameters define the type and number of values used to index the object. The return type of the indexer represents the type of the element or property being accessed.
Here's an example of defining an indexer in a class:
public class MyCollection
{
    private int[] data = new int[10];

    public int this[int index]
    {
        get => data[index];
        set => data[index] = value;
    }
}
In this example, MyCollection has an indexer that allows accessing elements of the data array using the indexing syntax (myCollection[index]). The get accessor retrieves the element at the specified index, and the set accessor assigns a value to the element at the specified index.
Indexers can have multiple parameters, allowing for multidimensional indexing or using different types for indexing. They can also be overloaded, enabling different behaviors based on the number or types of parameters.
By using indexers, you can provide a more intuitive and convenient way to access elements or properties of an object that logically represents a collection or an array-like structure.
________________________________________
30. What is caching?
Caching is a technique used in software development to store frequently accessed or expensive-to-compute data in memory, allowing for faster access and improved performance. It involves temporarily storing the results of expensive operations or frequently used data in a cache, which is a high-speed storage medium.
In the context of programming, caching can be applied in various scenarios, such as:
1.	Database query results: Instead of executing the same database query multiple times, the results can be cached in memory for subsequent requests. This reduces the load on the database server and improves response times.
2.	Computation-intensive operations: If a computation or algorithm involves repetitive calculations, the results can be cached to avoid redundant computations. This is particularly useful when the result is deterministic and doesn't change frequently.
3.	Web page or resource caching: Web servers can cache the generated HTML pages, images, or other resources to serve them faster to subsequent requests. This reduces the processing and network overhead, resulting in improved page load times.
Caching can be implemented using various caching strategies, such as using in-memory data structures like dictionaries, hash maps, or specialized caching libraries. The cached data is typically associated with a key or identifier for easy retrieval.
However, caching should be used judiciously, as it introduces additional complexity and can lead to stale or inconsistent data if not managed properly. Careful consideration should be given to cache expiration, cache invalidation, and managing memory usage to ensure the cache remains accurate and efficient.
________________________________________
31. What are immutable types and what's their purpose?
Immutable types in C# are types whose instances cannot be modified once they are created. Once an immutable object is initialized, its state cannot be changed, making it inherently thread-safe and eliminating the risk of accidental modifications.
The main purpose of immutable types is to ensure data integrity and simplify code by eliminating the need for defensive copying or complex synchronization mechanisms. With immutable types, you can safely share objects across multiple threads without worrying about race conditions or unexpected modifications.
Immutable types are typically implemented by having properties that are read-only and initialized through the constructor. Once the object is created, its properties cannot be modified. Any operation that needs to change the state of an immutable object returns a new instance with the updated state.
Some benefits of using immutable types include:
Thread safety: Immutable types are inherently thread-safe since their state cannot be modified after creation. This makes them ideal for concurrent or parallel programming scenarios.
•	Simpler code: With immutable types, you don't need to worry about defensive copying or synchronizing access to shared objects. The immutability guarantees that the object's state remains constant throughout its lifetime.
•	Predictable behavior: Immutable objects have a predictable and consistent state, which simplifies debugging and reasoning about program behavior. Since they can't change, their behavior remains the same regardless of when or where they are used.
Common examples of immutable types in C# include string, numeric types (int, float, etc.), and many of the types in the System.DateTime struct.
By using immutable types, you can write more robust, thread-safe, and maintainable code, while reducing the likelihood of bugs caused by mutable state changes.
________________________________________
32. What is an interface?
In C#, an interface is a reference type that defines a contract or set of operations that a class must implement. It specifies the members (methods, properties, events, and indexers) that a class implementing the interface should have, without specifying how those members are implemented.
An interface is declared using the interface keyword followed by a name, a set of member declarations, and optionally the access modifiers for the members. Here's an example:
public interface IShape
{
    double CalculateArea();
    void Draw();
}
In this example, IShape is an interface that defines two members: CalculateArea and Draw. Any class that implements the IShape interface must provide an implementation for these members.
To implement an interface in a class, you use the class keyword followed by the class name, a colon, and the interface name. Here's an example:
public class Circle : IShape
{
    public double CalculateArea()
    {
        // Implementation for calculating the area of a circle
    }

    public void Draw()
    {
        // Implementation for drawing a circle
    }
}
By implementing an interface, a class can define its behavior based on the contract specified by the interface. This allows for polymorphism, as objects of different classes that implement the same interface can be treated interchangeably.
Interfaces provide a way to achieve abstraction, modularity, and loose coupling in object-oriented programming. They are widely used to define contracts for services, plugins, or other components in a system.
________________________________________


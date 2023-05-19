
1. What is the difference between Tuples and ValueTuples?

Tuples and ValueTuples both allow grouping multiple values into a single object. Tuples are reference types, while ValueTuples are value types. Tuples can have any number of elements and allow naming individual elements, whereas ValueTuples have a limit of eight elements and use a fixed naming convention.

2. What is the difference between is and as keywords?

The is keyword is used for type checking, while the as keyword is used for type casting.

    is checks whether an object is of a certain type.
    as attempts to cast an object to a specified type and returns null if the cast is not successful.

3. What is the use of the "using" keyword?

The using keyword has two purposes:

    Resource Management: It ensures proper disposal of resources by automatically calling the Dispose() method when the scope is exited.
    Namespace Import: It simplifies the usage of types within a specific namespace.

4. What are anonymous types?

Anonymous types allow creating objects without explicitly defining a named type. They are useful for temporary or one-time object structures and are defined using the new keyword and object initializer syntax.

5. What is the purpose of the "dynamic" keyword?

The dynamic keyword enables late binding and dynamic resolution of member invocations. It allows calling methods, properties, and fields on an object without compile-time type checking. The actual type of the object is determined at runtime.

6. What are expression-bodied members?

Expression-bodied members provide a concise syntax for defining members in classes or structs. They allow writing methods, properties, and indexers as single-line expressions instead of full method bodies.

7. What are Funcs and lambda expressions?

Funcs are delegate types that represent functions with specific input and output types. They provide a way to define and pass around methods as parameters or variables. Lambda expressions are anonymous functions that can be used to create instances of Funcs or other delegate types in a more compact and expressive way.

8. What are delegates?

Delegates are types that define a method signature and can hold references to methods with compatible signatures. They are often used for event handling, callback mechanisms, or implementing the observer pattern.

9. How does the Garbage Collector decide which objects can be removed from memory?

The Garbage Collector (GC) in .NET determines object eligibility for garbage collection by analyzing their reachability. Objects that are no longer reachable from the root of the object graph (i.e., not referenced by any active objects or rooted references) are considered eligible for garbage collection and will be reclaimed in subsequent GC cycles.

10. What are generations?

In the context of the .NET Garbage Collector, generations represent different levels of object longevity. Objects are initially allocated in Generation 0, and if they survive garbage collections, they can be promoted to higher generations (1 or 2) based on their longevity. The GC performs more frequent collections on Generation 0, making it a short-lived objects area, while higher generations contain objects with longer lifetimes.

11. What is the difference between Dispose and Finalize methods?

The Dispose method is used to release unmanaged resources explicitly. It should be called explicitly or by utilizing the using statement. On the other hand, the Finalize method, also known as the destructor, is called by the garbage collector to release unmanaged resources when an object is garbage collected. The Finalize method should be overridden only when unmanaged resources are involved.

12. What are default implementations in interfaces?

Default implementations in interfaces, introduced in C# 8.0, allow providing a default implementation for interface members. This feature enables adding new members to existing interfaces without breaking compatibility with implementing classes. Default implementations are defined using the default keyword and can be overridden by implementing classes.

13. What is deconstruction?

Deconstruction is a feature that allows breaking down the members of an object into individual variables or properties. It simplifies the process of extracting values from complex objects or data structures. Deconstruction is achieved by defining a Deconstruct method within the object, which returns the deconstructed values.

14. Why is "catch(Exception)" almost always a bad idea (and when it is not)?

Using catch(Exception) to catch all exceptions indiscriminately is generally considered a bad practice. It makes it harder to diagnose and handle specific exceptions appropriately. It is recommended to catch specific exceptions or use multiple catch blocks to handle different exception types. However, in certain cases, such as in top-level exception handlers or logging scenarios, catching all exceptions can be useful for logging or reporting purposes.

15. What is the difference between "throw" and "throw ex"?

The throw statement is used to propagate an exception while preserving the original stack trace. On the other hand, throw ex rethrows an exception after resetting the stack trace, effectively losing the original information. It is generally advised to use throw without the "ex" to preserve the complete exception details.

16. What is the difference between typeof and GetType?

typeof is an operator used to obtain the Type object of a type at compile time. It is resolved statically and does not require an instance of the type. GetType, on the other hand, is a method available on all objects that returns the Type object representing the actual runtime type of the instance.

17. What is reflection?

Reflection is a powerful feature in .NET that allows inspecting and manipulating types, methods, properties, and other members at runtime. It provides the ability to dynamically load assemblies, create instances of types, invoke methods, access properties, and retrieve type information.

18. What are attributes?

Attributes are declarative tags used to attach metadata to various program elements such as types, methods, properties, or parameters. They provide additional information or behavior to the program. Attributes can be queried at runtime using reflection, enabling powerful customization and extensibility scenarios.

19. What is serialization?

Serialization is the process of converting an object's state into a format that can be stored, transmitted, or persisted. It allows objects to be written to a file, sent over a network, or stored in a database. Deserialization is the reverse process of reconstructing the object from the serialized format.

20. What is pattern matching?

Pattern matching is a feature introduced in C# 7.0 that allows checking whether an object satisfies a particular pattern and extracting information from it. It provides concise and expressive syntax for performing common pattern-based operations such as type checking, property extraction, or conditional matching.

21. How does the binary number system work?

The binary number system is a base-2 numbering system that uses only two digits, 0 and 1. In binary, each digit represents a power of 2, starting from the rightmost digit. The value of each digit is determined by multiplying it with the corresponding power of 2 and summing up the results. Binary numbers are widely used in computer systems to represent and manipulate data.

22. What is the purpose of the "checked" keyword?

The "checked" keyword in C# is used to explicitly enable overflow checking for arithmetic operations. By default, C# performs arithmetic operations without checking for overflow. However, by using the "checked" keyword, overflow is detected, and an exception is thrown when an overflow occurs, preventing potential silent data corruption.

23. What is the difference between double and decimal?

In C#, "double" and "decimal" are both numeric data types, but they differ in precision and range. "Double" is a 64-bit floating-point type that can represent a wider range of values but has limited precision. "Decimal" is a 128-bit decimal type that offers higher precision for financial or monetary calculations but has a smaller range.

24. What is an Array?

An array is a fixed-size collection of elements of the same type. It provides random access to its elements through an index, which starts from 0. Arrays in C# are zero-based, meaning the first element is accessed with index 0. They offer efficient storage and retrieval of elements but have a fixed size that cannot be changed after creation.

25. What is a List?

A List is a dynamic collection that can grow or shrink in size dynamically. It is part of the System.Collections.Generic namespace in C#. Lists provide methods and properties to add, remove, and manipulate elements efficiently. They are widely used when the number of elements is unknown or can vary over time.

26. What is an ArrayList?

ArrayList is a non-generic collection class in C# that can store elements of different types. It dynamically resizes itself to accommodate new elements and provides methods to add, remove, and access elements efficiently. However, due to its lack of type safety, ArrayList should be used with caution, and it is generally recommended to use generic collections like List<T> for type-safe operations.

27. What is the purpose of the GetHashCode method?

The GetHashCode method in C# returns a hash code for an object. It is primarily used in hash-based collections like Dictionary or HashSet to efficiently store and retrieve objects. The GetHashCode method should be overridden when implementing custom equality for custom types, ensuring that objects with equal values produce the same hash code for proper collection behavior.

28. What is a Dictionary?

A Dictionary is a generic collection class in C# that represents a collection of key-value pairs. It provides fast lookup and retrieval of values based on their associated keys. Keys in a dictionary must be unique, and each key can be associated with a corresponding value. Dictionaries are commonly used when efficient key-based access is required.

29. What are indexers?

Indexers in C# allow instances of a class or struct to be accessed like arrays using square brackets. They provide a way to define custom collection-like access to the elements of an object. By defining indexers, you can specify the behavior when accessing elements by index, enabling more intuitive and convenient syntax for accessing elements.

30. What is caching?

Caching is a technique used to store frequently accessed or computed data in memory for faster retrieval. Instead of recalculating or fetching data from a slow data source, cached data can be retrieved directly from memory, resulting in significant performance improvements. Caching can be implemented using various caching mechanisms and strategies based on the specific requirements of an application.

31. What are immutable types and what's their purpose?

Immutable types are types whose values cannot be changed once they are created. In C#, immutable types are designed to be thread-safe and provide guarantees of data integrity and consistency. By preventing modifications to their values, immutable types simplify code and eliminate potential issues related to shared mutable state, making programs more robust and easier to reason about.

32. What are records and record structs?

Records are a feature introduced in C# 9 that provide a concise way to define immutable data types. They automatically generate useful members like equality methods, hash code, and string representation based on the defined properties or fields. Records are commonly used for modeling data transfer objects (DTOs), immutable data structures, or value objects.

33. Why does string behave like a value type even though it is a reference type?

In C#, strings are reference types, but they have value-like semantics. This is because string instances in C# are immutable, meaning their values cannot be changed after creation. String manipulation operations, such as concatenation or substring extraction, result in new string instances rather than modifying the original string. This immutability allows for more efficient memory usage and simplifies string handling in multithreaded scenarios.

34. What is the difference between string and StringBuilder?

In C#, both strings and StringBuilder are used to manipulate textual data, but they differ in how they handle string modifications. Strings are immutable, meaning they cannot be changed once created. Each modification operation creates a new string instance, which can be inefficient for frequent modifications. StringBuilder, on the other hand, provides a mutable buffer for efficient string modifications, making it suitable for scenarios where extensive string manipulation is required.

35. What is operator overloading?

Operator overloading in C# allows you to redefine the behavior of operators (+, -, *, /, etc.) for user-defined types. By overloading operators, you can define custom semantics for how operators should work with your types, enabling more natural and expressive syntax. Operator overloading is useful when working with custom data types, such as complex numbers or matrices.

36. What are anonymous types?

Anonymous types in C# allow you to define and create objects without explicitly defining a class or a structure. They are useful when you need to create temporary objects to hold a set of related values without the need for a permanent type definition. Anonymous types are primarily used for querying data using LINQ or when returning data from methods.

37. What is cohesion?

Cohesion is a software engineering principle that measures how closely the members of a class or module are related to each other. High cohesion means that the members of a class or module are focused and closely related to a single responsibility or purpose, leading to more maintainable and understandable code. Low cohesion, on the other hand, indicates that the members have disparate responsibilities and may be better off split into separate classes or modules.

38. What is coupling?

Coupling is a measure of how closely one class or module is connected or dependent on another class or module. It refers to the degree of interdependence between software components. Loose coupling means that components are independent and can be modified or replaced without affecting other components. Tight coupling indicates strong dependencies, making it harder to modify or replace components without causing ripple effects.

    39. What is the Strategy design pattern?

The Strategy design pattern is a behavioral pattern that enables dynamic selection of algorithms or behaviors at runtime. It allows encapsulating multiple algorithms under interchangeable interfaces, making it easy to switch between different strategies based on the specific context or requirements. The Strategy pattern promotes flexibility, extensibility, and maintainability by decoupling the implementation details of algorithms from the code that uses them.

40. What is the Dependency Injection design pattern?

The Dependency Injection (DI) design pattern is a technique for providing dependencies to an object rather than letting the object create or manage its dependencies. It involves injecting dependencies through constructor parameters, method parameters, or properties. DI promotes loose coupling, testability, and modularity by allowing dependencies to be easily replaced or mocked during testing and enabling the composition of complex systems from smaller, reusable components.

41. What is the Template Method design pattern?

The Template Method design pattern is a behavioral pattern that defines the skeleton of an algorithm in a base class but allows subclasses to provide specific implementations for certain steps of the algorithm. It enables code reuse and allows for variations in the behavior of the algorithm without modifying its overall structure. The Template Method pattern is useful when you want to define a common algorithm structure but allow customization of certain steps.

42. What is the Decorator design pattern?

The Decorator design pattern is a structural pattern that allows adding additional behaviors or responsibilities to an object dynamically. It involves wrapping the original object with one or more decorator objects, each adding specific functionalities. Decorators adhere to the open-closed principle, allowing for flexible extension of an object's behavior without modifying its underlying implementation. This pattern is useful when you need to add or remove responsibilities from objects at runtime.

43. What is the Observer design pattern?

The Observer design pattern is a behavioral pattern that establishes a one-to-many dependency between objects, so that when one object changes its state, all dependent objects are notified and updated automatically. It provides a loosely coupled way to define interactions between objects, where changes in one object trigger actions in other objects. The Observer pattern is widely used in event-driven and reactive programming paradigms.

44. What are events?

Events in C# provide a mechanism for communication and coordination between objects. An event represents a publish-subscribe model, where an object (the publisher) can notify other objects (the subscribers) when a certain action or state change occurs. Subscribers can subscribe to and unsubscribe from events, allowing them to be notified and respond accordingly. Events are widely used for handling user interactions, asynchronous programming, and building loosely coupled systems.

45. What is Inversion of Control?

Inversion of Control (IoC) is a design principle and a programming technique where the control flow and dependencies of an application are inverted or delegated to a separate framework or container. Instead of objects creating and managing their dependencies, IoC containers take responsibility for creating and injecting dependencies into objects. This promotes loose coupling, modular design, and easier testability by removing explicit dependencies from the code.

46. What is the "composition over inheritance" principle?

The "composition over inheritance" principle is a guideline in software design that favors composition (object containment) over inheritance as a way to achieve code reuse and flexibility. Rather than using inheritance to create complex object hierarchies, the principle suggests using composition by combining simpler objects to form more complex ones. Composition offers more flexibility, avoids the limitations of class inheritance, and enables better code maintainability and extensibility.
    
    47. What are mocks?

Mocks are objects that simulate the behavior of real objects during testing. They are used to replace real dependencies of an object being tested, allowing controlled and predictable interactions for testing specific scenarios. Mocks provide predefined behavior and allow verifying method calls and parameter values to ensure correct interactions between objects. Mocking frameworks provide convenient ways to create and manage mocks during unit testing.

48. What is a memory leak?

A memory leak occurs when memory is allocated for objects in a program but not properly deallocated or released when it is no longer needed. As a result, the allocated memory remains in use, leading to a gradual decrease in available memory. If memory leaks are not addressed, they can cause the program to consume more and more memory over time, potentially leading to performance degradation and system instability.

49. What is garbage collection?

Garbage collection is a memory management technique used by programming languages like C# to automatically reclaim memory occupied by objects that are no longer needed or accessible. The garbage collector identifies and frees up memory occupied by objects that are no longer referenced by the program, ensuring efficient memory usage and eliminating the need for manual memory management and deallocation.

50. What is multithreading?

Multithreading is the concurrent execution of multiple threads within a single process. It allows for the simultaneous execution of multiple tasks or portions of code, improving performance and responsiveness in applications. Each thread represents an independent sequence of execution, allowing tasks to be executed concurrently and potentially in parallel on systems with multiple processor cores. Multithreading requires careful synchronization and coordination to ensure thread safety and avoid data races or deadlocks.

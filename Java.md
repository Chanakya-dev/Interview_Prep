## Object-Oriented Programming (OOP) Concepts

### 1) What are the four main principles of Object-Oriented Programming?

Answer: The four main principles are:
Encapsulation: Bundling data and methods that operate on the data within one unit (class).
Inheritance: Mechanism to create new classes based on existing ones.
Polymorphism: Ability to take many forms, allowing methods to do different things based on the object that it is acting upon.
Abstraction: Hiding complex implementation details and showing only essential features.

### 2) Explain the concept of inheritance in Java.

Answer: Inheritance allows one class (subclass) to inherit fields and methods from another class (superclass). This promotes code reusability and establishes a hierarchical relationship between classes.

### 3) What is polymorphism, and how is it implemented in Java?

Answer: Polymorphism allows methods to perform different tasks based on the object that it is acting upon. It can be implemented in Java through method overloading (compile-time polymorphism) and method overriding (runtime polymorphism).

### 4)What is encapsulation, and why is it important?

Answer: Encapsulation is the technique of wrapping data (variables) and methods into a single unit (class). It is important for protecting the internal state of an object from unintended interference and misuse.

### 5)What is an abstract class, and how does it differ from an interface?

Answer: An abstract class is a class that cannot be instantiated and may contain abstract methods (without implementation). An interface is a contract that a class can implement, containing only abstract methods. A class can implement multiple interfaces but can only extend one abstract class.

### 6)Explain method overloading and method overriding.
Answer: Method overloading allows multiple methods in the same class to have the same name but different parameters. Method overriding allows a subclass to provide a specific implementation of a method that is already defined in its superclass.

### 7)What is the purpose of the super keyword in Java?
Answer: The super keyword refers to the superclass of the current object and is used to access superclass methods and constructors.

### 8) What are interfaces in Java, and how do they differ from abstract classes?
Answer: Interfaces are contracts that define methods that must be implemented by classes. They can contain only abstract methods and default methods. Abstract classes can contain both abstract and concrete methods, and a class can implement multiple interfaces, while it can only extend one abstract class.

## Java Basics

### 1) Explain the Java Virtual Machine (JVM) and its role in Java execution.

Answer: The JVM is an abstract computing machine that enables Java bytecode to be executed on any device or operating system, providing platform independence.

### 2) What is the difference between JDK, JRE, and JVM?

- JDK (Java Development Kit): A software development kit used to develop Java applications. It includes the JRE and development tools like compilers and debuggers.
- JRE (Java Runtime Environment): Provides the libraries and components necessary to run Java applications. It includes the JVM.
- JVM (Java Virtual Machine): Executes Java bytecode.

### 3) How does Java achieve platform independence?

Answer: Java achieves platform independence by compiling Java source code into bytecode, which can be executed on any platform that has a compatible JVM.

## Java Collection Framework
### 1) What is the difference between ArrayList and LinkedList?

- ArrayList: Based on a dynamic array, allows random access, provides fast iteration and element access, but slow insertion and deletion (except at the end).
- LinkedList: Based on a doubly linked list, better performance for insertion and deletion at any position but slower iteration and random access.

### 2) What is a Set in Java?
Answer: A Set is a collection that cannot contain duplicate elements. Its common implementations are:

- HashSet: Unordered collection, backed by a hash table.
- LinkedHashSet: Ordered collection, backed by a hash table and a linked list.
- TreeSet: Ordered collection, backed by a red-black tree.

### 3) What is the difference between HashSet and TreeSet?

- HashSet: Unordered, backed by a hash table, provides constant-time performance for basic operations.
- TreeSet: Ordered, backed by a red-black tree, provides log-time performance and maintains elements in sorted order.

### 4) What is the difference between Iterator and ListIterator?

- Iterator: Allows traversing a collection in one direction and supports the remove operation.
- ListIterator: Extends Iterator, allowing bidirectional traversal, modification of the list, and obtaining the index of elements.

### 5) What are Comparator and Comparable in Java?

- Comparable: Defines the natural ordering of objects via the compareTo method.
- Comparator: Defines custom orderings via the compare method and can be used when multiple orderings are needed.

### 6) What is the difference between List and Set in terms of functionality?

- List: An ordered collection that allows duplicate elements and provides positional access.
- Set: An unordered collection that does not allow duplicates, ensuring uniqueness.

### 7) What is the behavior of Set implementations when trying to add a duplicate?
 All Set implementations prevent duplicate elements. If a duplicate is added, the operation will not change the Set, and the add method will return false.

### 8) What is the difference between HashMap and TreeMap?

- HashMap: Unordered and backed by a hash table, provides constant-time performance for basic operations.
- TreeMap: Ordered and backed by a red-black tree, provides log-time performance and maintains keys in sorted order.

### 9) What are the differences between Map and Set in Java?
- Map: Represents a collection of key-value pairs, where keys are unique.
- Set: Represents a collection of unique elements without any key-value mapping.

### 10) What is a Queue in Java, and what are its main implementations?

Answer: A Queue is a collection that represents a first-in, first-out (FIFO) data structure. Main implementations include:
- LinkedList: Implements the Queue interface.
- PriorityQueue: Orders elements based on their natural ordering or a custom comparator.

## Threads and Concurrency

### 1) What is the purpose of the yield() method in Java, and how does it work?
Answer: The yield() method hints to the thread scheduler that the current thread is willing to yield its current use of the CPU. It suggests that other threads of equal priority should be given a chance to execute, but there is no guarantee.

### 2) What is the join() method in Java, and how does it work?
Answer: The join() method allows one thread to wait for the completion of another thread. If Thread A calls threadB.join(), Thread A will pause and wait until Thread B finishes executing.

### 3) What is a daemon thread in Java?
Answer: A daemon thread is a low-priority thread that runs in the background to perform tasks like garbage collection. It does not prevent the JVM from exiting when the program finishes execution.

### 4) How can you interrupt a thread in Java?
Answer: You can interrupt a thread by calling its interrupt() method. This sets the thread's interrupt flag, and if the thread is currently blocked or sleeping, it will throw an InterruptedException.

### 5) What is static synchronization?
 Static synchronization synchronizes static methods or blocks associated with the class itself, ensuring that only one thread can execute any synchronized static method across all instances of the class at a time.

### 6) Explain the lifecycle of a thread in Java. What are the key stages?
The thread lifecycle consists of the following stages:
- New: The thread is created but not yet started.
- Runnable: The thread is ready to run and waiting for CPU time.
- Running: The thread is executing its code.
- Blocked/Waiting: The thread is waiting for a resource or a signal from another thread.
- Dead: The thread has finished executing.

### 7) What are wait(), notify(), and notifyAll() methods in Java, and how do they work?

- wait(): Causes the current thread to release the monitor (lock) and wait until another thread calls notify() or notifyAll().
- notify(): Wakes up one waiting thread, but doesn't release the lock immediately.
- notifyAll(): Wakes up all waiting threads; however, only one will be able to acquire the lock and proceed.

### 8) Describe a situation where you would use wait() and notify().

Answer: A classic producer-consumer scenario where a producer thread produces data and adds it to a shared buffer. If the buffer is full, the producer calls wait() until a consumer consumes an item and calls notify() to wake the producer.

### 9) What is thread synchronization, and why is it important in Java?

Answer: Thread synchronization is the mechanism that ensures that two or more concurrent threads do not access shared resources simultaneously, preventing data inconsistency and race conditions.

### 10) What is a deadlock in threads, and how does it occur?

Answer: A deadlock occurs when two or more threads are blocked forever, each waiting for the other to release a resource. It typically arises when there are circular dependencies among threads.

### 11) What is a race condition, and how can it be avoided?

Answer: A race condition occurs when multiple threads access shared data simultaneously, leading to unpredictable results. It can be avoided using synchronization mechanisms like synchronized methods, locks, or concurrent data structures.

## Exception Handling
### 1) What is an exception in Java?
Answer: An exception is an event that disrupts the normal flow of the program’s execution. It is an object that encapsulates an error condition.

### 2) What is the difference between checked and unchecked exceptions?
Answer:
- Checked Exceptions: These are checked at compile-time and must be either caught or declared in the method signature (e.g., IOException).
- Unchecked Exceptions: These occur at runtime and are not required to be caught or declared (e.g., NullPointerException).

### 3)What are the main keywords used in exception handling in Java?
Answer: The main keywords are:
- try: Block of code to be tested for exceptions.
- catch: Block of code that handles the exception.
- finally: Block that executes regardless of whether an exception occurred.
- throw: Used to explicitly throw an exception.
- throws: Indicates what exceptions may be thrown by a method.

### 4) What is the difference between Error and Exception in Java?
Answer:
- Error: Represents serious problems that a reasonable application should not catch (e.g., OutOfMemoryError).
- Exception: Represents conditions that a program might want to catch.

### 5) What is the try-with-resources statement in Java?
Answer: The try-with-resources statement is a try block that declares one or more resources, automatically closing them after execution, which is helpful for managing resources like files or network connections.

### 6) What happens if an exception is not caught in Java?
Answer: If an exception is not caught, it propagates up the call stack until it reaches the Java Runtime Environment, which terminates the program and prints the stack trace.

## Regular Expressions (Regex)
### 1) What is a regular expression in Java?
A regular expression is a sequence of characters that defines a search pattern. It is used for string matching and manipulation in Java through the java.util.regex package.

### 2)How do you compile a regular expression in Java?

You can compile a regular expression using the Pattern.compile() method, which returns a Pattern object. For example: Pattern pattern = Pattern.compile("regex");

### 3)What is the purpose of the Matcher class in Java?
The Matcher class is used to perform matching operations on a Pattern. It provides methods to find, replace, and extract information from strings based on the defined pattern.

### 4) What is the difference between find() and matches() methods in the Matcher class?
The find() method searches for the next subsequence of the input sequence that matches the pattern, while the matches() method checks if the entire input sequence matches the pattern.

### 5)How can you use regular expressions to validate an email address in Java?
You can use a regular expression pattern that matches the structure of a valid email address and utilize the Matcher class to check if the email string matches the pattern.

### 6)What does the \d pattern represent in a regular expression?

The \d pattern represents any digit (equivalent to [0-9]).

### 7) What is the purpose of the replaceAll() method in the String class?

The replaceAll() method is used to replace each substring of a string that matches a given regular expression with a specified replacement string.

### 8) How can you use regular expressions to split a string in Java?

You can use the String.split() method with a regular expression to divide a string into an array based on a specified delimiter pattern.

### 9) What is a character class in regular expressions?

A character class is a set of characters enclosed in square brackets (e.g., [abc] matches any single character a, b, or c). It allows for matching any one character from the set.

### 10) What does the ^ symbol indicate in a regular expression?

The ^ symbol indicates the start of a string when used at the beginning of a regex pattern. It ensures that the match occurs at the start of the input string.

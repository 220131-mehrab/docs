# Java 

## QC Topics
- Java: 
    - Programming Paradigms
    - JDK, JRE, JVM
    - First Java Program: HelloWorld
    - Control Flow
    - Statements
    - Compiling in Java
    - Class vs Object
    - String API
    - StringBuilder, StringBuffer
    - Packages and Imports
    - Constructors
    - Methods and Parameters
    - Variable Scopes
    - Arrays, Var-args, for-each loops
    - Access Modifiers
    - Non-access modifiers
    - Wrapper Classes
    - ArrayList and LinkedList
    - Garbage Collection
    - Stack and Heap
    - Reference Types
    - Read from console (Scanner)
    - File I/O: FileInputStream/FileReader/FileWriter
    - Annotations
    - Exception Handling or Declarations
    - Try-with-resources
    - Multi-catch blocks
    - Checked vs Unchecked Exceptions
    - Custom Exceptions
    - Exception Hierarchy
    - Pillars of OOP
    - Interfaces
    - Abstract Classes
    - Object class
    - Inheritance vs Composition
    - Method Overriding and Overloading
    - Generics
    - Comparable Interface
    - Comparator interface
    - Covarience
    - Java Widening and Narrowing
    - Maven Repositories
    - Project Coordinates
    - Maven Lifecycles
    - Project object model (POM)
    - Frameworks vs Libraries
    - Logging Levels
    - Setting Logging Threshold
    - Intro to TDD and Unit Testing
    - Assert Methods
    - JUnit Annotations
    - Overview of Logging

## Topic Breakdown
## Concepts
- Environment: bash, PATH, CLASSPATH, JAVA_HOME, command vs flag vs argument
- Memory memory model: stack, heap, String Pool, Garbage collector, threads
- Compile-time vs Runtime: source code vs bytecode
- OOP: Polymorphism, Encapsulation, Inheritance, Abstraction
- Source Code Management: Git, local vs remote, GitHub
- Project management: Gradle
- Unit testing: Test Driven Development

## Tools
- JDK: `javac`, `java`, `jar`
- Git subcommands `init`, `add`, `commit`, `checkout`, `merge`, `remote`, `clone`, `push`
- Gradle: `build`, `run`, `test`, `jar`

## Language Features
- Default Constructor
- Overloading and Overriding
- Checked vs Unchecked Exceptions
- Variable scopes: class/global, object/instance, method, block/loop, bracket

## Language Syntax
- Package & Import
- Class & method signatures: parameters, access modifiers, return types, constructors, varargs
- Access modfiers: public, protected, (default), private
- Non-access modifiers: static, final, abstract, synchronized
- Control statements: if, if else, else, while, do/while, for, switch, continue, break
- Primitive types: byte, short, int, long, char, boolean, float, double
- Reference types: Classes, Enums, Interfaces, Arrays
- Inheritance: extends, implements
- Exception handling: try, catch, finally
- Generics: type inference, type erasure, bounded types

## Standard Library
- [java.lang](https://docs.oracle.com/javase/8/docs/api/java/lang/package-summary.html)
  - [Object](https://docs.oracle.com/javase/8/docs/api/java/lang/Object.html): `toString()`, `hashcode()`, `equals()`, `finalize()`, `notify()`
  - [String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html), [StringBuilder](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html) & [StringBuffer](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuffer.html)
  - Wrapper Classes: [Integer](https://docs.oracle.com/javase/8/docs/api/java/lang/Integer.html), [Double](https://docs.oracle.com/javase/8/docs/api/java/lang/Double.html), etc.
  - [Iterable](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html): `forEach()`
  - [Comparable](https://docs.oracle.com/javase/8/docs/api/java/lang/Comparable.html): `compareTo()`
  - [System](https://docs.oracle.com/javase/8/docs/api/java/lang/System.html): `System.in`, `System.out`, `getenv()`, `gc()`
  - [Throwable](https://docs.oracle.com/javase/8/docs/api/java/lang/Throwable.html): [Error](https://docs.oracle.com/javase/8/docs/api/java/lang/Error.html), [Exception](https://docs.oracle.com/javase/8/docs/api/java/lang/Exception.html), [RuntimeException](https://docs.oracle.com/javase/8/docs/api/java/lang/RuntimeException.html)
- [java.io](https://docs.oracle.com/javase/8/docs/api/java/io/package-summary.html)
  - [File](https://docs.oracle.com/javase/8/docs/api/java/io/File.html)
  - [BufferedReader](https://docs.oracle.com/javase/8/docs/api/java/io/BufferedReader.html) & [BufferedWriter](https://docs.oracle.com/javase/8/docs/api/java/io/BufferedWriter.html)
- [java.util](https://docs.oracle.com/javase/8/docs/api/java/util/package-summary.html)
  - [StringTokenizer](https://docs.oracle.com/javase/8/docs/api/java/util/StringTokenizer.html)
  - [Scanner](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html)
  - [Java Collections Framework](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/index.html):
    - [Collection](https://docs.oracle.com/javase/8/docs/api/java/util/Collection.html):
      - [Map](https://docs.oracle.com/javase/8/docs/api/java/util/Map.html): [Hashtable](https://docs.oracle.com/javase/8/docs/api/java/util/Hashtable.html), [HashMap](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html), [TreeMap](https://docs.oracle.com/javase/8/docs/api/java/util/TreeMap.html)
      - [List](https://docs.oracle.com/javase/8/docs/api/java/util/List.html): [ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html)
    - [Iterator](https://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html)
    - [Comparator](https://docs.oracle.com/javase/8/docs/api/java/util/Comparator.html)

## Questions
- What is Java? What are the benefits of Java?
- What is the difference between the JRE, JDK, and JVM?
- What happens during the compilation process?
- What is a constructor?
- What are the primitive data types?
- What is a no args constructor?
- What is the default constructor?
- What are the scopes of a variable in java?
- What are the different access modifiers?
- What are the different control statements and how are they different?
- How do you create an array in java?
- What are varargs?
- What are packages and imports?
- What is a static import?
- What is static?
- What are Strings?
- What are some string methods?
- What is the difference between String, StringBuilder, and StringBuffer?
- What is the String Pool?
- What is the difference between the stack and the heap?
- What is an exception?
- What is the difference between exception and error?
- What are the ways one can handle an exception?
- What are checked exceptions and unchecked exceptions?
- How many catch blocks can be used in a try catch?
- What does the finally block do?
- How do I create a custom exception?
- What is autoboxing?
- What is a wrapper class?
- What is garbage collection?
- What are the pillars of object oriented programming?
- What is the difference between an abstract class and an interface?
- What are the differences between FileInputStream, FileReader, and BufferedReader (and their output counterparts)?
- What are generics? Why use them?
- What is the difference between Comparator and Comparable?
- What is the purpose of the Object class?
- What is the difference between  == and .equals?
- What is the purpose of hashcode?
- What is JUnit?
- What are the annotations of JUnit?
- What are the different assert methods of JUnit?
- How do I create a test case and test suite in JUnit?

## Resources
### Articles
- [Data Structures and Algorithms in Java](https://www.javaworld.com/article/3527188/data-structures-and-algorithms-in-java-a-beginners-guide.html)
- [Java Versions and Features](https://www.marcobehler.com/guides/a-guide-to-java-versions-and-features)
- [Java Programming Cheatsheet](https://introcs.cs.princeton.edu/java/11cheatsheet/)
- [JVM Internals](https://blog.jamesdbloom.com/JVMInternals.html)
- [JVM Performance Optimization](https://www.javaworld.com/article/2078623/core-java-jvm-performance-optimization-part-1-a-jvm-technology-primer.html)
- [How the JVM Handles Exceptions](https://www.javaworld.com/article/2076868/how-the-java-virtual-machine-handles-exceptions.html)
- [How the JVM Performs Thread Synchronization](https://www.javaworld.com/article/2076971/how-the-java-virtual-machine-performs-thread-synchronization.html)

### Books
- [The Java Language Environment](https://www.oracle.com/java/technologies/language-environment.html)
- [Think Java](https://books.trinket.io/thinkjava/index.html)
- [Wikibooks - Java Programming](https://en.wikibooks.org/wiki/Java_Programming)
- [Introduction to Programming Using Java, Eighth Edition](http://math.hws.edu/eck/cs124/javanotes8/)
- [Open Data Sructures (in Java)](http://opendatastructures.org/ods-java/)
- [Inside the Java Virtual Machine](https://www.artima.com/insidejvm/ed2/)

### Documentation
- [Java Platform Standard Edition 8 Documentation](https://docs.oracle.com/javase/8/docs/index.html)
- [Java Platform Overview](https://docs.oracle.com/javase/8/docs/technotes/guides/index.html)
- [Enhancements in Java SE 8](https://docs.oracle.com/javase/8/docs/technotes/guides/language/enhancements.html)
- [Java Virtual Machine and Language Specifications](https://docs.oracle.com/javase/specs/index.html)
- [The java.lang.* and java.util.* Packages](https://docs.oracle.com/javase/8/docs/technotes/guides/lang/index.html)
- [The Collections Framework](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/index.html)
- [Java I/O](https://docs.oracle.com/javase/8/docs/technotes/guides/io/index.html)
- [Java Generics](https://docs.oracle.com/javase/tutorial/extra/generics/)
- [Java Archive (JAR) Files](https://docs.oracle.com/javase/8/docs/technotes/guides/jar/index.html)
- [Java Networking](https://docs.oracle.com/javase/8/docs/technotes/guides/net/index.html)
- [OpenJDK 8 documentation](https://devdocs.io/openjdk~8/)
- [OpenJDK 8 Standard Library](https://hg.openjdk.java.net/jdk8/jdk8/jdk/file/687fd7c7986d/src/share/classes/java)
- [JUnit 5](https://junit.org/junit5/docs/current/user-guide/)

### Tutorials
- [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/index.html)
- [Java SE 8 Programmer I Exam Prep](https://docs.oracle.com/javase/tutorial/extra/certification/javase-8-programmer1.html)
- [IBM Intro to Java Programming](https://developer.ibm.com/series/intro-to-java-programming/)
- [Learn X in Y - Java](https://learnxinyminutes.com/docs/java/)
- [Baeldung](https://www.baeldung.com/)
- [Jenkov](http://tutorials.jenkov.com/)
- [Tutorialspoint](https://www.tutorialspoint.com/java/index.htm)

### Design Patterns
- [Java Design Patterns](https://java-design-patterns.com/)
- [The Catalog of Design Patterns](https://refactoring.guru/design-patterns/catalog)

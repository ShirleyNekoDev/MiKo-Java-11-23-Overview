[Project Panama](https://openjdk.org/projects/panama/)
================

- new foreign function and memory API
- safer replacement for Java Native Interface (JNI)
- remove the need to write intermediate native code wrappers in Java
- replace ByteBuffer API with more future-proof memory API
- introduce platform-agnostic, secure, and memory-efficient way to invoke native code


## [JEP 454: Foreign Function & Memory API](https://openjdk.org/jeps/454) (Java 17-22)
-> Incubator JEP 412 builds on top of
  - [JEP 393: Foreign-Memory Access API (Third Incubator)](https://openjdk.org/jeps/393) (Java 14-16)
  - [JEP 389: Foreign Linker API (Incubator)](https://openjdk.org/jeps/389) (Java 16)

A Linker is a bridge between two binary interfaces: the JVM and C/C++ native code, also known as C ABI.


The Foreign function and Memory API helps Java programs interoperate with code and data outside of the Java runtime.

It does this by efficiently invoking foreign functions (i.e., code outside the JVM) and by safely accessing foreign memory (i.e., memory not managed by the JVM).

It combines two earlier incubating APIs: the Foreign-Memory Access API and the Foreign Linker API.

The API provides a set of classes and interfaces to do these:

allocate foreign memory with MemorySegment, MemoryAddress, and SegmentAllocator
control the allocation and deallocation of foreign memory through Arena (MemorySession was split into Arena and SegmentScope, starting with JDK20)
manipulate structured foreign memory using MemoryLayout
access structured foreign memory via VarHandles
call foreign functions thanks to Linker, FunctionDescriptor, and SymbolLookup


 Foreign Memory Allocation
First, let’s explore memory allocation. Here, the main abstraction is MemorySegment. It models a contiguous region of memory located either off-heap or on-heap. MemoryAddress is an offset within a segment. Simply put, a memory segment is made of memory addresses, and a memory segment can contain other memory segments.

Besides, memory segments are bound to their encapsulated Arena and are released when no longer required. The Arena manages the segments’ lifecycles and ensures they are properly freed when accessed by multiple threads.


Foreign Memory Manipulation
Next, we dive into memory manipulation with memory layouts. A MemoryLayout describes a segment’s content. It’s useful to manipulate high-level data structures of native code such as structs, pointers, and pointers to structs.

Let’s use a GroupLayout to allocate off-heap a C struct representing a point with x and y coordinates:


Native Function Calls From Java
Foreign Function API allows Java developers to consume any native library without relying on a third-party wrapper. It heavily relies on Method Handles and provides three main classes: Linker, FunctionDescriptor, and SymbolLookup.


With JExtract, there’s no need to directly use most of the Foreign Function & Memory API abstractions. Let’s recreate printing our “Hello World” example above.

First, we need to generate Java classes from the standard library headers:

jextract --source --output src/main -t foreign.c -I c:\mingw\include c:\mingw\include\stdio.h


## [JEP 472: Prepare to Restrict the Use of JNI](https://openjdk.org/jeps/472) (Java 24)
issue warnings on use of JNI & FFM API to prepare developers for a future release that ensures integrity by default by uniformly restricting this access
- users have to explicitly enable these interfaces at startup when required


## Related

- [JEP 193: Variable Handles](https://openjdk.org/jeps/193) (Java 9)
  - API for safe, performant memory access
  - replaces `java.util.concurrent.atomic` and `sun.misc.Unsafe` operations 

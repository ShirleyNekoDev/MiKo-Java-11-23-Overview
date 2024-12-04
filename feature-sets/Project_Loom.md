[Project Loom](https://openjdk.org/projects/loom/)
==============

- normal Threads in Java are OS kernel threads
  - concurrent number not scalable to millions
  - use OS scheduler
    - no differentiation between work threads (e.g. same task -> same core)
    - have thread-synchronization
    - expensive context switches between kernel threads
  - heavy-weight = big footprint because they include native call stack
- Java provides asynchronous concurrent APIs on top of threads for finer-grained concurrency
  - harder to debug and integrate with legacy APIs
- new lightweight, high-throughput concurrency model
  - user-mode threads / virtual-threads / fibers / "green-threads"
  - Java runtime implementation of continuations (coroutines)
  - Java runtime scheduler which can schedule tasks based on relationship information
- tail-call elimination

Fibers
------
- wrap any task in an internal user-mode continuation
- cheap to create and block
- allow nesting
- use pluggable user-mode scheduler (default scheduler: ForkJoinPool in asynchronous mode)
- suspend and resume in Java runtime
  - starts at entry point
  - suspends at yield point
  - whenever caller resumes continuation, control returns to last yield point


## [JEP 428: Structured Concurrency (Incubator)](https://openjdk.org/jeps/428) (Java 19)
API for structured concurrency
- structure multiple tasks as single unit of work
- streamline error handling and cancellation
- improve reliability
- enhance observability


## [JEP 444: Virtual Threads](https://openjdk.org/jeps/444) (Java 19-21)
lightweight virtual threads on Java platform (green-threads)



## [JEP 487: Scoped Values (Fourth Preview)](https://openjdk.org/jeps/487) (Java 20-24)
share immutable data with callees within a thread and with child threads
- easier reasoning about dataflow compared to thread-local variables
- lifetime comprehensibility apparent from syntatic code structure
- efficient data sharing across threads


## Resources
- [Structured Concurrency in Practice](https://docs.oracle.com/en/java/javase/21/core/structured-concurrency.html)
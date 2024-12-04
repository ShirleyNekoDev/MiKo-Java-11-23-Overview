[Project Leyden](https://openjdk.org/projects/leyden/)
================

- make Java programs start faster
- reduce time to peak performance
- reduce CPU & memory footprint


## [JEP 483: Ahead-of-Time Class Loading & Linking](https://openjdk.org/jeps/483) (Java 24)
improve startup time by caching a captured load and link state of classes and reusing it on the next startup


## [JEP draft: Ahead-of-Time Code Compilation](https://openjdk.org/jeps/8335368)
store precompiled code in AOT cache


## [JEP draft: Ahead-of-Time Method Profiling](https://openjdk.org/jeps/8325147)
store precomputed method profiles in AOT cache


## Related

- [JEP 310: Application Class-Data Sharing](https://openjdk.org/jeps/310) (Java 10)
  - share common class metadata across different Java processes
  - archive class data for faster future startups
- [JEP 350: Dynamic CDS Archives](https://openjdk.org/jeps/350) (Java 13)
  - dynamic archiving of classes at end of execution

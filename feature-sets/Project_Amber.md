[Project Amber](https://openjdk.org/projects/amber/)
===============

- explore and incubate smaller, productivity-oriented Java language features
- make Java feel like a modern language (like Kotlin)


## [JEP 286: Local-Variable Type Inference](https://openjdk.org/jeps/286) (Java 10)
allow var for inferrable variable types


## [JEP 323: Local-Variable Syntax for Lambda Parameters](https://openjdk.org/jeps/323) (Java 11)
allow automatic parameter types inferrence of implicitly typed lambda expressions


## [JEP 361: Switch Expressions](https://openjdk.org/jeps/361) (Java 14)
switch can now be used as an expression


## [JEP 378: Text Blocks](https://openjdk.org/jeps/378) (Java 15)
multi-line string literal that avoids the need for most escape sequence
- automatically formats the string in a predictable way
- gives the developer control over the format when desired


## [JEP 394: Pattern Matching for instanceof](https://openjdk.org/jeps/394) (Java 14-16)
- allow pattern matching for instanceof operator


## [JEP 395: Records](https://openjdk.org/jeps/395) (Java 14-16)
record classes as transparent carriers for immutable data ("tuples")
  - opt out of separate internal state (vs value classes ([Project Valhalla](./Project_Valhalla.md)) to opt out of identity)

- [JEP 468: Derived Record Creation (Preview)](https://openjdk.org/jeps/468)
  - derive new record objects from old record objects


## [JEP 465: String Templates (Third Preview)](https://openjdk.org/jeps/465) (Java 21-22)
!! string templates are currently back in draft status !!


## [JEP 476: Module Import Declarations (Preview)](https://openjdk.org/jeps/476) (Java 23)
import all of the packages exported by a module


## [JEP 488: Primitive Types in Patterns, instanceof, and switch (Second Preview)](https://openjdk.org/jeps/488) (Java 23-24)
- allow primitive types in all pattern matching contexts
- extend instanceof and switch to work with primitive types


## [JEP 492: Flexible Constructor Bodies (Third Preview)](https://openjdk.org/jeps/492) (Java 22-24)
(JEP 447: Statements before super(...))

allow statements that do not reference the instance being created to appear before an explicit constructor invocation
- useful for argument validation or data generation


## [JEP 495: Simple Source Files and Instance Main Methods (Fourth Preview)](https://openjdk.org/jeps/495) (Java 21-24)
(JEP 445: Unnamed Classes and Instance Main Methods), (JEP 463: Implicitly Declared Classes and Instance Main Methods)

allows writing a simple Java program with less builerplate code
- (main) method outside of main class (implicitly generated)
- automatic import of useful methods like `println` (`System.out`)


## Resources
- [Pattern Matching](https://openjdk.org/projects/amber/design-notes/patterns/pattern-matching-for-java)

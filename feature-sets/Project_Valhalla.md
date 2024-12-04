[Project Valhalla](https://openjdk.org/projects/valhalla/)
==================

!! mostly in separate JVM previews or drafts !!

- "adapt the Java language and runtime to modern hardware"
  - memory fetch operations are now ~ 200-1000 times more expensive than arithmetic operations
  - indirection from pointer fetches is bad for performance!
  - Java objects are pointer-heavy (regular class supports: object-identity, synchronization, ...)
- remove indirection for data structures which do not need advanced functionality
- reduce memory usage by flattening object graphs into a packed layout
- add language support for null-restricted and nullable types
- converge primitive and object types
- improves memory footprint, locality, and garbage collection efficiency


## [JEP 401: Value Classes and Objects (Preview)](https://openjdk.org/jeps/401)
add value objects: class instances that have only final fields and lack object identity (pure data aggregates)
- distinguished (equality) solely by their field values
- highly-efficient small 'objects' without inheritance
- still reference types (like regular classes, not only a struct), stored in heap space
- allows JVM to flatten value types into arrays, objects, and (to an extent) into other value types
- can still be null, are references on heap requiring atomical modification
- currently used for `java.util.Optional` and DateTime API (internally via `@jdk.internal.ValueBased`)

### Primitive classes
- act like regular Java primitives, can not be null
- can be stored in stack memory, belonging to its own thread
- instances = composition of primitive types with additional utility methods
- can implement interfaces, can be used as generic types
- -> faster objects & user-defined primitives
- -> migrate boxed primitive wrapper classes (Integer, Float, ...)
  - deprecate their constructor [JEP 390: Warnings for Value-Based Classes](https://openjdk.org/jeps/390)


## [JEP 402: Enhanced Primitive Boxing (Preview)](https://openjdk.org/jeps/402)
enhance boxing to allow treating primitive types more like reference types
- unify treatment of reference and primitive types in generics
- allow primitive types in type variables instead of their boxed equivalent
- related to [JEP 218: Generics over Primitive Types](https://openjdk.org/jeps/218), [JEP draft: Universal Generics (Preview)](https://openjdk.org/jeps/8261529)
- removes need for dedicated classes like `IntStream`, `ToIntFunction`, ...


## [JEP draft: Null-Restricted Value Class Types (Preview)](https://openjdk.org/jeps/8316779)
allow type of a variable storing a value objects to exclude null
- new kind of valee classes like primitive types that cannot be null
- allow opting in to automatic creation of appropriate default values


## Related

- [JEP 395: Records](https://openjdk.org/jeps/395) (Java 14-16)
  - record classes as transparent carriers for immutable data ("tuples")
  - [Project Amber](./Project_Amber.md)
  - records are used to opt out of separate internal state, while value classes are used to opt out of identity
- [Project Lilliput](./Project_Lilliput.md) is orthogonal and complementary to project Valhalla (also reducing object memory size)

Sind wir bereit für Java 23? - Übersicht neuer (Preview-)Features seit Java 11
==============================================================================

Leyden & Lilliput, Jigsaw & Loom, Panama & Valhalla, Amber & Shenandoah – all dies sind Projekte unter OpenJDK, die die Java-Sprache und Java-VM weiterentwickeln sollen. Wir werden uns anschauen welche neuen Features in den letzten Jahren vorgestellt wurden und worauf wir uns in der Java-Zukunft noch freuen können.

Wir werden uns auf 3 Hauptschwerpunkte fokussieren: Javas Implementierung von Coroutinen mittels virtueller Threads und Structured Concurrency; neue Sprach-Features und Syntactic Sugar rund um Records, Pattern-Matching und String-Templates; sowie die neue Schnittstelle für native Funktionsaufrufe, Off-Heap-Speicher und Vektoroperationen. Falls noch Zeit ist können wir auch darauf eingehen, wie die JVM-Startzeit reduziert werden kann und was mittlerweile für alternative Garbage-Collector existieren.

Diese MiKo soll auch ein Recap für alle Projekte bieten, die zuletzt den Feature-Stand von Java 11 verwenden mussten und zeigen, was mit den LTS-Versionen Java 17 und 21 möglich wird und welche API-Änderungen sich in der Zeit ergeben haben.


Why so many new Java versions?
------------------------------
- "new" 6-month feature release model (since Java 9 2018)
- releases each March / September with support period until next release
- LTS versions every 2 years (3 years before Java 17)
- push many new features in shorter time with less presure to make it in time for the next release
- allow experimental features and collect feedback iteratively


Feature Types
-------------
- normal features
- preview features
  - fully specified and implemented, but not yet permanent
  - to gather developer feedback based on real-world use before making the feature permanent
  - enabled via --enable-preview compiler flag
- experimental features
  - early versions of features, often at the VM level, which can be risky, incomplete, or unstable
  - to test and iterate on new ideas that are not yet ready for broader use
  - enabled using specific flags
- incubating features ([Incubator](https://openjdk.org/jeps/11))
  - experimental APIs distributed as separate modules prefixed with jdk.incubator.
  - to allow developers to try out new APIs that are still in development
  - modules need to be explicitly added to the project


Overview
--------
- [Project Jigsaw](./feature-sets/Project_Jigsaw.md):
  module system for the Java language, JDK sources and Java runtime
- [Project Amber](./feature-sets/Project_Amber.md):
  small utilities & syntactic sugar to make development easier
- [Project Loom](./feature-sets/Project_Loom.md):
  new lightweight, high-throughput concurrency model
- [Project Panama](f./eature-sets/Project_Panama.md):
  foreign function and memory API
- [Project Valhalla](./feature-sets/Project_Valhalla.md):
  value classes, primitive classes, and primitive generics
- [Project Lilliput](./feature-sets/Project_Lilliput.md):
  reduce object header size
- [Project Leyden](./feature-sets/Project_Leyden.md):
  improve startup time, time to peak performance, and footprint of Java programs
- [Features Outside of Projects](./feature-sets/others.md)

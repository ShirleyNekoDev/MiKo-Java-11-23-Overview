[Project Lilliput](https://openjdk.org/projects/lilliput/)
==================

- shrink object header size from 128 bit to 64 bit (or even 32 bit)
- make header layout more flexible (build-/run-time)

Results:
- reduced heap usage -> less memory pressure -> reduced GC activity
- higher object allocation rate
- tighter packing of objects -> better cache locality


## [JEP 450: Compact Object Headers (Experimental)](https://openjdk.org/jeps/450) (Java 24)
on 64-bit architectures: reduce object headers size down to 64 bits

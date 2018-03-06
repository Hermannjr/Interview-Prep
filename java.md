> Describe and compare fail-fast and fail-safe iterators. Give examples.

https://www.toptal.com/java/interview-questions
https://docs.oracle.com/javase/tutorial/tutorialLearningPaths.html

---

## Understanding JVM Internals
https://www.cubrid.org/blog/understanding-jvm-internals/

* Java Virtual Machine (JVM) - analyzes and executes Java byte code

### Virtual Machine
The **Virtual machine** is a software implementation of a machine (computer), executing programs like a physical machine. **WORA**, or write once, run anywhere is what the java VM was originally built for. 

JVM Features:
* **Stack-based** - x86 and ARM run based on a register. JVM runs based on a stack.
* **Symbolic reference** - All types (class and interface) *except for primitives* are referred to ythrough symbolic reference, instead of through explicit memory address-based reference.
* **Garbage collection** - Class instances are explicitly created by the user code, and automatically destroyed by the GC.
* **Clearly defined primitive data types** - Unlike C/C++, the JVM clearly defines the primitive data types to maintain compatibility and guarantee platform independence.
* **Network byte order** - Java class files use network byte order. This is to maintain platform independence between the little endian used by Intel x86 and the big endian by RISC. JVM uses the network byte order, which is used for network transfer. Network byte order is big endian byte order.

![./Images/Big-Endian.svg](./Images/Big-Endian.svg)

---

## Monitoring tools
JFR - https://docs.oracle.com/javacomponents/jmc-5-5/jfr-runtime-guide/toc.htm
Troubleshooting (Java 8) - https://docs.oracle.com/javase/8/docs/technotes/guides/troubleshoot/toc.html

## What's new in Java 8
> http://www.baeldung.com/java-8-new-features

## What's new in Java 9
> https://docs.oracle.com/javase/9/whatsnew/toc.htm
> http://www.baeldung.com/new-java-9

## Garbage Collector
https://docs.oracle.com/javase/9/gctuning/toc.htm

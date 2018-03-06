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

Differnt VMs:
* Oracle Hotspot JVM
* Oracle JRockit
* IBM J9
* SAP JVM
* Azul Zulu
* Azul Zing
* Google's Android JVM, Dalvik, though not byte code compatible since it's register based

### Java bytecode
We can use tools like **javap** to disassemble class files into human-readable bytecode. As an example, the following method:

```java
// UserService.java
…
public void add(String userName) {
    admin.addUser(userName);
}
```

would look like this:

```java
public void add(java.lang.String);
  Code:
   0:   aload_0
   1:   getfield        #15; //Field admin:Lcom/nhn/user/UserAdmin;
   4:   aload_1
   5:   invokevirtual   #23; //Method com/nhn/user/UserAdmin.addUser:(Ljava/lang/String;)V
   8:   return
```

The fourth instruction uses **invokevirtual** to invoke the method corresponding to the 23rd index. The *javap* program annotates the method with the name and namespace added as a comment. 

These are the OpCodes that invoke a method in Java Bytecode:
* **invokeinterface** - invokes an interface method
* **invokespecial** - invokes an initializer, private method, or superclass method
* **invokestatic** - invokes static methods
* **invokevirtual** - invokes instance methods

The instruction set of Java Bytecode consists of OpCode and Operand. In this case, the OpCode for invokevirtual requires a 2-byte Operand. The number in front of the instruction is the byte number. Instruction OpCodes such as *aload_0*, *getfield*, and *invokevirtual* are expressed as a 1-byte byte number (*aload_0* = 0x2a, *getfield* = 0xb4, *invokevirtual* = 0xb6). Therefore, the maximum number of OpCodes is limited to 256.

OpCodes such as aload_0 and aload_1 don't need any Operand, that's they the next instruction follows with the next byte. However, getfield and invokevirtual require the 2-byte Operand, and thus, the next instruction is written on the fourth byte, skipping two additional bytes. The resulting bytecode in the class file looks like this then:

```
2a b4 00 0f 2b b6 00 17 57 b1
```


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

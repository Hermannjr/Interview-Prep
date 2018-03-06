## Checklist
[] - Data structures
[] - Sorting
[] - Searching
[] - JVM
[] - Garbage collection
[] - Instrumentation
[] - Serialization
[] - Memory sizes
[] - JIT 


## Application Performance Concepts


## Memory Management

## Garbage Collection

### Weak Generational Hypothesis and Little's Law
**Theorem:** The mean lifetime of a heap allocated object is equal to the mean amount of reachable storage.
Proof: This is Little's Law with λ=1.

This turns out to be a pretty handy theorem. Here's an example.

In a prior post, I mentioned that a prerequisite for effective garbage collection is that the amount of reachable storage must at all times be less than the amount of memory available for the heap. We apply Little's Law and get this: The mean lifetime of a heap allocated object must be less than the time it takes to exhaust the heap.

That naturally follows: in order for garbage collection to “work”, we need something to become garbage before we completely run out of memory. But Little's Law allows us to make a much stronger statement. The mean lifetime of all objects (where lifetime is measured in subsequent allocations), is, by Little's Law, equal to the mean size of reachable storage. The mean size of the reachable storage has to be less than the amount of memory available for the heap. Since the mean lifetime of an object must be small, and we have the occasional very long-lived object, it must be the case that the vast majority of objects have very short lifetimes. Or in other words, 

> Most allocated objects die young.

This statement is often called the weak generational hypothesis. It is usually presented as an empirical observation. By Little's Law, it is equivalent to saying that the size of the reachable objects is small, which is not a hypothesis, but a strong pre-condition of garbage collection.



https://docs.oracle.com/javase/8/docs/platform/jvmti/jvmti.html
https://www.dynatrace.com/resources/ebooks/javabook/
Garbage Collection

https://www.cubrid.org/blog/understanding-java-garbage-collection

https://stackify.com/what-is-java-garbage-collection/

https://stackify.com/our-code-has-performance-problems-too/

http://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html

https://www.geeksforgeeks.org/garbage-collection-java/

https://www.dynatrace.com/resources/ebooks/javabook/how-garbage-collection-works/

https://www.dynatrace.com/news/blog/understanding-g1-garbage-collector-java-9/


JAVA:
https://www.dynatrace.com/news/blog/java-9-language-features/

https://www.dynatrace.com/news/blog/whats-ahead-with-java-9-project-jigsaw/

https://www.dynatrace.com/news/blog/new-ways-introducing-compiled-code-java-9/

WeakRefrence vs SoftReference
http://javarevisited.blogspot.co.at/2014/03/difference-between-weakreference-vs-softreference-phantom-strong-reference-java.html

Garbage Collection
http://javarevisited.blogspot.co.at/2011/04/garbage-collection-in-java.html
https://www.artima.com/insidejvm/ed2/gcP.html
NOTE: READ PART ABOUT FINALIZERS!!!
https://docs.oracle.com/javase/8/docs/technotes/guides/vm/gctuning/toc.html



READ THIS!!!
http://www.oracle.com/technetwork/java/javase/tech/memorymanagement-whitepaper-1-150020.pdf




APM:
https://www.dynatrace.com/news/blog/trades-of-a-performance-engineer-in-2020/

https://www.dynatrace.com/news/blog/using-dynatrace-monitor-rpa-robotic-process-automation-robots-botfarms/

https://www.dynatrace.com/news/blog/using-dynatrace-ai-based-monitoring-ensure-blockchain-performance/




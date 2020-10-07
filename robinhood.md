## <a name='toc'>Table of Contents</a>

- [Object Oriented Programming](#ood)
- 

#### [[⬆]](#toc) <a name='ood'>Object Oriented Programming:</a>
<br>
- **Inheritance vs Composition**

  - Inheritance means some type belongs to another more generic type, for example, Apple is a fruit. It's called "is-a" relationship
  - Composition means a class can have many parts of code, and those parts can be reused in other classes. So it's more of a "has-a" relationship. Like "Bird has the fly functionality and so does plane"
  - Usually we prefer composition over inheritance, because the child class wont be have to tightly coupled with the parent class, and also helps separation of concerns. (Most programming languages also dont support multiple inheritance, and it's very confusing when used.)

#### [[⬆]](#toc) <a name='concurrency'>Concurrency:</a>

- **Thread vs Process vs Program**
  - **Thread** is the smallest unit of execution for CPU
  - **Process** is the program which is actively running, including its threads
  - **Program** is a set of instructions, represented by code that can executed plus its data
- **Multi-threading vs Multi-processing**
```
Multi-threading still share the same resource and does not necessarily mean doing multiple computations simultaneously. The CPU could be switching back and forth between the theads so many tasks can share the same CPU. While multi-processing takes advantage of multiple CPU-cores or multiple processors, and do not share resources between tasks.
```
- **Example of Multi-threading** <br>
Word will have one thread for keyboard input, one thread for rendering, another for saving files etc

- **Race Condition** 
A race condition occurs when two or more threads can access shared data and they try to change it at the same time. Because the thread scheduling algorithm can swap between threads at any time, you don’t know the order in which the threads will attempt to access the shared data. 

- **Deadlock**
Deadlock is a situation where a set of processes are blocked because each process is holding a resource and waiting for another resource acquired by some other process.

```
A deadlock happens when all four conditions are met: 
1. Mutual Exclusion (only one process can access a resource at given time)
2. Hold and Wait (process asks for other resource while already holding a resource)
3. No Preemption (one process cannot remove resource from another process)
4. Circular Wait (the processes form a circular chain in terms of resource dependency)
```

- **How to prevent deadlock**




#### [[⬆]](#toc) <a name='concurrency'>Concurrency:</a>
 

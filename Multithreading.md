Multithreading
====

#Issues and problems with multithreading

*Resources:*
[Common problems of concurrency](http://www.somanyword.com/2014/03/common-problems-of-concurrency-multi-threading-in-java/)
[](http://www.intuit.ru/studies/courses/14040/1281/lecture/24125)

1. **Atomicity**

In concurrent environment two or many threads can run concurrently, if all threads are trying to update some shared resource concurrently, there might be chance that threads trying to read shared resource get stale data and produce wrong outputs. To resolve this issue, it is necessary to make such critical code atomic. Atomicity is to create any operation atomic, in such way that operation can be performed in a single attempt. If a critical section of code is getting execute by only one thread at a time and no other thread can enter in this section until that thread complete its execution. That means this critical section is atomic. You can make any critical section of code atomic by synchronization.

2. **Visibility**

Visibility of shared object could be different for different threads. This is one of the problems of multi-threading environment. Suppose there are two threads, one is writing any shared variable and other is reading from shared variable. When reading and writing will be occur in different threads, there is no guarantee that reader thread will see the value written by writer thread. This problem of multi-threading is known as visibility issue of shared resource. This problem can be resolved with proper synchronization of shared resource.

3. **Reordering**

Order of execution of code can be different as it is written in class. Because JVM rearrange this code according to its convenience, that is known as reordering. Today’s machines do run on multiple processors. To utilize these processors JVM split code to run with different processors, therefore order of code could be change during execution. There might be change that any critical section of code can generate wrong result after reordering of code. If you do not want to change the order of execution of code written then you will have to synchronize your critical code.

4. **Race Conditions**

A race condition occurs when the correctness of computation depends on the relative time or interleaving of multiple threads by the runtime. In other words, when getting the right answers relies on lucky timing. The most common type of race condition is check-then-act, where a potentially stale observation is used to make a decision on what to do next. You can resolve this problem by make your critical section atomic using proper synchronization.

5. **Livelock**

Livelock is a form of liveness failure in which a thread, while not blocked, still cannot make progress because it keeps retrying an operation that will always fail. Livelock often occurs in transaction a messaging applications, where the messaging infrastructure rolls back a transaction if a message cannot be processed successfully, and puts it back at the head of the queue.

6. **Starvation**

Starvation occur when a thread is denied and not getting access to resource to progress its task. The most common starved resource is CPU cycles. Starvation in Java application can be caused by inappropriate use of thread priorities. For example two thread of same priority is trying to access a common resource and each thread allowing other thread to have its access first. In such situation no thread could get access of resource. That means both threads are suffering from starvation.

7. **Deadlock**

Deadlock occur when two of many thread are waiting for two or more resources, where each thread need to get access on all resources to progress and those resources are acquired by different threads and waiting for other resources to be release, which will not be possible ever. For example, two threads A and B need both resources X and Y to perform their tasks. If thread A acquires resource X and thread B acquires Y and now both threads are waiting for resources to be release by other thread. Which is not possible and this is called deadlock. You need to take care of the way of your synchronization if this is going to be a cause of deadlock.

#Sync primitives
*Resources:*
[Wiki page](https://ru.wikipedia.org/wiki/%D0%9C%D0%BD%D0%BE%D0%B3%D0%BE%D0%BF%D0%BE%D1%82%D0%BE%D1%87%D0%BD%D0%BE%D1%81%D1%82%D1%8C)

1. **MuText - mutuallly exclusive access**


2. **Semaphore** 

3. **Events**

4. **Critical sections**

5. **[Conditional variables](https://ru.wikipedia.org/wiki/%D0%A3%D1%81%D0%BB%D0%BE%D0%B2%D0%BD%D0%B0%D1%8F_%D0%BF%D0%B5%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F)** 

6. ****

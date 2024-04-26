## Overview

A thread is an extremely lightweight process, or the smallest component of the process, that enables software to work more effectively by doing numerous tasks concurrently.

Some of its uses include the fact that server-side programs employ it since a server should be multi-threaded so that many clients can be served at once.

Multithreading in Java is a process of executing multiple threads simultaneously. The main reason for incorporating threads into an application is to improve its performance.
Games and animations can also be made using threads.

overview of threads in Java:

1. **Thread Creation:** There are two primary ways to create threads in Java:
- Extending the Thread class: You can create a new class that extends the Thread class and override its run()
 method to define the code that the thread will execute.
- Implementing the Runnable interface: You can create a class that implements the Runnable interface and implement its run()
method. Then, you can pass an instance of this class to a Thread object.

2. **Thread States:** Threads in Java can be in one of several states:
   
- New: The thread has been created but has not yet started.
- Runnable: The thread is ready to run and is waiting for the scheduler to allocate processor time.
- Blocked/Waiting: The thread is waiting for a certain condition to occur (e.g., I/O operations or waiting for a lock).
- Terminated: The thread has completed its execution.
  
3. Thread Synchronization: In multi-threaded environments, it's crucial to ensure thread safety when multiple threads access shared resources
   concurrently. Java provides several mechanisms for thread synchronization, such as:
- Synchronized Blocks/Methods: Using the synchronized keyword to ensure that only one thread can execute a block of code or method at a time.
- Locks: Using explicit lock objects from the java.util.concurrent.locks package, such as ReentrantLock, for more fine-grained control over synchronization.
- Atomic Variables: Using classes from the java.util.concurrent.atomic package, such as AtomicInteger, to perform atomic operations on variables without explicit synchronization.

5. **Thread Lifecycle Management:** Java provides methods to manage the lifecycle of threads, such as:
   
- Starting a Thread: Invoking the start() method on a Thread object to begin its execution.
- Joining Threads: Using the join() method to wait for a thread to finish its execution before proceeding.
- Interrupting Threads: Using the interrupt() method to interrupt the execution of a thread, causing it to throw an InterruptedException if it's in a blocked or waiting state.

## What is Multithreading in Java?
Multithreading is a feature in Java that concurrently executes two or more parts of the program for utilizing the CPU at its maximum. 
The part of each program is called Thread which is a lightweight process.

According to the definition, it can be deduced that it expands the concept of multitasking in the program by allowing certain operations to
be divided into smaller units using a single application.

Each Thread operates concurrently and permits the execution of multiple tasks inside the same application.

## Multithreading vs. Multiprocessing in Java

Multithreading                                             |                                          	Multiprocessing
---------------------------------------------------------------------------------------------------------------------------
In this, multiple threads are created for    	             |           In this, CPUs are added in order to increase computational power. 
increasing computational power using a single process.  
---------------------------------------------------------------------------------------------------------------------------
Many threads of a process are executed simultaneously.	                          Many processes are executed simultaneously.
---------------------------------------------------------------------------------------------------------------------------
It is not classified into any categories.	                                Classified into two categories, symmetric and asymmetric.
---------------------------------------------------------------------------------------------------------------------------
The creation of a process is economical.                                          	Creation of a process is time-consuming.
---------------------------------------------------------------------------------------------------------------------------
In this, a common space of address is shared by all threads.	               Every process in this owns a separate space of address.


## How does Java Support Multithreading?

Java supports multithreading through its built-in features for creating and managing threads. It provides a __Thread__ class that can 
be extended to create custom threads or __Runnable__ interface to define tasks for threads. To use it, you can either extend the Thread 
class and override its __run()__ method to define the thread's task or implement the Runnable interface and pass an instance of the class 
to the Thread constructor. The __start()__ method is then called to begin the execution of the thread, which runs concurrently with other
threads in the JVM, enabling multithreading capabilities.

What are the different types of threads?
In Java, there are two main types of threads: user threads and daemon threads. User threads are created by 
the application and continue to run until their task is completed or the application terminates. On the other hand, daemon 
threads are background threads that are automatically terminated when there are no more user threads running. These daemon threads 
are useful for tasks like garbage collection, etc.

## What is the Use of Multi-Thread in Java?

Because each Thread is managed individually and several operations can be carried out at once, the user is not blocked.
It is used to save time as multiple operations are performed concurrently.
Since threads are independent, other threads don’t get affected even if an exception occurs in a single thread.

## Methods of Multithreading in Java

The following are methods used for Multithreading in Java.

Methods	Description
**void start()**	Causes the Thread to begin execution
**void run()**	Utilised to carry out a thread's action.
**long getId()**	Returns the identifier of the thread
**final String getName()**	Returns the threads name
**final void setName(String name)**	Sets the name of the thread
**final int getPriority()**	Returns thread’s priority
**final void setPriority(int newPriority)**	Changes the priority if the thread
**boolean isAlive()**	It checks to see if the Thread is alive.
**void suspend()**	It is used to suspend the Thread.
**void resume()**	The suspended Thread is resumed using it.
**void stop()**	The Thread is stopped using it.
**void destroy()**	The thread group and all of its subgroups are destroyed using it.
**static void sleep(long millis)** throws InterruptedException	Causes the currently executing Thread to sleep (temporarily cease execution)
for the specified number of milliseconds.
final void join() throws InterruptedException	Waits for the Thread to die
**void interrupt()**	It interrupts the Thread.
**boolean isinterrupted()**	It checks to see if the Thread has been interrupted.
**static boolean interrupted()**	It checks to see whether the current Thread has been interrupted.
**static int activeCount()**	It gives back how many threads are currently active in the thread group of the current Thread.
**void checkAccess()**	It determines if the currently running Thread has permission to modify the Thread.
**Thread.State getState()**	It is used to return the state of the Thread.
**void notify()**	It is used to give the notification for only one Thread that is waiting for a particular object.
**void notifyAll()**	It is used to give notification to all waiting threads of a particular object.

### 1. Extending the Thread class:
```java

class MyThread extends Thread {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Thread running: " + i);
            try {
                Thread.sleep(1000); // Sleep for 1 second
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread1 = new MyThread();
        MyThread thread2 = new MyThread();
        
        thread1.start();
        thread2.start();
    }
}
'''
In this example, we create a subclass MyThread that extends the Thread class and overrides its run() method. We then
create two instances of MyThread and start them using the start() method. Each thread prints numbers from 0 to 4 with a delay of 1 second between each iteration.

### 2. Implementing the Runnable interface:
```java


class MyRunnable implements Runnable {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Thread running: " + i);
            try {
                Thread.sleep(1000); // Sleep for 1 second
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread1 = new Thread(new MyRunnable());
        Thread thread2 = new Thread(new MyRunnable());
        
        thread1.start();
        thread2.start();
    }
}
```
In this example, we create a class MyRunnable that implements the Runnable interface and defines its run() method. We then create
two Thread objects, passing instances of MyRunnable to their constructors. The rest of the code is similar to the previous example.

## Multithreading in Java provides several benefits:

- Concurrency: Multithreading allows different parts of a program to execute concurrently, improving overall program responsiveness and performance.
- Resource Utilization: By utilizing multiple CPU cores, multithreading enables better resource utilization and faster execution of tasks.
- Asynchronous Programming: Multithreading facilitates asynchronous programming, enabling non-blocking execution of I/O operations and background tasks.
- Modularity and Maintainability: Multithreading allows developers to modularize code and separate concerns, making programs easier to understand, maintain, and scale.
- 
However, multithreading also introduces challenges such as race conditions, deadlocks, and thread synchronization issues. Proper synchronization
mechanisms and best practices are essential to
ensure thread safety and prevent these issues in multithreaded Java applications.

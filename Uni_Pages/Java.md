---
layout: default
title: Java
---


##Software Workshop 2

###Recursive Programming and Data Structures



#####Lists

#####Trees

#####AVL Trees



###Collection classes 

#####Sets and Maps

#####Interfaces

###Java Type System

#####Subtyping

Liskov Substitution Principle

    A <: B if, whenever B type objects are needed, a type A object can be used
    
Remember:   A <: B __does not mean that__ List<A> <: List<B>


#####Generics



###GUI classes

#####Event Handling



###Threads 


```java

public class ThreadA extends Thread throws InterruptedException  {

    public void run() {
        System.out.println("Hello from a thread!");
    }

```

The thread can be started  and stopped as follows:
```java
    ThreadA myThread = new ThreadA();
    myThread.start();
or 

    myThread.join();  //makes this thread wait until myThread has finished executing`
```

or alternatively

```java
    myThread.interrupt() //generates an InterruptedException in myThread
```
See [thread example](http://docs.oracle.com/javase/tutorial/essential/concurrency/simple.html) in Java Tutorials


####Synchronized



 * every object has an intrinsic lock associated with it

 * synchronizing a method by `public synchronized void myMethod()` automatically thocks the `this` object when the method is invoked and releases it when the method returns

 * using a 

```java
    synchronized(myObject){
	//some stuff in here
     }
```
only locks myObject whilst the statements between the { } are executing.  __Need to make sure I understand the example on Tutorials website__

 * it is not possible for two synchronized methods _of the same object_ to execute at the same time

 *  if an object is visible to more than one thread, all reads or writes to that object's variables are best donethrough `synchronized` methods

 
See [synchronization](http://docs.oracle.com/javase/tutorial/essential/concurrency/syncmeth.html) in Java Tutorials


####Deadlock and Starvation

Need to make sure that I can spot deadlock in code as well as describing with a practical example.

Basically seems to occur if a thread synchronizes on 2 objects and another thread synchronizes on them in the opposite order.

See [Deadlock](http://docs.oracle.com/javase/tutorial/essential/concurrency/deadlock.html) in Java Tutorials

####Sockets and Streams

Socket commands

 * Server side:

```java
ServerSocket listener = new ServerSocket(8787);  //port number goes in here
    while(true){
	Socket clientSocket = listener.accept();  	//gets a new socket for the client connection
	ThreadA client = new ClientHandler(clientSocket, spr);					
	Thread t = new Thread(client);
	t.start();	
    } // end while
}
 
```
 * Client side - `Socket cs = new Socket();`

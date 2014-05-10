---
layout: default
title: Java
---

##Software Workshop 2

##Recursive Programming and Data Structures

####Lists
####Trees
####AVL Trees

##Collection classes and Java Type Systems
####Sets and Maps
####Interfaces
####Subtyping
####Generics

##GUI classes
####Event Handling

##Threads and Networks
######Syntax for thread class

```java
public class ThreadA extends Thread {

    public void run() {

    }

}

```




######Interruption
Need to allow for threads to be interrupted - does this by adding __`throws InterruptedException__` to method declaration.

This is then caught as follows:

```java
public void run() {
    try{

      //method body goes here

    }
    catch (InterruptedException e)  {

      //perform clean up

    }

}

```


####Synchronized
* every object has an intrinsic lock associated with it
* if a method is `synchronised` it automatically obtains the lock when the method is invoked and releases it when the method returns
* it is not possible for two synchronized methods _of the same object_ to execute at the same time
* if we use the `synchronized(myObject);` statement this allows for only acquiring the lock on the object for as long as it is needed.  __Need to make sure I understand the example on Tutorials website__
*  if an object is visible to more than one thread, all reads or writes to that object's variables are done through `synchronized` methods
 
See [synchronization](http://docs.oracle.com/javase/tutorial/essential/concurrency/syncmeth.html) in Java Tutorials

####Deadlock and Starvation

Need to make sure that I can spot deadlock in code as well as describing with a practical example.

See [Deadlock](http://docs.oracle.com/javase/tutorial/essential/concurrency/deadlock.html) in Java Tutorials


####Sockets and Streams

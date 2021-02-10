# General interview questions

## 1. What is the difference between `NULL` and `Void`?

>TODO

## 2. What is an Object and a Class?

### Class

* Works as a blueprint for creating objects with specific properties.
* Data type that is a collection of data members and member functions. 
* Defines the kids of data and the functionality of its objects will have. 

### Object

* A class data type variable - an instance of the class.
* A block of memory that has been allocated and configured according to the class. 
* The objects/instances can be stored in a variable of a reference type or in a collection.

## 3. What are the fundamental OOP concepts? (The 4 pillars)

### Inheritance

* Ability to `receive` methods and properties from an existing class
* Ability to create a new class from a similar existing class.
* A process of object reusability.

### Polymorphism

* Each class implements the same methods, but they can change in different ways methods to specific characteristics.
* One function behaves in different ways in classes.
* Many forms of the single object.
* Static polymorphism (compile) - function overloading and operator overloading.
* Dynamic polymorphism (runtime) - function overriding.

### Abstraction

* Hides unnecessary details from type consumers - giving abstract design.
* Focus on what the object does rather that how it does it.

### Encapsulation

* Binds member function and data member into a single unit - class.
* Enclosing related operations and data into an object.
* Hiding the internal details for the object from the outside.

## 4. What is an Interface?

* An interface works as a contract between between its functionalities and the functionalities of the entities that implement the interface.
* An interface can contain declaration of methods, properties, indexers and events. Can not contain fields or implementations of methods. 
* Interface members are public by default, can not apply access modifiers. 
* A class or a struct can implement one or more interfaces. 


## 5. What is Multithreading?

>TODO

## 6. What is a `Deadlock` ?

* A situation in the multi-threading programming that two or more threads are frozen in their execution because they are waiting for each other to finish. 
* A *lock* is a shared object that can be Acquired by a Thread, and then Released. It is a way to synchronize between Threads. Usually a Lock is placed around a critical section when we want a single Thread at a time.
* Deadlock occurs when:
    - a limited number of a particular resource.
    - the ability to hold one resource and request another.
    - no preemption capability (using before the other thread). One thread can't force another thread to release a lock.
    - a circular wait condition.
* To avoid a Deadlock, the most common solutions are to use timeout value ( `System.Threading.Monitor` ), avoid unnecessary locks and avoid nested locks. 

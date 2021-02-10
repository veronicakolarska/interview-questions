# Design patterns interview questions

## 1. What is a design pattern? Why do we need it?

### Why do we need a design pattern?

Design patterns solve common problems like:
 - how to properly create a class - what fields it should have, access modifiers and methods
 - how to instantiate an object - use a method, a helper class or just an operator `new`
 - interaction between objects - parsing, how to call a method from one object to another
 - how to write loosely coupled code
 - how to write reusable code 

### What is a design pattern?

 - well-defined template for a solution to a common problem
 - proven standard approach, not a `copy-paste` solution
 - language independent
 - easy to maintain code

## 2. Types of design patterns

>TODO
### Structural
- 
- examples: Adapter, Facade, Bridge

### Creational
- 
- examples: Singleton, Factory, Bridge

### Behavioral
- how one class interacts with another class
- examples: Strategy, Observer, Iterator

### Non-categorized
- examples: MVC, Dependency injection

## 3. Singleton pattern

* A singleton is a class that allows only once instance of itself to be created.
* Usually singletons don't allow any parameters to be specified when creating the instance.
* They are created with a single constructor, which is private and parameterless.
* This way the creation of subclasses is prevented.
* Typically the instance is not created until needed.
* The class is sealed (not necessary, but may help the JIT).
* A static variable which holds a reference to the single created instance, if any.
* A public static means of getting the reference to the single created instance, creating one if necessary.

## 4. Facade pattern

>TODO
* hides all the internal / technical details from the consumer
* use only an abstraction; an interface of the module
* possible problems: oversimplification or over-verticalization (so specific to a use case that is no longer useful to be in general use)
* example: a compiler

## 5. Bridge pattern

>TODO
* using an abstract interface - can use different concrete implementations and everything is working

## 6. Strategy pattern

>TODO

## 7. Observer pattern

>TODO
* allows loose coupling between the publisher (that creates the events) and the subscriber (listening for the events)
* good practice is to use a specific message bus for every event

## 8. SOLID Design principles in `C#`

* S - Single Responsibility Principle
* O - Open Closed Principle
* L - Liskov Substitution Principle
* I - Interface Segregation Principle
* D - Dependency Inversion Principle

## 9. Single Responsibility principle

>TODO
* a class / interface should only have one responsibility
* divide class / interface into separate ones depending on functionality 

## 10. Open Closed Principle

>TODO
* class or software entity should be open for extension but closed for modification
* use abstract class as a base class for the most common functionality
* use separate classes for different implementation of abstract methods and create the child object and assign to parent

## 11. Liskov Substitution principle

>TODO
* object should be replaced with instance of its subtype without altering the correctness of the program
* base class instance replaced by its subtype instance will not change the functionality 

## 12. Interface Segregation Principle

>TODO

## 13. Dependency Inversion Principle

>TODO

## 14. MVC

>TODO

## 15. Dependency injection

>TODO

## 16. Repository pattern

>TODO

## 17. Best practices

- Keep it simple (KISS) - easy to understand
- Design first, code later - look at the bigger picture
- Focus on loosely coupling - easy to expand later
- Excess of everything can be bad - use design patterns to actually make the code better

## 18. How to implement a singleton design pattern in C#? And what about a thread safe singleton?

### Non-thread safe (bad example)

``` csharp
public sealed class Singleton
    {
    private static Singleton instance=null;

    private Singleton()
    {
    }

    public static Singleton Instance
    {
        get
        {
            if (instance==null)
            {
                instance = new Singleton();
            }
            return instance;
        }
    }
}
```

### Simple thread safety

``` csharp
public sealed class Singleton
{
    private static Singleton instance = null;
    private static readonly object padlock = new object();

    Singleton()
    {
    }

    public static Singleton Instance
    {
        get
        {
            lock (padlock)
            {
                if (instance == null)
                {
                    instance = new Singleton();
                }
                return instance;
            }
        }
    }
}
```
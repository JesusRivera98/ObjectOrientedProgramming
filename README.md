# ObjectOrientedProgramming
## OOP
### What is?


### Pillars
* [Encapsulation](#encapsulation)
* [Inheritance](#inheritance) 
* [Polymorphism](#polymorphism)
* [Abstraction](#abstraction)


### Advantages


## Inheritance
> Inheritance can be defined as the process where one class acquires the properties (methods and fields) of another. With the use of inheritance the information is made manageable in a hierarchical order.

The class which inherits the properties of other is known as subclass (derived class, child class) and the class whose properties are inherited is known as superclass (base class, parent class).

### extends Keyword
extends is the keyword used to inherit the properties of a class. Following is the syntax of extends keyword.

```Java
class Super {
   .....
   .....
}
class Sub extends Super {
   .....
   .....
}
```

### The super keyword
> The super keyword is similar to this keyword. Following are the scenarios where the super keyword is used.

* It is used to differentiate the members of superclass from the members of subclass, if they have same names.
* It is used to invoke the superclass constructor from subclass. 

```Java
super.variable
super.method();
```

### Invoking Superclass Constructor
> If a class is inheriting the properties of another class, the subclass automatically acquires the default constructor of the superclass. But if you want to call a parameterized constructor of the superclass, you need to use the super keyword as shown below.

```Java
super(values);
```
### IS-A Relationship
> IS-A is a way of saying: This object is a type of that object. Let us see how the extends keyword is used to achieve inheritance.

```Java
public class Animal {
}

public class Mammal extends Animal {
}

public class Reptile extends Animal {
}

public class Dog extends Mammal {
}
```

* Animal is the superclass of Mammal class.
* Animal is the superclass of Reptile class.
* Mammal and Reptile are subclasses of Animal class.
* Dog is the subclass of both Mammal and Animal classes.

If we consider the IS-A relationship:
* Mammal IS-A Animal
* Reptile IS-A Animal
* Dog IS-A Mammal
* Hence: Dog IS-A Animal as well

### The instanceof Keyword
> Let us use the instanceof operator to check determine whether Mammal is actually an Animal, and dog is actually an Animal.

### HAS-A relationship
> These relationships are mainly based on the usage. This determines whether a certain class HAS-A certain thing. This relationship helps to reduce duplication of code as well as bugs.

```Java
public class Vehicle{}
public class Speed{}

public class Van extends Vehicle {
   private Speed sp;
} 
```
___This shows that class Van HAS-A Speed.___

### Types
* **Single:**
  * A single super and a single subclass
* **Multi Level:**
  * A class inherits from another class that inherits from a super class
* **Herarchical:**
  * More than one class inherits from a superclass
* **Multiple:**
  * A class inherits from more than one super class (It is not supported by Java)

## Overriding
> If a class inherits a method from its superclass, then there is a chance to override the method provided that it is not marked final.
>The benefit of overriding is: ability to define a behavior that's specific to the subclass type, which means a subclass can implement a parent class method based on its requirement.
>In object-oriented terms, overriding means to override the functionality of an existing method.

In compile time, the check is made on the reference type. However, in the runtime, JVM figures out the object type and would run the method that belongs to that particular object.

### Rules
* The argument list should be exactly the same as that of the overridden method.
* The return type should be the same or a subtype of the return type declared in the original overridden method in the superclass.
* The access level cannot be more restrictive than the overridden method's access level. For example: If the superclass method is declared public then the overridding method in the sub class cannot be either private or protected.
* Instance methods can be overridden only if they are inherited by the subclass.
* A method declared final cannot be overridden.
* A method declared static cannot be overridden but can be re-declared.
* If a method cannot be inherited, then it cannot be overridden.
* A subclass within the same package as the instance's superclass can override any superclass method that is not declared private or final.
* A subclass in a different package can only override the non-final methods declared public or protected.
* An overriding method can throw any uncheck exceptions, regardless of whether the overridden method throws exceptions or not. However, the overriding method should not throw checked exceptions that are new or broader than the ones declared by the overridden method. The overriding method can throw narrower or fewer exceptions than the overridden method.
* Constructors cannot be overridden.

### Using the super Keyword
> When invoking a superclass version of an overridden method the super keyword is used.

## Polymorphism
> Polymorphism is the ability of an object to take on many forms. The most common use of polymorphism in OOP occurs when a parent class reference is used to refer to a child class object.

```Java
public interface Vegetarian{}
public class Animal{}
public class Deer extends Animal implements Vegetarian{}
```
Deer class is considered to be polymorphic since this has multiple inheritance.
* A Deer IS-A Animal
* A Deer IS-A Vegetarian
* A Deer IS-A Deer
* A Deer IS-A Object
```Java
Deer d = new Deer();
Animal a = d;
Vegetarian v = d;
Object o = d;
```
___All the reference variables d, a, v, o refer to the same Deer object in the heap.___

### Virtual Methods
> An overridden method is essentially hidden in the parent class, and is not invoked unless the child class uses the super keyword within the overriding method.


## Abstraction

> In Object-oriented programming, abstraction is a process of hiding the implementation details from the user, only the functionality will be provided to the user. In other words, the user will have the information on what the object does instead of how it does it.

In Java, abstraction is achieved using Abstract classes and interfaces.

### Abstract Class
A class which contains the abstract keyword in its declaration is known as abstract class.

* Abstract classes may or may not contain abstract methods, i.e., methods without body ( public void get(); )
* But, if a class has at least one abstract method, then the class must be declared abstract.
* If a class is declared abstract, it cannot be instantiated.
* To use an abstract class, you have to inherit it from another class, provide implementations to the abstract methods in it.
* If you inherit an abstract class, you have to provide implementations to all the abstract methods in it.

### Abstract Methods
If you want a class to contain a particular method but you want the actual implementation of that method to be determined by child classes, you can declare the method in the parent class as an abstract.

* abstract keyword is used to declare the method as abstract.
* You have to place the abstract keyword before the method name in the method declaration.
* An abstract method contains a method signature, but no method body.
* Instead of curly braces, an abstract method will have a semoi colon (;) at the end.

Declaring a method as abstract has two consequences −

* The class containing it must be declared as abstract.
* Any class inheriting the current class must either override the abstract method or declare itself as abstract.

> ___**Note:** Eventually, a descendant class has to implement the abstract method; otherwise, you would have a hierarchy of abstract classes that cannot be instantiated.___

## Encapsulation

Encapsulation is one of the four fundamental OOP concepts. The other three are inheritance, polymorphism, and abstraction.

> Encapsulation in Java is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.

To achieve encapsulation in Java:
* Declare the variables of a class as private.
* Provide public setter and getter methods to modify and view the variables values.

The public setXXX() and getXXX() methods are the access points of the instance variables of the class. Normally, these methods are referred as getters and setters. Therefore, any class that wants to access the variables should access them through these getters and setters.

### Benefits of Encapsulation
* The fields of a class can be made read-only or write-only.
* A class can have total control over what is stored in its fields.

## Interfaces


## Packages
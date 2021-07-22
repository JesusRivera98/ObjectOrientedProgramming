# ObjectOrientedProgramming
## OOP
### What is?


### Pillars


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


## Polymorphism


## Abstraction


## Ecapsulation


## Interfaces


## PAckages
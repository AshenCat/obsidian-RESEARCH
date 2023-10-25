### Encapsulation - Information hiding
Encapsulation is the packing of data and functions operating on that data into a single component restricting access to some of the object's components.
Encapsulation means that the internal representation of an object is generally hiddent from view outside of the object's definition.

### Abstraction - Implementation hiding
Abstraction is the mechanism which represent the essential features without including implementation details.

### Inheritance - Eliminate redundant code
Inheritance is the mechanism of basing an object or class upon another object (prototype-based inheritance) or class (class-based inheritance), retaining their implementation.

### Polymorpism - Common method, different results when inheriting
Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.

```java
class Animal {
  public void animalSound() {
    System.out.println("The animal makes a sound");
  }
}

class Pig extends Animal {
  public void animalSound() {
    System.out.println("The pig says: wee wee");
  }
}

class Dog extends Animal {
  public void animalSound() {
    System.out.println("The dog says: bow wow");
  }
}
```

### Abstract Class
Abstract classes allow you to create blueprints for concrete classes. But the inheriting class should implement the abstract method.

Abstract classes cannot be instantiated.

### Interface
interface is a blueprint that can be used to implement a class. The interface does not contain any concrete methods (methods that have code). All the methods of an interface are abstract methods.

An interface cannot be instantiated. However, classes that implement interfaces can be instantiated. Interfaces never contain instance variables but, they can contain public static final variables (i.e., constant class variables)


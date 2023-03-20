### Dynamic method dispatch
- is the mechanism in which a call to an overridden method is resolved at run time instead of compile time. 
- This is an important concept because of how Java implements run-time polymorphism.

- This is a mechanism in Java that allows a subclass to override a method of its superclass and execute its own implementation when the method is called.

- This mechanism is based on the concept of polymorphism, which allows objects of different types to be treated as if they are of the same type.

- In dynamic method dispatch, the method to be executed is determined at runtime based on the actual type of the object that invokes the method, rather than the declared type of the reference variable.

- To use dynamic method dispatch, the method in the superclass must be declared as either abstract or virtual. This allows the subclass to override the method and provide its own implementation.

The use of dynamic method dispatch provides flexibility in program design and promotes code reuse. It allows for the creation of generic code that can be used with different types of objects, as long as those objects share a common superclass.
### Advantages of dynamic method dispatch
- It allows Java to support overriding of methods, which are important for run-time polymorphism.
- It allows a class to define methods that will be shared by all its derived classes, while also allowing these sub-classes to define their specific implementation of a few or all of those methods.
- It allows subclasses to incorporate their own methods and define their implementation.

### Code
Here is an example illustrating dynamic method dispatch:
```Java
// Implementing Dynamic Method Dispatch

class Animal {
   public void sound() {
      System.out.println("The animal makes a sound");
   }
}

class Dog extends Animal {
   public void sound() {
      System.out.println("The dog barks");
   }
}

class Cat extends Animal {
   public void sound() {
      System.out.println("The cat meows");
   }
}

public class Main {
   public static void main(String args[]) {
      Animal animal1 = new Animal(); // create an Animal object
      Animal animal2 = new Dog(); // create a Dog object and assign it to an Animal reference
      Animal animal3 = new Cat(); // create a Cat object and assign it to an Animal reference

      animal1.sound(); // call the sound() method of Animal
      animal2.sound(); // call the sound() method of Dog
      animal3.sound(); // call the sound() method of Cat
   }
}
 
```

In this example, we have an Animal class with a sound() method that prints "The animal makes a sound". We also have two subclasses of Animal: Dog and Cat, each of which overrides the sound() method with its own implementation.

In the main() method, we create three objects: an Animal object, a Dog object, and a Cat object, and assign them to variables of type Animal. We then call the sound() method on each of these objects.

When we call animal1.sound(), the sound() method of the Animal class is called and "The animal makes a sound" is printed.

When we call animal2.sound(), the sound() method of the Dog class is called, even though the variable animal2 is of type Animal. This is because animal2 actually refers to a Dog object, and the sound() method is dynamically dispatched to the Dog class, which prints "The dog barks".

Similarly, when we call animal3.sound(), the sound() method of the Cat class is called, even though the variable animal3 is of type Animal. This is because animal3 actually refers to a Cat object, and the sound() method is dynamically dispatched to the Cat class, which prints "The cat meows".

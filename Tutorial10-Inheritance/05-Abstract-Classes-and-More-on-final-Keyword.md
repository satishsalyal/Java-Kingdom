># Abstract Classes and More on 'final' Keyword

## Abstract Class

- In Java, an abstract class is a class that cannot be instantiated directly, but can be subclassed by other classes. 
- It is designed to be used as a base class or template for other classes to extend from.

- An abstract class can have both abstract and non-abstract methods. 
- Abstract methods are methods that do not have an implementation in the abstract class, but must be implemented by any concrete subclass that extends the abstract class. 
- Non-abstract methods, on the other hand, have an implementation in the abstract class and can be inherited by any subclass.

To implement an abstract class in Java, you first need to declare it as abstract using the ```java abstract ``` keyword in the class declaration. Then, you can define abstract methods within the class using the same ```java abstract ``` keyword.

## Features of Abstract Class

### Template
The abstract class in Java enables the best way to execute the process of data abstraction by providing the developers with the option of hiding the code implementation. It also presents the end-user with a template that explains the methods involved.

### Loose Coupling
Data abstraction in Java enables loose coupling, by reducing the dependencies at an exponential level.

### Code Reusability
Using an abstract class in the code saves time. We can call the abstract method wherever the method is necessary. Abstract class avoids the process of writing the same code again.

### Abstraction
Data abstraction in Java helps the developers hide the code complications from the end-user by reducing the project's complete characteristics to only the necessary components.

### Dynamic Resolution
Using the support of dynamic method resolution, developers can solve multiple problems with the help of one abstract method.

**_Before moving forward, let’s first understand how to declare an abstract class._**

The Syntax for Abstract Class
To declare an abstract class, we use the access modifier first, then the "abstract" keyword, and the class name shown below.
```java
//Syntax:

<Access_Modifier> abstract class <Class_Name> {

//Data_Members;

//Statements;

//Methods;

}
```java


Here is an example:

##### [Example 01](../20-Examples/10-Inheritance/05-Abstract-Classes-and-More-on-final-Keyword/Example-01/)

```java
//abstract parent class
abstract class Animal{
   //abstract method
   public abstract void sound();
    //Non-abstract method
   public void eat() {
      System.out.println("Eating...");
}
```

```java
//Dog class extends Animal class
public class Dog extends Animal{

   public void sound(){
	System.out.println("Woof");
   }
   public static void main(String args[]){
	Animal obj = new Dog();
	obj.sound();
   }
}
```

##### Output

    Woof


## Using 'final' Keyword with Inheritance

While method overriding is one of Java’s most powerful features, there will be times when you will want to prevent it from occurring. To disallow a method from being overridden, specify `final` as a modifier at the start of its declaration. Methods declared as final cannot be overridden.

##### [Example 02](../20-Examples/10-Inheritance/05-Abstract-Classes-and-More-on-final-Keyword/Example-02/)

```java
class A {
   final void meth() {
      System.out.println("This is a final method.");
   }
}
```

```java
class B extends A {
   void meth() { // ERROR! Can't override.
      System.out.println("Illegal!");
   }
}
```

Because `meth()` is declared as final, it cannot be overridden in `B`. If you attempt to do so, a compile-time error will result.

## Using final to Prevent Inheritance

Sometimes you will want to prevent a class from being inherited. To do this, precede the class declaration with final. Declaring a class as final implicitly declares all of its methods as final, too. As you might expect, it is illegal to declare a class as both abstract and final since an abstract class is incomplete by itself and relies upon its subclasses to provide complete implementations.

```java
final class A {
   //...
}
// The following class is illegal.
class B extends A { // ERROR! Can't subclass A
   //...
}
```


># Strings

Strings in Java are Objects that are backed internally by a char array. Since arrays are immutable(cannot grow), Strings are immutable as well. Whenever a change to a String is made, an entirely new String is created. You will learn more about arrays in comming sections.

#### Creating a String

The most basic way of creating a string is

    String str = "Hello World";

As with any other objects in Java Strings can also created using 'new' keyword

##### [Example 01](../20-Examples/04-Data-Types/03-Strings/Example-01/)

```java
public class StringExample{
    public static void main(String[] args){
        // creating character array
        char[] arr = {'h','e','l','l','o'};
        // creating a String object
        String str = new String(arr);
        System.out.println(str);
    }
}
```

##### Output

    hello

You will learn about Onjects and 'new' keyword in Objects and Classes section.

#### [Some String Methods](../20-Examples/04-Data-Types/03-Strings/Example-02/)

##### Lenght of String
```java
String str = "Hello World";
int len = str.length();
System.out.println(len);
```
##### Output

    11

##### Concatenating two strings
```java
String str1 = "Hello";
String str2 = "World";

String str3 = str1.concat(str2);

System.out.println(str3);
System.out.println(str1 + str2);
System.out.println("Hello".concat(str2));
System.out.println("Hello" + "World");
```

##### Output

    HelloWorld
    HelloWorld
    HelloWorld
    HelloWorld


##### To get character at given index

Since a String is internally a character array index starts with 0
```java
String str = "Hello World";
System.out.println(str.charAt(0));
System.out.println(str.cahrtAt(6));
```
##### Output

    H
    W



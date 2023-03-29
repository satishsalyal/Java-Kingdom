## What is a Java string?

- A Java string is a sequence of characters that exists as an object of the class java.lang. 
- Java strings are created and manipulated through the string class. 
- Once created, a string is immutable -- its value cannot be changed.
- A string is sequence of characters.
-  A class is a user-defined template for creating an object. 
-  A string class is a user-defined template for creating and manipulating string objects, which are sequences of characters.

## Methods of class string enable the following capabilities:

- examining individual characters in the string;
- comparing strings;
- searching strings; and
- copying strings with characters converted from uppercase to lowercase or vice versa.

## Creating a Java string
### Below is one simple syntax for creating a Java string.

```java
String greeting = "Hello world!";
```
In this example, "Hello world!" is a string literal, which is a series of characters encased in quotation marks. 

### Another way to create strings is to use the new keyword
Since strings in Java are objects, we can create strings using the new keyword as well. For example,
```java
String s1 = new String("Hello world!");
```
That code will create an s1 string object and a reference variable.

### Example: Create Java Strings using the new keyword
```java
class Main {
  public static void main(String[] args) {

    // create a string using new
    String name = new String("Java String");

    System.out.println(name);  // print Java String
  }
}
```

### Methods of Java String


Besides those mentioned above, there are various string methods present in Java. Here are some of those methods:

 **Methods**	        Description
- **contains()**    	checks whether the string contains a substring
- **substring()**   	returns the substring of the string
- **join()**        	join the given strings using the delimiter
- **replace()**      	replaces the specified old character with the specified new character
- **replaceAll()**  	replaces all substrings matching the regex pattern
- **replaceFirst()**	replace the first matching substring
- **charAt()**      	returns the character present in the specified location
- **getBytes()**    	converts the string to an array of bytes
- **indexOf()**     	returns the position of the specified character in the string
- **compareTo()**   	compares two strings in the dictionary order
- **trim()**        	removes any leading and trailing whitespaces
- **split()**       	breaks the string into an array of strings
- **toLowerCase()** 	converts the string to lowercase
- **toUpperCase()**  	converts the string to uppercase
- **toCharArray()** 	converts the string to a char array
- **startsWith()**  	checks if the string begins with the given string
- **endsWith()**  	checks if the string ends with the given string




- String length(): The length() method is used to find the length of a string. 
   The syntax of the length() method is as follows:
   ```java
   String str = "Hello World";
int len = str.length();  // len will be 11
```

- String substring(int beginIndex, int endIndex): The substring() method is used to extract a portion of a string. 
The syntax of the substring() method is as follows:

```java
String str = "Hello World";
String subStr = str.substring(0, 5);  // subStr will be "Hello"

```
- String equals(String anotherString): The equals() method is used to compare two strings.
-  The syntax of the equals() method is as follows:

```java
String str1 = "Hello";
String str2 = "World";
boolean result = str1.equals(str2);  // result will be false

```

- String compareTo(String anotherString): The compareTo() method is used to compare two strings lexicographically. 
  The syntax of the compareTo() method is as follows:
  
  ```java
String str1 = "Hello";
String str2 = "World";
int result = str1.compareTo(str2);  // result will be negative (-15)

   ```
- String concat(String str): The concat() method is used to concatenate two strings. 
The syntax of the concat() method is as follows:

```java
String str1 = "Hello";
String str2 = "World";
String result = str1.concat(str2);  // result will be "HelloWorld"

```

- String replace(char oldChar, char newChar): The replace() method is used to replace all occurrences of a character in a string with another character.
The syntax of the replace() method is as follows

```java
String str = "Hello World";
String result = str.replace('o', 'a');  // result will be "Hella Warld"

```



# Java-Prep-Interview 🚀
 
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Code Style](https://img.shields.io/badge/Code%20Style-Standard-brightgreen.svg)](https://github.com/standard/standard)

<p align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java Logo" width="200" />
</p>

### Table of Contents
| Sr.No.        | Question      | 
| ------------- |-------------| 
| 1             |[What is difference between @Override & Overload ?]  (https://github.com/6531503042/Java-Prep-Interview/blob/main/README.md#1-what-is-difference-between-override--overload) |
| 2             |[Difference between GET & POST METHODS?](https://github.com/aatul/Java-Interview-Questions-Answers/blob/master/README.md#2-difference-between-get--post-methods) |
| 3             |[Difference between forward() method & SendRedirect() method?](https://github.com/aatul/Java-Interview-Questions-Answers/blob/master/README.md#3-difference-between-forward-method--sendredirect-method) |
| 4             |[Difference between HashMap and HashTable?](https://github.com/aatul/Java-Interview-Questions-Answers/blob/master/README.md#4-difference-between-hashmap-and-hashtable) |

### 1. What is difference between @Override & Overload ?

## - Override - Annotation -> @Override

1. **Same Method Signature**: The method in the subclass must have the same name, return type, and parameter list as the method in the superclass.
2. **Annotation**: It is good practice to use the `@Override` annotation to indicate that a method is being overridden.
3. **Access Modifier**: The access level cannot be more restrictive than the overridden method's access level in the superclass.
4. **Exceptions**: The subclass method can throw the same exceptions or fewer/less broad exceptions than the superclass method.
5. **Runtime Polymorphism**: Method overriding is a key feature of runtime polymorphism (or dynamic method dispatch) in Java.

 ### Example:
```java
// Parent class
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

// Child class
class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.sound(); // Output: Dog barks
    }
}

```
<!-- Override is allow subclass to provide a specific implementation of method that is already defined by on of it's parent classes or interfaces.
 - The method that inheritance the method must be the same name, return type, parameters as the parent class.
 - The sub-class that inheritance from parent must be at least as accessible or more than the method of the parent like if the parent class method is `public`, the child class method must also be `public`.
 - The Overriding method can throw any `Unchecked (runtime)` exceptions, whenever the overrided methood delcares them or not, But we can't throw `Checked` exception that are new or broaded than those declared by the overrided method. 
 - Method overriding is a key feature of polymorphism in Java. It allows a subclass to be treated as an instance of its superclass, and the overridden method will be called based on the actual object type (at runtime), not the reference type. -->

## - Overload - Annotation -> @Overload

1. **Same Method Name**: Overloaded methods must have the same name.
2. **Different Parameter Lists**: Overloaded methods must differ in the number, type, or order of parameters.
3. **Independent of Return Type**: The return type can be different, but it does not influence method overloading. Overloading is determined by the method signature (method name and parameter list) only.
.
 ### Example:

```java
public class Calculator {

    // Method to add two integers
    public int add(int a, int b) {
        return a + b;
    }

    // Overloaded method to add three integers
    public int add(int a, int b, int c) {
        return a + b + c;
    }

    // Overloaded method to add two doubles
    public double add(double a, double b) {
        return a + b;
    }

    // Overloaded method to add an integer and a double
    public double add(int a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println("Sum of 10 and 20: " + calc.add(10, 20)); // Calls add(int, int)
        System.out.println("Sum of 10, 20 and 30: " + calc.add(10, 20, 30)); // Calls add(int, int, int)
        System.out.println("Sum of 10.5 and 20.5: " + calc.add(10.5, 20.5)); // Calls add(double, double)
        System.out.println("Sum of 10 and 20.5: " + calc.add(10, 20.5)); // Calls add(int, double)
    }
}
```

Output
```bash
Sum of 10 and 20: 30
Sum of 10, 20 and 30: 60
Sum of 10.5 and 20.5: 31.0
Sum of 10 and 20.5: 30.5

```







<!-- | Override        | Overload      | 
| ------------- |-------------| 
|Overridingg os to allow a sub-class to provide a specific implementation of method that is already defined by one of its parent classed or interfaces.| |
|Not Secured because data is exposed in the URL bar.|Secured because data is not exposed in the URL bar.|
|Can be bookmarked|Cannot be bookmarked|
|Idempotent|Non-Idempotent|
|It is more efficient and use than Post|It is less efficient and used| -->




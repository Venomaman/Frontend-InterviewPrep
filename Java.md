### **1. Java Basics**

#### **1.1 Introduction to Java**

Java is a high-level, class-based, object-oriented programming language designed to have as few implementation dependencies as possible. It's used for building a range of applications, from mobile apps to enterprise systems.

**Key Features of Java:**
- **Platform Independence**: Java programs are compiled into bytecode which can run on any system that has a Java Virtual Machine (JVM). This feature is often referred to as "Write Once, Run Anywhere" (WORA).
- **Object-Oriented**: Java promotes the use of objects, which can encapsulate data and methods, making it easier to manage and maintain code.
- **Automatic Memory Management**: Java includes automatic garbage collection to manage memory and clean up unused objects.
- **Robustness**: Java provides strong memory management, exception handling, and a type-checking mechanism, enhancing reliability.

**Example: Hello World Program**

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!"); // Outputs Hello, World! to the console.
    }
}
```

**Explanation:**
- `public class HelloWorld`: Defines a public class named `HelloWorld`. In Java, everything happens inside classes.
- `public static void main(String[] args)`: The `main` method is the entry point of any Java application. The `String[] args` parameter allows command-line arguments to be passed to the program.
- `System.out.println("Hello, World!");`: This line prints the string "Hello, World!" to the console.

---

Certainly! Let’s dive into each topic from **Data Types and Variables** with detailed explanations and project examples to help you understand the concepts better. 

### **1. Java Data Types and Variables**

#### **1.1 Primitive Data Types**

Java has eight primitive data types, each designed to store a specific type of data. Here's a detailed look at each:

1. **byte**: 
   - **Size**: 8-bit
   - **Range**: -128 to 127
   - **Usage**: Useful for saving memory in large arrays.

2. **short**: 
   - **Size**: 16-bit
   - **Range**: -32,768 to 32,767
   - **Usage**: Useful for saving memory when you are sure the value will be within its range.

3. **int**: 
   - **Size**: 32-bit
   - **Range**: -2^31 to 2^31-1
   - **Usage**: Default choice for integer values.

4. **long**: 
   - **Size**: 64-bit
   - **Range**: -2^63 to 2^63-1
   - **Usage**: For larger integer values.

5. **float**: 
   - **Size**: 32-bit
   - **Range**: Approximately ±3.40282347E+38F
   - **Usage**: For floating-point numbers with less precision.

6. **double**: 
   - **Size**: 64-bit
   - **Range**: Approximately ±1.79769313486231570E+308
   - **Usage**: For floating-point numbers with double precision.

7. **char**: 
   - **Size**: 16-bit
   - **Range**: 0 to 65,535 (unsigned)
   - **Usage**: For single characters.

8. **boolean**: 
   - **Size**: Not precisely defined, typically 1-bit
   - **Range**: true or false
   - **Usage**: For true/false values.

**Example: Using Primitive Data Types**

```java
public class PrimitiveDataTypesExample {
    public static void main(String[] args) {
        byte b = 100;
        short s = 10000;
        int i = 100000;
        long l = 10000000000L;
        float f = 10.5f;
        double d = 100.123456;
        char c = 'A';
        boolean bool = true;

        System.out.println("Byte value: " + b);
        System.out.println("Short value: " + s);
        System.out.println("Int value: " + i);
        System.out.println("Long value: " + l);
        System.out.println("Float value: " + f);
        System.out.println("Double value: " + d);
        System.out.println("Char value: " + c);
        System.out.println("Boolean value: " + bool);
    }
}
```

**Explanation:**
- Each variable is declared with its specific type and initialized with a value.
- The `System.out.println` statements output the values of each variable.

---

#### **1.2 Non-Primitive Data Types**

Non-primitive data types are more complex than primitives and include classes, interfaces, and arrays.

1. **String**:
   - Represents a sequence of characters.
   - Immutable in Java.

2. **Arrays**:
   - A collection of variables of the same type.
   - Fixed size.

3. **Classes and Objects**:
   - **Class**: A blueprint for creating objects.
   - **Object**: An instance of a class.

**Example: Using Strings and Arrays**

```java
public class NonPrimitiveDataTypesExample {
    public static void main(String[] args) {
        // String Example
        String greeting = "Hello, World!";
        System.out.println("Greeting: " + greeting);

        // Array Example
        int[] numbers = {1, 2, 3, 4, 5};
        System.out.println("Array elements:");
        for (int number : numbers) {
            System.out.println(number);
        }
    }
}
```

**Explanation:**
- `String greeting = "Hello, World!";`: Declares and initializes a string.
- `int[] numbers = {1, 2, 3, 4, 5};`: Declares and initializes an array.
- The `for` loop iterates over the array elements and prints each one.

---

#### **1.3 Variables**

Variables are used to store data values. They need to be declared before use and can be of any data type.

**1. Variable Declaration and Initialization:**
- **Syntax:**
  ```java
  dataType variableName = value;
  ```

**2. Variable Scope:**
- **Local Variables**: Declared inside a method or block.
- **Instance Variables**: Declared inside a class but outside any method.
- **Class Variables (Static Variables)**: Declared with the `static` keyword.

**Example: Variable Scope and Initialization**

```java
public class VariableScopeExample {
    // Instance variable
    int instanceVariable = 10;
    
    // Class variable (Static)
    static int classVariable = 20;

    public static void main(String[] args) {
        // Local variable
        int localVariable = 30;
        
        // Creating an object to access instance variable
        VariableScopeExample example = new VariableScopeExample();
        
        System.out.println("Local Variable: " + localVariable);
        System.out.println("Instance Variable: " + example.instanceVariable);
        System.out.println("Class Variable: " + VariableScopeExample.classVariable);
    }
}
```

**Explanation:**
- **Local Variable**: `localVariable` is declared within the `main` method and is accessible only inside it.
- **Instance Variable**: `instanceVariable` belongs to an instance of the class and can be accessed through an object.
- **Class Variable**: `classVariable` is shared among all instances of the class and is accessed using the class name.

---

#### **1.4 Small Project: Simple Calculator**

Here’s a small project that uses various data types and variables to create a simple calculator.

**Project Code:**

```java
import java.util.Scanner;

public class SimpleCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter first number:");
        double num1 = scanner.nextDouble();

        System.out.println("Enter second number:");
        double num2 = scanner.nextDouble();

        System.out.println("Enter an operator (+, -, *, /):");
        char operator = scanner.next().charAt(0);

        double result;

        switch (operator) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                if (num2 != 0) {
                    result = num1 / num2;
                } else {
                    System.out.println("Error! Division by zero.");
                    return;
                }
                break;
            default:
                System.out.println("Error! Operator is not correct.");
                return;
        }

        System.out.println("Result: " + result);
        scanner.close();
    }
}
```

**Explanation:**
- **Scanner Class**: Used to get input from the user.
- **Data Types**: `double` for numerical inputs and `char` for the operator.
- **Switch Case**: Determines the operation based on user input.
- **Arithmetic Operations**: Performs the calculation based on the chosen operator.

This project integrates primitive data types, operators, and control flow statements into a practical application, reinforcing the concepts learned.

---
Sure! Let's move on to the next section: **Control Flow Statements**. I’ll provide detailed explanations, examples, and a small project to illustrate each control flow statement.

---

### **2. Control Flow Statements**

Control flow statements manage the execution of code based on certain conditions and loops.

#### **2.1 If-Else Statements**

**Purpose:** To execute code based on conditional checks.

**Syntax:**

```java
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

**Example:**

```java
public class IfElseExample {
    public static void main(String[] args) {
        int number = 15;

        if (number % 2 == 0) {
            System.out.println(number + " is even.");
        } else {
            System.out.println(number + " is odd.");
        }
    }
}
```

**Explanation:**
- The `if` statement checks if `number % 2 == 0` (even).
- If true, it prints that the number is even.
- Otherwise, it prints that the number is odd.

---

#### **2.2 Switch-Case Statements**

**Purpose:** To execute one block of code among many based on a variable’s value.

**Syntax:**

```java
switch (expression) {
    case value1:
        // Code to execute if expression == value1
        break;
    case value2:
        // Code to execute if expression == value2
        break;
    default:
        // Code to execute if expression doesn't match any case
}
```

**Example:**

```java
public class SwitchCaseExample {
    public static void main(String[] args) {
        int day = 4;

        switch (day) {
            case 1:
                System.out.println("Monday");
                break;
            case 2:
                System.out.println("Tuesday");
                break;
            case 3:
                System.out.println("Wednesday");
                break;
            case 4:
                System.out.println("Thursday");
                break;
            case 5:
                System.out.println("Friday");
                break;
            case 6:
                System.out.println("Saturday");
                break;
            case 7:
                System.out.println("Sunday");
                break;
            default:
                System.out.println("Invalid day");
        }
    }
}
```

**Explanation:**
- The `switch` statement evaluates the `day` variable.
- Based on its value, it prints the corresponding day of the week.
- The `default` case handles values not covered by the `case` labels.

---

#### **2.3 Loops**

Loops are used to execute a block of code repeatedly.

**1. For Loop:**
- **Purpose:** To iterate over a block of code a fixed number of times.

**Syntax:**

```java
for (initialization; condition; update) {
    // Code to execute
}
```

**Example:**

```java
public class ForLoopExample {
    public static void main(String[] args) {
        for (int i = 0; i < 5; i++) {
            System.out.println("i: " + i);
        }
    }
}
```

**Explanation:**
- The `for` loop initializes `i` to 0.
- Continues to loop while `i` is less than 5.
- After each iteration, `i` is incremented by 1.

**2. While Loop:**
- **Purpose:** To execute a block of code as long as the condition is true.

**Syntax:**

```java
while (condition) {
    // Code to execute
}
```

**Example:**

```java
public class WhileLoopExample {
    public static void main(String[] args) {
        int i = 0;
        while (i < 5) {
            System.out.println("i: " + i);
            i++;
        }
    }
}
```

**Explanation:**
- The `while` loop executes as long as `i` is less than 5.
- Inside the loop, it prints the value of `i` and then increments `i`.

**3. Do-While Loop:**
- **Purpose:** To execute a block of code at least once, then repeat while the condition is true.

**Syntax:**

```java
do {
    // Code to execute
} while (condition);
```

**Example:**

```java
public class DoWhileLoopExample {
    public static void main(String[] args) {
        int i = 0;
        do {
            System.out.println("i: " + i);
            i++;
        } while (i < 5);
    }
}
```

**Explanation:**
- The `do-while` loop executes the block of code at least once before checking the condition.
- The condition `i < 5` is checked after the code execution in each iteration.

---

#### **2.4 Small Project: Number Guessing Game**

Here's a small project that incorporates if-else statements, loops, and user input to create a number guessing game.

**Project Code:**

```java
import java.util.Scanner;
import java.util.Random;

public class NumberGuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        
        int numberToGuess = random.nextInt(100) + 1; // Number between 1 and 100
        int userGuess = 0;
        int attempts = 0;
        boolean hasGuessedCorrectly = false;

        System.out.println("Guess the number between 1 and 100:");

        do {
            userGuess = scanner.nextInt();
            attempts++;

            if (userGuess < numberToGuess) {
                System.out.println("Too low! Try again.");
            } else if (userGuess > numberToGuess) {
                System.out.println("Too high! Try again.");
            } else {
                hasGuessedCorrectly = true;
                System.out.println("Congratulations! You've guessed the number in " + attempts + " attempts.");
            }
        } while (!hasGuessedCorrectly);

        scanner.close();
    }
}
```

**Explanation:**
- **Scanner Class**: For user input.
- **Random Class**: To generate a random number to guess.
- **Do-While Loop**: Continuously prompts the user to guess until they guess correctly.
- **If-Else Statements**: Provide feedback on whether the guess is too high or too low.

---
Great! Let’s move on to the next section: **Methods and Functions**.

---

### **3. Methods and Functions**

Methods are blocks of code designed to perform a specific task. They can be defined once and called from multiple places within your program. 

#### **3.1 Defining and Calling Methods**

**Purpose:** To encapsulate code into reusable blocks, improving modularity and readability.

**Syntax:**

```java
returnType methodName(parameters) {
    // Code to execute
    return returnValue; // If returnType is not void
}
```

**Example:**

```java
public class MethodExample {
    public static void main(String[] args) {
        int result = add(10, 5); // Calling the method
        System.out.println("Sum: " + result);
    }

    // Method to add two numbers
    public static int add(int a, int b) {
        return a + b;
    }
}
```

**Explanation:**
- `public static int add(int a, int b)`: Defines a method named `add` that takes two integer parameters and returns their sum.
- `int result = add(10, 5);`: Calls the `add` method and stores the result in `result`.

---

#### **3.2 Method Overloading**

**Purpose:** To define multiple methods with the same name but different parameter lists. This allows for different implementations based on the number or type of arguments.

**Example:**

```java
public class MethodOverloadingExample {
    public static void main(String[] args) {
        System.out.println(sum(10, 20)); // Calls the first method
        System.out.println(sum(10, 20, 30)); // Calls the second method
    }

    // Method to add two integers
    public static int sum(int a, int b) {
        return a + b;
    }

    // Method to add three integers
    public static int sum(int a, int b, int c) {
        return a + b + c;
    }
}
```

**Explanation:**
- Both `sum` methods have the same name but different parameter lists.
- Java determines which method to call based on the number of arguments.

---

#### **3.3 Method Overriding**

**Purpose:** To provide a new implementation of a method inherited from a superclass.

**Syntax:**

```java
@Override
returnType methodName(parameters) {
    // New code to execute
}
```

**Example:**

```java
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog barks");
    }
}

public class MethodOverridingExample {
    public static void main(String[] args) {
        Animal myDog = new Dog();
        myDog.makeSound(); // Calls the overridden method
    }
}
```

**Explanation:**
- `makeSound()` in `Dog` overrides the `makeSound()` method in `Animal`.
- When `myDog.makeSound()` is called, it uses the overridden implementation in `Dog`.

---

#### **3.4 Recursive Methods**

**Purpose:** To solve problems by having a method call itself.

**Syntax:**

```java
returnType methodName(parameters) {
    if (baseCondition) {
        return baseValue;
    } else {
        // Recursive call
        return methodName(updatedParameters);
    }
}
```

**Example:**

```java
public class RecursiveExample {
    public static void main(String[] args) {
        int number = 5;
        System.out.println("Factorial of " + number + " is " + factorial(number));
    }

    // Method to compute factorial
    public static int factorial(int n) {
        if (n == 0) {
            return 1;
        } else {
            return n * factorial(n - 1);
        }
    }
}
```

**Explanation:**
- The `factorial` method calls itself to compute the factorial of a number.
- The base case is when `n` is 0, returning 1.

---

#### **3.5 Small Project: Simple Banking System**

Here’s a small project to demonstrate methods in action, including method overloading and recursive methods.

**Project Code:**

```java
import java.util.Scanner;

public class SimpleBankingSystem {
    private static double balance = 0.0;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int choice;
        
        do {
            System.out.println("1. Deposit");
            System.out.println("2. Withdraw");
            System.out.println("3. Check Balance");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter amount to deposit: ");
                    double depositAmount = scanner.nextDouble();
                    deposit(depositAmount);
                    break;
                case 2:
                    System.out.print("Enter amount to withdraw: ");
                    double withdrawAmount = scanner.nextDouble();
                    withdraw(withdrawAmount);
                    break;
                case 3:
                    checkBalance();
                    break;
                case 4:
                    System.out.println("Exiting...");
                    break;
                default:
                    System.out.println("Invalid choice!");
            }
        } while (choice != 4);

        scanner.close();
    }

    public static void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: " + amount);
        } else {
            System.out.println("Deposit amount must be positive.");
        }
    }

    public static void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrew: " + amount);
        } else {
            System.out.println("Invalid withdrawal amount or insufficient funds.");
        }
    }

    public static void checkBalance() {
        System.out.println("Current balance: " + balance);
    }
}
```

**Explanation:**
- **Deposit Method**: Adds money to the balance.
- **Withdraw Method**: Subtracts money from the balance if sufficient funds are available.
- **Check Balance Method**: Displays the current balance.
- The `do-while` loop provides a simple menu-driven interface for user interaction.

---


Certainly! Here’s an in-depth look at each core concept of Object-Oriented Programming (OOP), including their definitions, examples, and real-world applications. This detailed guide will help you understand how these concepts are implemented in real-world industry projects.

---

### **5. Object-Oriented Programming (OOP)**

#### **5.1 Classes and Objects**

**Purpose:** Classes define the blueprint for objects. Objects are instances of classes and represent real-world entities.

**Definition:**
- **Class:** A template for creating objects. It encapsulates data for the object and methods to manipulate that data.
- **Object:** An instance of a class. It has state (attributes) and behavior (methods).

**Example:**

```java
public class Car {
    // Fields (Attributes)
    private String model;
    private int year;

    // Constructor
    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    // Method (Behavior)
    public void displayInfo() {
        System.out.println("Model: " + model + ", Year: " + year);
    }

    public static void main(String[] args) {
        // Creating an object of Car
        Car myCar = new Car("Toyota Camry", 2020);
        myCar.displayInfo(); // Output: Model: Toyota Camry, Year: 2020
    }
}
```

**Real-World Application:**
- **Project Management System:** Define classes like `Project`, `Task`, and `TeamMember` to manage and track project details and activities.

---

#### **5.2 Encapsulation**

**Purpose:** Encapsulation is the concept of wrapping data (attributes) and methods (functions) into a single unit, a class. It restricts direct access to some of an object's components.

**Definition:**
- **Encapsulation:** Achieved using access modifiers like `private`, `protected`, and `public`. It hides the internal state and requires all interactions to be performed through methods.

**Example:**

```java
public class BankAccount {
    private double balance; // Private field

    // Constructor
    public BankAccount(double initialBalance) {
        this.balance = initialBalance;
    }

    // Getter method
    public double getBalance() {
        return balance;
    }

    // Setter method
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    // Public method to withdraw money
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }
}

public class BankingSystem {
    public static void main(String[] args) {
        BankAccount account = new BankAccount(1000.00);
        account.deposit(500.00);
        account.withdraw(200.00);
        System.out.println("Current Balance: " + account.getBalance()); // Output: 1300.00
    }
}
```

**Real-World Application:**
- **E-Commerce System:** Encapsulate order processing and payment handling to ensure secure transactions and prevent unauthorized modifications.

---

#### **5.3 Inheritance**

**Purpose:** Inheritance allows a new class to inherit properties and behaviors from an existing class. It supports code reusability and establishes a hierarchical relationship between classes.

**Definition:**
- **Superclass (Parent Class):** The class whose properties and methods are inherited.
- **Subclass (Child Class):** The class that inherits from the superclass. It can extend or override superclass methods.

**Example:**

```java
// Superclass
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

// Subclass
class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat(); // Inherited method
        myDog.bark(); // Subclass method
    }
}
```

**Real-World Application:**
- **Employee Management System:** Define a base `Employee` class and specialized subclasses like `Manager` and `Developer` to inherit common attributes and methods while adding specific features.

---

#### **5.4 Polymorphism**

**Purpose:** Polymorphism allows objects of different classes to be treated as objects of a common superclass. It enables a single action to behave differently based on the object.

**Definition:**
- **Method Overloading:** Multiple methods with the same name but different parameters within the same class.
- **Method Overriding:** Subclass provides a specific implementation for a method already defined in its superclass.

**Example:**

```java
// Method Overloading
class Printer {
    void print(String message) {
        System.out.println("Message: " + message);
    }

    void print(int number) {
        System.out.println("Number: " + number);
    }
}

// Method Overriding
class Animal {
    void makeSound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cat meows");
    }
}

public class PolymorphismExample {
    public static void main(String[] args) {
        Printer printer = new Printer();
        printer.print("Hello"); // Calls print(String)
        printer.print(123); // Calls print(int)

        Animal myCat = new Cat();
        myCat.makeSound(); // Calls Cat's implementation
    }
}
```

**Real-World Application:**
- **Graphics System:** Use polymorphism to handle different shapes like `Circle`, `Rectangle`, and `Triangle` through a common interface or superclass `Shape`.

---

#### **5.5 Abstraction**

**Purpose:** Abstraction is the concept of hiding the complex implementation details and showing only the essential features of an object.

**Definition:**
- **Abstract Class:** A class that cannot be instantiated and may contain abstract methods (methods without a body) that must be implemented by subclasses.
- **Interface:** A reference type in Java that can contain only constants, method signatures, default methods, static methods, and nested types. Interfaces are implemented by classes.

**Example:**

```java
// Abstract Class
abstract class Shape {
    abstract void draw(); // Abstract method

    void display() {
        System.out.println("Displaying shape");
    }
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle");
    }
}

public class AbstractionExample {
    public static void main(String[] args) {
        Shape myShape = new Circle();
        myShape.draw(); // Calls Circle's implementation
        myShape.display(); // Calls inherited method
    }
}
```

**Real-World Application:**
- **Payment System:** Define an abstract class `Payment` with methods like `processPayment()`. Subclasses such as `CreditCardPayment` and `PayPalPayment` implement these methods based on specific payment types.

---

#### **5.6 Interfaces**

**Purpose:** Interfaces provide a way to achieve abstraction and multiple inheritance. They allow classes to implement multiple interfaces and provide a contract for what a class can do.

**Definition:**
- **Interface:** A reference type in Java that contains abstract methods and constants. A class that implements an interface must provide the implementation for all of its methods.

**Example:**

```java
interface Drawable {
    void draw(); // Abstract method
}

class Circle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Rectangle implements Drawable {
    @Override
    public void draw() {
        System.out.println("Drawing a rectangle");
    }
}

public class InterfaceExample {
    public static void main(String[] args) {
        Drawable circle = new Circle();
        Drawable rectangle = new Rectangle();
        circle.draw(); // Calls Circle's implementation
        rectangle.draw(); // Calls Rectangle's implementation
    }
}
```

**Real-World Application:**
- **Design Patterns:** Use interfaces to define common operations in design patterns like Strategy or Observer, allowing for flexible and interchangeable implementations.

---

#### **5.7 Composition**

**Purpose:** Composition is a design principle where a class is composed of one or more objects of other classes. It allows for building complex types by combining objects.

**Definition:**
- **Composition:** Instead of inheritance, a class can use instances of other classes to provide its functionality.

**Example:**

```java
class Engine {
    void start() {
        System.out.println("Engine starts");
    }
}

class Car {
    private Engine engine; // Composition: Car has an Engine

    // Constructor
    public Car(Engine engine) {
        this.engine = engine;
    }

    void startCar() {
        engine.start(); // Delegates functionality to Engine
        System.out.println("Car starts");
    }
}

public class CompositionExample {
    public static void main(String[] args) {
        Engine engine = new Engine();
        Car car = new Car(engine);
        car.startCar(); // Output: Engine starts \n Car starts
    }
}
```

**Real-World Application:**
- **Computer System:** Compose a `Computer` class with `CPU`, `RAM`, and `Storage` objects to model a computer system.

---

#### **5.8 Aggregation**

**Purpose:** Aggregation is a special form of association with a whole-part relationship but with less strict ownership compared to composition.

**Definition:**
- **Aggregation:** Represents a relationship where the child can exist independently of the parent.

**Example:**

```java
class Department {
    private String name;

    // Constructor
    public Department(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

class Employee {


    private String name;
    private Department department; // Aggregation: Employee has a Department

    // Constructor
    public Employee(String name, Department department) {
        this.name = name;
        this.department = department;
    }

    public void displayInfo() {
        System.out.println("Employee: " + name);
        System.out.println("Department: " + department.getName());
    }
}

public class AggregationExample {
    public static void main(String[] args) {
        Department dept = new Department("IT");
        Employee emp = new Employee("John", dept);
        emp.displayInfo(); // Output: Employee: John \n Department: IT
    }
}
```

**Real-World Application:**
- **University System:** Aggregate `Student` and `Course` where students can be enrolled in multiple courses and courses can have multiple students.

---

These concepts form the foundation of Object-Oriented Programming and are crucial for designing robust and maintainable software systems. Understanding and implementing these concepts will help you in various real-world projects and industry applications.

Certainly! Let’s delve into detailed notes for each Object-Oriented Programming (OOP) concept with a small project example for practical understanding. We'll cover each core concept with a small project that demonstrates its application in a real-world scenario.

---

### **5. Object-Oriented Programming (OOP)**

#### **5.1 Classes and Objects**

**Concept Overview:**
- **Class:** Blueprint for creating objects. Defines attributes and methods.
- **Object:** Instance of a class with its own state and behavior.

**Detailed Example:**

**Project: Simple Banking System**

**Objective:** Create a basic banking system with `Account` and `Customer` classes to manage bank accounts.

```java
// Class: Customer
public class Customer {
    private String name;
    private int age;

    // Constructor
    public Customer(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Getter methods
    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }
}

// Class: Account
public class Account {
    private Customer customer;
    private double balance;

    // Constructor
    public Account(Customer customer, double balance) {
        this.customer = customer;
        this.balance = balance;
    }

    // Method to deposit money
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    // Method to withdraw money
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }

    // Method to display account details
    public void displayAccountInfo() {
        System.out.println("Customer: " + customer.getName() + ", Age: " + customer.getAge());
        System.out.println("Balance: $" + balance);
    }
}

// Main class to demonstrate the banking system
public class BankingSystem {
    public static void main(String[] args) {
        Customer customer = new Customer("John Doe", 30);
        Account account = new Account(customer, 1000.00);
        
        account.deposit(500.00);
        account.withdraw(200.00);
        account.displayAccountInfo(); // Output: Customer: John Doe, Age: 30 \n Balance: $1300.00
    }
}
```

**Explanation:**
- **Customer Class:** Encapsulates customer details.
- **Account Class:** Manages account balance and interactions. Uses composition to include `Customer`.

**Real-World Application:** Basic structure of a banking application with customer and account management.

---

#### **5.2 Encapsulation**

**Concept Overview:**
- **Encapsulation:** Bundling data and methods within a class. Restricts direct access to some components.

**Detailed Example:**

**Project: Library Management System**

**Objective:** Manage books in a library with encapsulated attributes and methods.

```java
// Class: Book
public class Book {
    private String title;
    private String author;
    private int publishedYear;

    // Constructor
    public Book(String title, String author, int publishedYear) {
        this.title = title;
        this.author = author;
        this.publishedYear = publishedYear;
    }

    // Getter methods
    public String getTitle() {
        return title;
    }

    public String getAuthor() {
        return author;
    }

    public int getPublishedYear() {
        return publishedYear;
    }
}

// Class: Library
import java.util.ArrayList;
import java.util.List;

public class Library {
    private List<Book> books;

    // Constructor
    public Library() {
        books = new ArrayList<>();
    }

    // Method to add a book
    public void addBook(Book book) {
        books.add(book);
    }

    // Method to display all books
    public void displayBooks() {
        for (Book book : books) {
            System.out.println("Title: " + book.getTitle() + ", Author: " + book.getAuthor() + ", Year: " + book.getPublishedYear());
        }
    }
}

// Main class to demonstrate the library system
public class LibraryManagement {
    public static void main(String[] args) {
        Library library = new Library();
        
        Book book1 = new Book("1984", "George Orwell", 1949);
        Book book2 = new Book("To Kill a Mockingbird", "Harper Lee", 1960);
        
        library.addBook(book1);
        library.addBook(book2);

        library.displayBooks(); // Output: Title: 1984, Author: George Orwell, Year: 1949 \n Title: To Kill a Mockingbird, Author: Harper Lee, Year: 1960
    }
}
```

**Explanation:**
- **Book Class:** Encapsulates book details with private fields and public getters.
- **Library Class:** Manages a collection of books and provides methods to add and display books.

**Real-World Application:** Library management system with encapsulated book and library operations.

---

#### **5.3 Inheritance**

**Concept Overview:**
- **Inheritance:** Mechanism to create a new class from an existing class. Supports code reuse and hierarchy.

**Detailed Example:**

**Project: Employee Hierarchy**

**Objective:** Model different types of employees using inheritance.

```java
// Superclass: Employee
public class Employee {
    private String name;
    private double salary;

    // Constructor
    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }

    // Method to display employee details
    public void displayInfo() {
        System.out.println("Name: " + name + ", Salary: $" + salary);
    }
}

// Subclass: Manager
public class Manager extends Employee {
    private int teamSize;

    // Constructor
    public Manager(String name, double salary, int teamSize) {
        super(name, salary); // Call superclass constructor
        this.teamSize = teamSize;
    }

    // Method to display manager details
    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Team Size: " + teamSize);
    }
}

// Main class to demonstrate employee hierarchy
public class EmployeeHierarchy {
    public static void main(String[] args) {
        Employee emp = new Employee("Jane Smith", 60000);
        Manager mgr = new Manager("John Doe", 80000, 10);
        
        emp.displayInfo(); // Output: Name: Jane Smith, Salary: $60000.0
        mgr.displayInfo(); // Output: Name: John Doe, Salary: $80000.0 \n Team Size: 10
    }
}
```

**Explanation:**
- **Employee Class:** Base class with common attributes and methods.
- **Manager Class:** Extends `Employee` and adds additional attributes and methods specific to managers.

**Real-World Application:** Human resources management system with different types of employees.

---

#### **5.4 Polymorphism**

**Concept Overview:**
- **Polymorphism:** Ability of different classes to be treated as instances of the same class through a common interface or superclass. Supports method overriding and overloading.

**Detailed Example:**

**Project: Shape Drawing Application**

**Objective:** Create a system to draw different shapes using polymorphism.

```java
// Base class: Shape
public abstract class Shape {
    abstract void draw(); // Abstract method
}

// Subclass: Circle
public class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a circle");
    }
}

// Subclass: Rectangle
public class Rectangle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing a rectangle");
    }
}

// Main class to demonstrate polymorphism
public class ShapeDrawing {
    public static void main(String[] args) {
        Shape myShape1 = new Circle(); // Base reference, derived object
        Shape myShape2 = new Rectangle();
        
        myShape1.draw(); // Output: Drawing a circle
        myShape2.draw(); // Output: Drawing a rectangle
    }
}
```

**Explanation:**
- **Shape Class:** Abstract class with an abstract `draw` method.
- **Circle and Rectangle Classes:** Provide concrete implementations for the `draw` method.

**Real-World Application:** Graphics software where different shapes are drawn using a common interface.

---

#### **5.5 Abstraction**

**Concept Overview:**
- **Abstraction:** Hiding the complex implementation details and exposing only the necessary features. Achieved using abstract classes and interfaces.

**Detailed Example:**

**Project: Payment Processing System**

**Objective:** Abstract payment processing into different payment methods.

```java
// Abstract Class: Payment
public abstract class Payment {
    abstract void processPayment(double amount); // Abstract method
}

// Subclass: CreditCardPayment
public class CreditCardPayment extends Payment {
    @Override
    void processPayment(double amount) {
        System.out.println("Processing credit card payment of $" + amount);
    }
}

// Subclass: PayPalPayment
public class PayPalPayment extends Payment {
    @Override
    void processPayment(double amount) {
        System.out.println("Processing PayPal payment of $" + amount);
    }
}

// Main class to demonstrate abstraction
public class PaymentProcessing {
    public static void main(String[] args) {
        Payment payment1 = new CreditCardPayment();
        Payment payment2 = new PayPalPayment();
        
        payment1.processPayment(100.00); // Output: Processing credit card payment of $100.0
        payment2.processPayment(200.00); // Output: Processing PayPal payment of $200.0
    }
}
```

**Explanation:**
- **Payment Class:** Abstract class defining the `processPayment` method.
- **CreditCardPayment and PayPalPayment Classes

:** Implement the `processPayment` method with specific details.

**Real-World Application:** Payment gateway systems with different payment methods.

---

#### **5.6 Interfaces**

**Concept Overview:**
- **Interface:** Defines a contract for classes to implement. Can contain abstract methods and constants.

**Detailed Example:**

**Project: Notification System**

**Objective:** Implement different notification types using interfaces.

```java
// Interface: Notifiable
public interface Notifiable {
    void sendNotification(String message); // Abstract method
}

// Class: EmailNotification
public class EmailNotification implements Notifiable {
    @Override
    public void sendNotification(String message) {
        System.out.println("Sending email: " + message);
    }
}

// Class: SMSNotification
public class SMSNotification implements Notifiable {
    @Override
    public void sendNotification(String message) {
        System.out.println("Sending SMS: " + message);
    }
}

// Main class to demonstrate interfaces
public class NotificationSystem {
    public static void main(String[] args) {
        Notifiable email = new EmailNotification();
        Notifiable sms = new SMSNotification();
        
        email.sendNotification("Your order has been shipped."); // Output: Sending email: Your order has been shipped.
        sms.sendNotification("Your order has been shipped."); // Output: Sending SMS: Your order has been shipped.
    }
}
```

**Explanation:**
- **Notifiable Interface:** Defines a contract for sending notifications.
- **EmailNotification and SMSNotification Classes:** Implement the `sendNotification` method for different notification types.

**Real-World Application:** Notification services where multiple types of notifications are sent using a common interface.

---

#### **5.7 Composition**

**Concept Overview:**
- **Composition:** Designing classes with references to other classes. Allows building complex objects from simpler ones.

**Detailed Example:**

**Project: Computer System**

**Objective:** Model a computer system with components using composition.

```java
// Class: CPU
public class CPU {
    void start() {
        System.out.println("CPU is starting...");
    }
}

// Class: RAM
public class RAM {
    void load() {
        System.out.println("RAM is loading...");
    }
}

// Class: Computer
public class Computer {
    private CPU cpu;
    private RAM ram;

    // Constructor
    public Computer(CPU cpu, RAM ram) {
        this.cpu = cpu;
        this.ram = ram;
    }

    void startComputer() {
        cpu.start();
        ram.load();
        System.out.println("Computer is starting...");
    }
}

// Main class to demonstrate composition
public class ComputerSystem {
    public static void main(String[] args) {
        CPU cpu = new CPU();
        RAM ram = new RAM();
        Computer computer = new Computer(cpu, ram);
        
        computer.startComputer(); // Output: CPU is starting... \n RAM is loading... \n Computer is starting...
    }
}
```

**Explanation:**
- **CPU and RAM Classes:** Represent components of a computer.
- **Computer Class:** Uses composition to include `CPU` and `RAM`.

**Real-World Application:** Computer system design with modular components.

---

#### **5.8 Aggregation**

**Concept Overview:**
- **Aggregation:** A form of association where the child can exist independently of the parent.

**Detailed Example:**

**Project: School System**

**Objective:** Model students and courses with aggregation to represent the relationship.

```java
// Class: Course
public class Course {
    private String courseName;

    // Constructor
    public Course(String courseName) {
        this.courseName = courseName;
    }

    public String getCourseName() {
        return courseName;
    }
}

// Class: Student
import java.util.ArrayList;
import java.util.List;

public class Student {
    private String name;
    private List<Course> courses; // Aggregation: Student can have multiple Courses

    // Constructor
    public Student(String name) {
        this.name = name;
        this.courses = new ArrayList<>();
    }

    // Method to add a course
    public void addCourse(Course course) {
        courses.add(course);
    }

    // Method to display student details
    public void displayInfo() {
        System.out.println("Student: " + name);
        System.out.println("Courses: ");
        for (Course course : courses) {
            System.out.println("- " + course.getCourseName());
        }
    }
}

// Main class to demonstrate aggregation
public class SchoolSystem {
    public static void main(String[] args) {
        Course math = new Course("Mathematics");
        Course science = new Course("Science");

        Student student = new Student("Alice");
        student.addCourse(math);
        student.addCourse(science);

        student.displayInfo(); // Output: Student: Alice \n Courses: \n - Mathematics \n - Science
    }
}
```

**Explanation:**
- **Course Class:** Represents a course that can be associated with students.
- **Student Class:** Uses aggregation to maintain a list of courses.

**Real-World Application:** Educational systems where students can be enrolled in multiple courses.

---

These detailed notes, along with the example projects, should help you grasp each OOP concept and see how they can be applied in real-world scenarios. Each project demonstrates the core concepts and their practical usage, providing a solid foundation for understanding and implementing OOP in industry projects.


Let's dive into the **Java Collection Framework**, which is a fundamental aspect of Java programming. Understanding the collection framework is crucial as it provides the architecture to store and manipulate groups of objects. We'll cover it from basic to advanced, with examples and a small project to reinforce your learning.

---

### **6. Java Collection Framework**

---

### **6.1 Introduction to Collections**

**Concept Overview:**
- The **Java Collection Framework (JCF)** is a unified architecture for representing and manipulating collections.
- **Collection:** An object that can hold references to other objects (elements).
- Collections are used to store, retrieve, manipulate, and communicate aggregate data.

**Core Interfaces:**
- **Collection Interface:** The root of the collection hierarchy.
  - **List Interface:** Ordered collection (sequence) that can contain duplicate elements. E.g., `ArrayList`, `LinkedList`.
  - **Set Interface:** A collection that cannot contain duplicate elements. E.g., `HashSet`, `LinkedHashSet`.
  - **Queue Interface:** Typically orders elements in a FIFO (first-in, first-out) manner. E.g., `PriorityQueue`.
  - **Map Interface:** An object that maps keys to values, with no duplicate keys. E.g., `HashMap`, `TreeMap`.

**Example:**
```java
import java.util.ArrayList;
import java.util.HashSet;
import java.util.HashMap;

public class CollectionIntroduction {
    public static void main(String[] args) {
        // List example
        ArrayList<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Apple"); // Duplicates allowed
        System.out.println("List: " + list); // Output: [Apple, Banana, Apple]

        // Set example
        HashSet<String> set = new HashSet<>();
        set.add("Apple");
        set.add("Banana");
        set.add("Apple"); // Duplicates not allowed
        System.out.println("Set: " + set); // Output: [Apple, Banana]

        // Map example
        HashMap<String, Integer> map = new HashMap<>();
        map.put("Apple", 1);
        map.put("Banana", 2);
        map.put("Apple", 3); // Keys are unique
        System.out.println("Map: " + map); // Output: {Apple=3, Banana=2}
    }
}
```

**Explanation:**
- **List:** Allows duplicate elements and maintains insertion order.
- **Set:** Does not allow duplicate elements.
- **Map:** Stores key-value pairs, where keys are unique.

**Real-World Use Case:**
- **List:** Managing a list of tasks where order matters.
- **Set:** Tracking unique user IDs.
- **Map:** Associating user names with their contact numbers.

---

### **6.2 List Interface**

**Concept Overview:**
- The **List interface** provides a way to store ordered collections that can contain duplicate elements.
- Commonly used implementations: `ArrayList`, `LinkedList`, `Vector`.

**ArrayList vs. LinkedList:**
- **ArrayList:**
  - Backed by a dynamic array.
  - Fast random access, slow insertion/deletion in the middle.
- **LinkedList:**
  - Backed by a doubly linked list.
  - Fast insertion/deletion, slow random access.

**Example:**
```java
import java.util.ArrayList;
import java.util.LinkedList;

public class ListExample {
    public static void main(String[] args) {
        // ArrayList example
        ArrayList<String> arrayList = new ArrayList<>();
        arrayList.add("Java");
        arrayList.add("Python");
        arrayList.add("C++");
        System.out.println("ArrayList: " + arrayList); // Output: [Java, Python, C++]

        // LinkedList example
        LinkedList<String> linkedList = new LinkedList<>();
        linkedList.add("JavaScript");
        linkedList.add("Ruby");
        linkedList.add("PHP");
        System.out.println("LinkedList: " + linkedList); // Output: [JavaScript, Ruby, PHP]
    }
}
```

**Real-World Use Case:**
- **ArrayList:** Ideal for scenarios where you need fast access to elements by index, such as in dynamic arrays.
- **LinkedList:** Useful when frequent insertions and deletions are required, such as in queue or stack implementations.

**Project: Task Manager**
```java
import java.util.ArrayList;
import java.util.Scanner;

public class TaskManager {
    public static void main(String[] args) {
        ArrayList<String> tasks = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        String task;

        while (true) {
            System.out.println("Enter a task (or 'quit' to stop): ");
            task = scanner.nextLine();
            if (task.equalsIgnoreCase("quit")) {
                break;
            }
            tasks.add(task);
        }

        System.out.println("Your tasks:");
        tasks.forEach(System.out::println);
    }
}
```

**Explanation:**
- This project demonstrates a simple task manager using an `ArrayList` to store tasks entered by the user.

---

### **6.3 Set Interface**

**Concept Overview:**
- The **Set interface** represents a collection that cannot contain duplicate elements.
- Commonly used implementations: `HashSet`, `LinkedHashSet`, `TreeSet`.

**HashSet vs. TreeSet:**
- **HashSet:**
  - Does not maintain any order of elements.
  - Allows one `null` element.
  - Best for search operations.
- **TreeSet:**
  - Maintains elements in sorted order.
  - Does not allow `null` elements.

**Example:**
```java
import java.util.HashSet;
import java.util.TreeSet;

public class SetExample {
    public static void main(String[] args) {
        // HashSet example
        HashSet<String> hashSet = new HashSet<>();
        hashSet.add("Java");
        hashSet.add("Python");
        hashSet.add("C++");
        hashSet.add("Java"); // Duplicate will not be added
        System.out.println("HashSet: " + hashSet); // Output: [Java, Python, C++]

        // TreeSet example
        TreeSet<String> treeSet = new TreeSet<>();
        treeSet.add("JavaScript");
        treeSet.add("Ruby");
        treeSet.add("PHP");
        System.out.println("TreeSet: " + treeSet); // Output: [JavaScript, PHP, Ruby]
    }
}
```

**Real-World Use Case:**
- **HashSet:** Ideal for applications where you need to maintain a unique collection of elements without caring about the order.
- **TreeSet:** Useful when you need to store elements in a sorted order.

**Project: Unique Product Names**
```java
import java.util.HashSet;
import java.util.Scanner;

public class UniqueProductNames {
    public static void main(String[] args) {
        HashSet<String> products = new HashSet<>();
        Scanner scanner = new Scanner(System.in);
        String product;

        while (true) {
            System.out.println("Enter a product name (or 'quit' to stop): ");
            product = scanner.nextLine();
            if (product.equalsIgnoreCase("quit")) {
                break;
            }
            if (!products.add(product)) {
                System.out.println("Product already exists!");
            }
        }

        System.out.println("Unique products:");
        products.forEach(System.out::println);
    }
}
```

**Explanation:**
- This project uses a `HashSet` to store unique product names, ensuring that no duplicates are added.

---

### **6.4 Map Interface**

**Concept Overview:**
- The **Map interface** represents a collection that maps keys to values, with no duplicate keys allowed.
- Commonly used implementations: `HashMap`, `LinkedHashMap`, `TreeMap`.

**HashMap vs. TreeMap:**
- **HashMap:**
  - Does not maintain any order of keys.
  - Allows one `null` key and multiple `null` values.
- **TreeMap:**
  - Maintains keys in sorted order.
  - Does not allow `null` keys.

**Example:**
```java
import java.util.HashMap;
import java.util.TreeMap;

public class MapExample {
    public static void main(String[] args) {
        // HashMap example
        HashMap<String, Integer> hashMap = new HashMap<>();
        hashMap.put("Java", 1);
        hashMap.put("Python", 2);
        hashMap.put("C++", 3);
        System.out.println("HashMap: " + hashMap); // Output: {Java=1, Python=2, C++=3}

        // TreeMap example
        TreeMap<String, Integer> treeMap = new TreeMap<>();
        treeMap.put("JavaScript", 4);
        treeMap.put("Ruby", 5);
        treeMap.put("PHP", 6);
        System.out.println("TreeMap: " + treeMap); // Output: {JavaScript=4, PHP=6, Ruby=5}
    }
}
```

**Real-World Use Case:**
- **HashMap:** Frequently used for caching data where the order of keys is not important.
- **TreeMap:** Useful in applications where you need to maintain sorted order of keys, such as a directory.

**Project: Student Grades Management**
```java
import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

public class StudentGrades {
    public static void main(String[] args) {
        Map<String, Integer> grades = new HashMap<>();
        Scanner scanner = new Scanner(System.in);
        String student;
        int grade;

       

 while (true) {
            System.out.println("Enter student's name (or 'quit' to stop): ");
            student = scanner.nextLine();
            if (student.equalsIgnoreCase("quit")) {
                break;
            }
            System.out.println("Enter grade for " + student + ": ");
            grade = scanner.nextInt();
            scanner.nextLine(); // Consume the newline character
            grades.put(student, grade);
        }

        System.out.println("Student Grades:");
        grades.forEach((name, grd) -> System.out.println(name + ": " + grd));
    }
}
```

**Explanation:**
- This project uses a `HashMap` to store student names and their corresponding grades, demonstrating how to use key-value pairs effectively.

---

### **6.5 Advanced Collections**

**Concept Overview:**
- **Synchronized Collections:** Ensures thread-safe operations on collections. E.g., `Collections.synchronizedList()`.
- **Immutable Collections:** Collections that cannot be modified after creation. E.g., `Collections.unmodifiableList()`.
- **Custom Implementations:** Creating custom collection implementations by extending abstract classes like `AbstractList`, `AbstractSet`.

**Example: Synchronized List**
```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class SynchronizedListExample {
    public static void main(String[] args) {
        List<String> list = Collections.synchronizedList(new ArrayList<>());
        list.add("Thread 1");
        list.add("Thread 2");
        System.out.println("Synchronized List: " + list);
    }
}
```

**Example: Immutable List**
```java
import java.util.Collections;
import java.util.List;

public class ImmutableListExample {
    public static void main(String[] args) {
        List<String> list = List.of("Apple", "Banana", "Cherry");
        List<String> immutableList = Collections.unmodifiableList(list);
        System.out.println("Immutable List: " + immutableList);
    }
}
```

**Real-World Use Case:**
- **Synchronized Collections:** Useful in multi-threaded applications where you need to ensure thread safety.
- **Immutable Collections:** Ideal for scenarios where you want to prevent modification of the collection, such as in configuration settings.

---


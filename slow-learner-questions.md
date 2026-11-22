# Slow Learner Questions

## Programming Questions

### 1. Create a `Student` class with a name and age, then display them.

```java
public class Main {
    public static void main(String[] args) {
        Student student = new Student();
        student.displayDetails();
    }
}

class Student {
    String name = "Manu";
    int age = 20;

    void displayDetails() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}


```
**Output:**
```text
Name: Manu
Age: 20
```


### 2. Create a `Fruit` class with a name and color, then display them.

```java
public class Main {
    public static void main(String[] args) {
        Fruit fruit = new Fruit();
        fruit.displayDetails();
    }
}

class Fruit {
    String name = "Mango";
    String color = "Yellow";

    void displayDetails() {
        System.out.println("Fruit: " + name);
        System.out.println("Color: " + color);
    }
}
```

**Output:**
```text
Fruit: Mango
Color: Yellow
```


### 3. Create a `Book` class with a constructor that sets its title, then display the title.

```java
public class Main {
    public static void main(String[] args) {
        Book book = new Book("The Jungle Book");
        book.displayTitle();
    }
}

class Book {
    String title;

    Book(String bookTitle) {
        title = bookTitle;
    }

    void displayTitle() {
        System.out.println("Title: " + title);
    }
}
```

**Output:**
```text
Title: The Jungle Book
```

### 4. Create an `Animal` class with an `eat()` method. Create a `Dog` class that inherits from `Animal` and has a `bark()` method. Display both messages.

```java
public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.eat();
        dog.bark();
    }
}

class Animal {
    void eat() {
        System.out.println("The animal eats food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}
```

**Output:**
```text
The animal eats food.
The dog barks.
```

### 5. Create a `Calculator` class with two overloaded `add()` methods: one adds two numbers and the other adds three numbers. Display both sums.

```java
public class Main {
    public static void main(String[] args) {
        Calculator calculator = new Calculator();

        System.out.println("Sum of two numbers: " + calculator.add(5, 3));
        System.out.println("Sum of three numbers: " + calculator.add(5, 3, 2));
    }
}

class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

**Output:**
```text
Sum of two numbers: 8
Sum of three numbers: 10
```


# Slow Learner Non-Programming Questions

### 1. What is object-oriented programming (OOP)?

**Answer:** OOP is a way of writing programs by organizing them around classes and objects.

### 2. What is the difference between a class and an object?

**Answer:** A class is a blueprint that describes data and actions. An object is an instance created from that class.

### 3. What is a constructor in Java?

**Answer:** A constructor is a special part of a class that runs when an object is created. It is used to give the object its starting values.

### 4. What is inheritance?

**Answer:** Inheritance lets one class receive fields and methods from another class. The class that receives them is called the child class.

### 5. What is method overloading?

**Answer:** Method overloading means having multiple methods with the same name in one class, but with different parameter lists.

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

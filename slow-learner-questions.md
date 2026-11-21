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


### 3. Create a `Rectangle` class with length and width, then display its area.

```java
public class Main {
    public static void main(String[] args) {
        Rectangle rectangle = new Rectangle();
        rectangle.displayArea();
    }
}

class Rectangle {
    int length = 5;
    int width = 3;

    void displayArea() {
        int area = length * width;
        System.out.println("Area: " + area);
    }
}
```

**Output:**
```text
Area: 15
```

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


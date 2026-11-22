# Advanced Learner Programming Questions

### 1. Create an abstract `Employee` class with an abstract salary calculation method. Create full-time and part-time employee subclasses that override the method. Use an `Employee` array to display each employee’s salary.

```java
public class Main {
    public static void main(String[] args) {
        Employee[] employees = {
            new FullTimeEmployee("Asha", 50000),
            new PartTimeEmployee("Ravi", 40, 150)
        };

        for (Employee employee : employees) {
            System.out.println(
                employee.getName() + " salary: " + employee.calculateSalary()
            );
        }
    }
}

abstract class Employee {
    private String name;

    Employee(String name) {
        this.name = name;
    }

    String getName() {
        return name;
    }

    abstract double calculateSalary();
}

class FullTimeEmployee extends Employee {
    private double monthlySalary;

    FullTimeEmployee(String name, double monthlySalary) {
        super(name);
        this.monthlySalary = monthlySalary;
    }

    @Override
    double calculateSalary() {
        return monthlySalary;
    }
}

class PartTimeEmployee extends Employee {
    private int hoursWorked;
    private double hourlyRate;

    PartTimeEmployee(String name, int hoursWorked, double hourlyRate) {
        super(name);
        this.hoursWorked = hoursWorked;
        this.hourlyRate = hourlyRate;
    }

    @Override
    double calculateSalary() {
        return hoursWorked * hourlyRate;
    }
}
```

**Output:**
```text
Asha salary: 50000.0
Ravi salary: 6000.0
```

### 2. Create a `PaymentMethod` interface with card and UPI payment classes. Use the interface to process both payments.

```java
public class Main {
    public static void main(String[] args) {
        PaymentMethod[] methods = {
            new CardPayment(),
            new UpiPayment()
        };

        for (PaymentMethod method : methods) {
            method.pay(1500);
        }
    }
}

interface PaymentMethod {
    void pay(double amount);
}

class CardPayment implements PaymentMethod {
    @Override
    public void pay(double amount) {
        System.out.println("Card payment processed: Rs. " + amount);
    }
}

class UpiPayment implements PaymentMethod {
    @Override
    public void pay(double amount) {
        System.out.println("UPI payment processed: Rs. " + amount);
    }
}
```

**Output:**
```text
Card payment processed: Rs. 1500.0
UPI payment processed: Rs. 1500.0
```

### 3. Create a user-defined exception called `InvalidMarksException`. Use it to reject student marks outside the range 0–100, then display the grade for valid marks.

```java
public class Main {
    public static void main(String[] args) {
        try {
            Student firstStudent = new Student("Nila", 85);
            System.out.println(
                firstStudent.getName() + " grade: " + firstStudent.getGrade()
            );

            Student secondStudent = new Student("Arun", 105);
            System.out.println(
                secondStudent.getName() + " grade: " + secondStudent.getGrade()
            );
        } catch (InvalidMarksException error) {
            System.out.println("Error: " + error.getMessage());
        }
    }
}

class Student {
    private String name;
    private int marks;

    Student(String name, int marks) throws InvalidMarksException {
        if (marks < 0 || marks > 100) {
            throw new InvalidMarksException("Marks must be between 0 and 100.");
        }

        this.name = name;
        this.marks = marks;
    }

    String getName() {
        return name;
    }

    String getGrade() {
        if (marks >= 90) return "A";
        if (marks >= 75) return "B";
        if (marks >= 60) return "C";
        return "D";
    }
}

class InvalidMarksException extends Exception {
    InvalidMarksException(String message) {
        super(message);
    }
}
```

**Output:**
```text
Nila grade: B
Error: Marks must be between 0 and 100.
```

### 4. Store students and their subject marks using `ArrayList` and `HashMap`. Use an `Iterator` to remove students whose average is below 40.

```java
import java.util.ArrayList;
import java.util.HashMap;
import java.util.Iterator;

public class Main {
    public static void main(String[] args) {
        ArrayList<Student> students = new ArrayList<>();

        Student asha = new Student("Asha");
        asha.addMark("Java", 88);
        asha.addMark("Maths", 82);

        Student ravi = new Student("Ravi");
        ravi.addMark("Java", 35);
        ravi.addMark("Maths", 45);

        Student maya = new Student("Maya");
        maya.addMark("Java", 30);
        maya.addMark("Maths", 35);

        students.add(asha);
        students.add(ravi);
        students.add(maya);

        Iterator<Student> iterator = students.iterator();

        while (iterator.hasNext()) {
            Student student = iterator.next();

            if (student.getAverage() < 40) {
                iterator.remove();
            }
        }

        System.out.println("Students with an average of 40 or higher:");

        for (Student student : students) {
            System.out.println(
                student.getName() + " - " + student.getAverage()
            );
        }
    }
}

class Student {
    private String name;
    private HashMap<String, Integer> marks = new HashMap<>();

    Student(String name) {
        this.name = name;
    }

    void addMark(String subject, int mark) {
        marks.put(subject, mark);
    }

    String getName() {
        return name;
    }

    double getAverage() {
        int total = 0;

        for (int mark : marks.values()) {
            total += mark;
        }

        return (double) total / marks.size();
    }
}
```

**Output:**
```text
Students with an average of 40 or higher:
Asha - 85.0
Ravi - 40.0
```

### 5. Create two threads that safely increase a shared counter. Use a synchronized method so the final count is correct.

```java
public class Main {
    public static void main(String[] args) throws InterruptedException {
        Counter counter = new Counter();

        CounterThread firstThread = new CounterThread(counter);
        CounterThread secondThread = new CounterThread(counter);

        firstThread.start();
        secondThread.start();

        firstThread.join();
        secondThread.join();

        System.out.println("Final count: " + counter.getCount());
    }
}

class Counter {
    private int count = 0;

    synchronized void increment() {
        count++;
    }

    int getCount() {
        return count;
    }
}

class CounterThread extends Thread {
    private Counter counter;

    CounterThread(Counter counter) {
        this.counter = counter;
    }

    @Override
    public void run() {
        for (int i = 0; i < 1000; i++) {
            counter.increment();
        }
    }
}
```

**Output:**
```text
Final count: 2000
```

# Advanced Learner Non-Programming Questions

### 1. How is an abstract class different from an interface in Java? When would you use each?

**Answer:** An abstract class can have constructors, instance variables, and both abstract and regular methods. An interface mainly defines behavior that implementing classes agree to provide. Use an abstract class when related classes share state or code; use an interface when different classes need to follow the same behavior contract.

### 2. Explain the difference between method overloading and method overriding. How are they related to polymorphism?

**Answer:** Overloading uses the same method name with different parameter lists, usually in the same class. It is compile-time polymorphism. Overriding happens when a subclass provides its own version of an inherited method with the same signature. It enables runtime polymorphism because Java chooses the method based on the actual object.

### 3. What is the difference between checked and unchecked exceptions? Why might a programmer create a custom exception?

**Answer:** A checked exception must be caught or declared in the method signature. An unchecked exception does not have that compile-time requirement. A custom exception lets a program report a specific error related to its own rules, such as invalid student marks.

### 4. How are `ArrayList` and `HashMap` different? Why might an `Iterator` be used when removing items from a collection?

**Answer:** An `ArrayList` stores an ordered sequence of items and allows access by index. A `HashMap` stores key-value pairs and looks up values by key. An `Iterator` visits collection items one at a time; using `iterator.remove()` is a safe way to remove the current item during iteration.

### 5. What is a race condition in a multithreaded program, and how can `synchronized` help prevent it?

**Answer:** A race condition happens when multiple threads access and change shared data at the same time, causing unpredictable results. A `synchronized` method or block lets only one thread at a time access that protected code, helping keep shared data consistent.

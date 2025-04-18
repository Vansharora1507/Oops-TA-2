# Oops-TA-2

```java
// Q1: Animal with overridden method in subclass
class Animal {
    void makeSound() {
        System.out.println("Animal sound");
    }
}

class Cat extends Animal {
    void makeSound() {
        System.out.println("Cat is barking");
    }

    public static void main(String[] args) {
        Cat c = new Cat();
        c.makeSound();
    }
}

// Q2: Vehicle class with overridden drive method
class Vehicle {
    void drive() {
        System.out.println("Vehicle is moving");
    }
}

class Car extends Vehicle {
    void drive() {
        System.out.println("Repairing a car");
    }

    public static void main(String[] args) {
        Car car = new Car();
        car.drive();
    }
}

// Q3: Shape and Rectangle with getArea
class Shape {
    double getArea() {
        return 0;
    }
}

class Rectangle extends Shape {
    double length = 5;
    double width = 3;

    double getArea() {
        return length * width;
    }

    public static void main(String[] args) {
        Rectangle r = new Rectangle();
        System.out.println("Area: " + r.getArea());
    }
}

// Q4: Employee and HRManager with additional method
class Employee {
    void work() {
        System.out.println("Employee is working");
    }

    void getSalary() {
        System.out.println("Getting salary");
    }
}

class HRManager extends Employee {
    void work() {
        System.out.println("HR Manager is working");
    }

    void addEmployee() {
        System.out.println("Adding new employee");
    }

    public static void main(String[] args) {
        HRManager h = new HRManager();
        h.work();
        h.getSalary();
        h.addEmployee();
    }
}

// Q5: BankAccount with withdrawal restriction
class BankAccount {
    int balance = 150;

    void deposit(int amount) {
        balance += amount;
    }

    void withdraw(int amount) {
        balance -= amount;
    }
}

class SavingsAccount extends BankAccount {
    void withdraw(int amount) {
        if (balance - amount >= 100) {
            balance -= amount;
            System.out.println("Withdrawn: " + amount);
        } else {
            System.out.println("Withdrawal denied. Balance too low.");
        }
    }

    public static void main(String[] args) {
        SavingsAccount s = new SavingsAccount();
        s.deposit(200);
        s.withdraw(50);
        s.withdraw(300);
    }
}

// Q6: Animal and Cheetah
class AnimalMove {
    void move() {
        System.out.println("Animal moves");
    }
}

class Cheetah extends AnimalMove {
    void move() {
        System.out.println("Cheetah runs");
    }

    public static void main(String[] args) {
        Cheetah c = new Cheetah();
        c.move();
    }
}

// Q7: Person and Employee with job title
class Person {
    String getFirstName() {
        return "John";
    }

    String getLastName() {
        return "Doe";
    }
}

class EmployeeInfo extends Person {
    String getEmployeeId() {
        return "EMP001";
    }

    String getLastName() {
        return "Doe - Software Engineer";
    }

    public static void main(String[] args) {
        EmployeeInfo e = new EmployeeInfo();
        System.out.println(e.getFirstName());
        System.out.println(e.getLastName());
        System.out.println(e.getEmployeeId());
    }
}

// Q8: Shape with getArea and getPerimeter
class CircleShape {
    double radius = 5;

    double getArea() {
        return 3.14 * radius * radius;
    }

    double getPerimeter() {
        return 2 * 3.14 * radius;
    }

    public static void main(String[] args) {
        CircleShape c = new CircleShape();
        System.out.println("Area: " + c.getArea());
        System.out.println("Perimeter: " + c.getPerimeter());
    }
}

// Q9: Vehicle hierarchy
class VehicleBase {
    String make, model, fuelType;
    int year;

    void fuelEfficiency() {
        System.out.println("Calculating fuel efficiency...");
    }

    void distanceTraveled() {
        System.out.println("Distance traveled...");
    }

    void maxSpeed() {
        System.out.println("Max speed...");
    }
}

class Truck extends VehicleBase { }
class CarModel extends VehicleBase { }
class Motorcycle extends VehicleBase {
    public static void main(String[] args) {
        Motorcycle m = new Motorcycle();
        m.fuelEfficiency();
        m.distanceTraveled();
        m.maxSpeed();
    }
}

// Q10: Employee hierarchy with roles
class Emp {
    String name, address, jobTitle;
    int salary;

    void bonus() {
        System.out.println("Bonus calculated");
    }

    void report() {
        System.out.println("Performance report generated");
    }

    void manage() {
        System.out.println("Project managed");
    }
}

class Manager extends Emp { }
class Developer extends Emp { }
class Programmer extends Emp {
    public static void main(String[] args) {
        Programmer p = new Programmer();
        p.name = "Alice";
        p.salary = 50000;
        p.jobTitle = "Programmer";
        p.bonus();
        p.report();
        p.manage();
    }
}
```

---



```java
// Q1: Single thread single task
class Q1 {
    void task() {
        System.out.println("Task 1 is running...");
    }

    public static void main(String[] args) {
        Q1 obj = new Q1();
        obj.task();
    }
}

// Q2: Single thread multi task
class Q2 {
    void task1() {
        System.out.println("Task 1 is running...");
    }

    void task2() {
        System.out.println("Task 2 is running...");
    }

    public static void main(String[] args) {
        Q2 obj = new Q2();
        obj.task1();
        obj.task2();
    }
}

// Q3: Multithread single task
class SingleTask extends Thread {
    public void run() {
        System.out.println("Running task in thread: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        SingleTask t1 = new SingleTask();
        SingleTask t2 = new SingleTask();
        t1.start();
        t2.start();
    }
}

// Q4: Multithread multi task
class Task1 extends Thread {
    public void run() {
        System.out.println("Task 1 running in: " + Thread.currentThread().getName());
    }
}

class Task2 extends Thread {
    public void run() {
        System.out.println("Task 2 running in: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        Task1 t1 = new Task1();
        Task2 t2 = new Task2();
        t1.start();
        t2.start();
    }
}

// Q5: Create a file
import java.io.*;

class Q5 {
    public static void main(String[] args) {
        try {
            File f = new File("file1.txt");
            if (f.createNewFile()) {
                System.out.println("File created: " + f.getName());
            } else {
                System.out.println("File already exists.");
            }
        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}

// Q6: Read from a file
import java.io.*;

class Q6 {
    public static void main(String[] args) {
        try {
            FileReader fr = new FileReader("file1.txt");
            int ch;
            while ((ch = fr.read()) != -1) {
                System.out.print((char) ch);
            }
            fr.close();
        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}

// Q7: Write to a file
import java.io.*;

class Q7 {
    public static void main(String[] args) {
        try {
            FileWriter fw = new FileWriter("file1.txt");
            fw.write("This is some written content.");
            fw.close();
            System.out.println("Successfully wrote to the file.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}

// Q8: Copy file content
import java.io.*;

class Q8 {
    public static void main(String[] args) {
        try {
            FileReader fr = new FileReader("file1.txt");
            FileWriter fw = new FileWriter("file2.txt");
            int ch;
            while ((ch = fr.read()) != -1) {
                fw.write(ch);
            }
            fr.close();
            fw.close();
            System.out.println("Data copied successfully.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}

// Q9: Arithmetic exception
class Q9 {
    public static void main(String[] args) {
        try {
            int a = 10, b = 0;
            int result = a / b;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero.");
        }
    }
}

// Q10: Multiple inheritance using interface
interface A {
    void methodA();
}

interface B {
    void methodB();
}

class Q10 implements A, B {
    public void methodA() {
        System.out.println("Method from interface A");
    }

    public void methodB() {
        System.out.println("Method from interface B");
    }

    public static void main(String[] args) {
        Q10 obj = new Q10();
        obj.methodA();
        obj.methodB();
    }
}
```
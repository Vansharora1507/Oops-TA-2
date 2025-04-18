# Oops-TA-2 
# OOPS Assignment - TA-2

```java
// Question 1: Single thread single task
class Q1 {
    void execute() {
        System.out.println("Task 1 is running...");
    }

    public static void main(String[] args) {
        Q1 t = new Q1();
        t.execute();
    }
}

// Question 2: Single thread multi task
class Q2 {
    void task1() {
        System.out.println("Task 1 is running...");
    }

    void task2() {
        System.out.println("Task 2 is running...");
    }

    public static void main(String[] args) {
        Q2 t = new Q2();
        t.task1();
        t.task2();
    }
}

// Question 3: Multithread single task
class MySingleTask extends Thread {
    public void run() {
        System.out.println("Running single task from: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        MySingleTask t1 = new MySingleTask();
        MySingleTask t2 = new MySingleTask();
        t1.start();
        t2.start();
    }
}

// Question 4: Multithread multi task
class MultiTask1 extends Thread {
    public void run() {
        System.out.println("Task 1 running in: " + Thread.currentThread().getName());
    }
}

class MultiTask2 extends Thread {
    public void run() {
        System.out.println("Task 2 running in: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        MultiTask1 t1 = new MultiTask1();
        MultiTask2 t2 = new MultiTask2();
        t1.start();
        t2.start();
    }
}

// Question 5: Write a Java program to create a file
import java.io.File;
import java.io.IOException;

class Q5 {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt");
            if (file.createNewFile()) {
                System.out.println("File created: " + file.getName());
            } else {
                System.out.println("File already exists.");
            }
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}

// Question 6: To read from a file
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

class Q6 {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt");
            Scanner reader = new Scanner(file);
            while (reader.hasNextLine()) {
                String data = reader.nextLine();
                System.out.println(data);
            }
            reader.close();
        } catch (FileNotFoundException e) {
            System.out.println("File not found.");
            e.printStackTrace();
        }
    }
}

// Question 7: Write to a file
import java.io.FileWriter;
import java.io.IOException;

class Q7 {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("example.txt");
            writer.write("This is a sample content.");
            writer.close();
            System.out.println("Successfully wrote to the file.");
        } catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}

// Question 8: Copying data from one file to another
import java.io.*;

class Q8 {
    public static void main(String[] args) {
        try {
            FileReader fr = new FileReader("source.txt");
            FileWriter fw = new FileWriter("destination.txt");
            int ch;
            while ((ch = fr.read()) != -1) {
                fw.write(ch);
            }
            fr.close();
            fw.close();
            System.out.println("File copied successfully.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

// Question 9: ArithmeticException example
class Q9 {
    public static void main(String[] args) {
        try {
            int a = 10, b = 0;
            int c = a / b;
            System.out.println(c);
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero.");
        }
    }
}

// Question 10: Multiple inheritance using interface
interface A {
    void showA();
}

interface B {
    void showB();
}

class Q10 implements A, B {
    public void showA() {
        System.out.println("Interface A method");
    }

    public void showB() {
        System.out.println("Interface B method");
    }

    public static void main(String[] args) {
        Q10 obj = new Q10();
        obj.showA();
        obj.showB();
    }
}
```
# Oops-TA-2 
# OOPS Assignment - TA-2

```java
// Question 1: Single thread single task
class Q1 {
    void task() {
        System.out.println("Task 1 is running...");
    }

    public static void main(String[] args) {
        Q1 obj = new Q1();
        obj.task();
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
        Q2 obj = new Q2();
        obj.task1();
        obj.task2();
    }
}

// Question 3: Multithread single task
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

// Question 4: Multithread multi task
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

// Question 5: Write a Java program to create a file
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

// Question 6: To read from a file
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

// Question 7: Write to a file
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

// Question 8: Copying data from one file to another
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

// Question 9: ArithmeticException example
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

// Question 10: Multiple inheritance using interface
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
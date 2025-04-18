# Oops-TA-2 
//single thread single task
class Task1 {
    void execute() {
        System.out.println("Task 1 is running...");
    }

    public static void main(String[] args) {
        Task1 t = new Task1();
        t.execute();
    }
}
//single thread multi task
class Tasks {
    void task1() {
        System.out.println("Task 1 is running...");
    }

    void task2() {
        System.out.println("Task 2 is running...");
    }

    public static void main(String[] args) {
        Tasks t = new Tasks();
        t.task1();
        t.task2();
    }
}
//multiple thread single task
class MyTask extends Thread {
    public void run() {
        System.out.println("Running single task from: " + Thread.currentThread().getName());
    }

    public static void main(String[] args) {
        MyTask t1 = new MyTask();
        MyTask t2 = new MyTask();
        t1.start();
        t2.start();
    }
}
//multiple tgreads multiple task

class Task1 extends Thread {
    public void run() {
        System.out.println("Task 1 running...");
    }
}

class Task2 extends Thread {
    public void run() {
        System.out.println("Task 2 running...");
    }
}

public class MultiThreadMultiTask {
    public static void main(String[] args) {
        Task1 t1 = new Task1();
        Task2 t2 = new Task2();
        t1.start();
        t2.start();
    }
}
//creating a file
import java.io.*;

public class FileCreation {
    public static void main(String[] args) {
        try {
            File f1 = new File("TestFile1.txt");
            f1.createNewFile();
            System.out.println("File created: " + f1.getName());

            File f2 = new File("TestFile2.txt");
            f2.createNewFile();
            System.out.println("File created: " + f2.getName());

        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}
//writing a file
import java.io.*;

public class FileWriting {
    public static void main(String[] args) {
        try {
            FileWriter w1 = new FileWriter("TestFile1.txt");
            w1.write("Writing something in this file....");
            System.out.println("Done writing in the file.");
            w1.close();

        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}
//reading from a file
import java.io.*;

public class FileWriting {
    public static void main(String[] args) {
        try {
            FileWriter w1 = new FileWriter("TestFile1.txt");
            w1.write("Writing something in this file....");
            System.out.println("Done writing in the file.");
            w1.close();

        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}
//copying data from one file to another
import java.io.*;

public class FileCopy {
    public static void main(String[] args) {
        try {
            FileReader r1 = new FileReader("TestFile1.txt");
            FileWriter w2 = new FileWriter("TestFile2.txt");

            int i;
            while ((i = r1.read()) != -1) {
                w2.write(i);
            }

            System.out.println("File copied successfully.");
            r1.close();
            w2.close();

        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}
//arithmetic exception
public class ArithmeticExceptionExample {
    public static void main(String[] args) {
        try {
            int a = 10;
            int b = 0;
            int result = a / b; // This will throw ArithmeticException
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero!");
        }
        
        System.out.println("Program continues...");
    }
}
//multiple inheritance using interface
interface A {
    void methodA();
}

interface B {
    void methodB();
}

class C implements A, B {
    public void methodA() {
        System.out.println("Method A");
    }
    public void methodB() {
        System.out.println("Method B");
    }
}




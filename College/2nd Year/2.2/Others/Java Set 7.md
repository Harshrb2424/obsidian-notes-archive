## 7.1. Write a Java program to handle checked and unchecked exceptions. Also, demonstrate the usage of custom exceptions in real-time scenarios.

### Source Code: `ex3.java` [view file](./exp3.java)
```java
import java.io.File;
import java.io.FileReader;
import java.io.FileNotFoundException;

class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message);
    }
}
class Experiment3 {
    public static void register(String name, int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("User must be at least 18 years old.");
        } else {
            System.out.println("Registration successful for user: " + name);
        }
    }

    public static void main(String[] args) {
        try {
            File file = new File("myfile.txt");
            FileReader fr = new FileReader(file); 
        } catch (FileNotFoundException e) {
            System.out.println("File not found: " + e.getMessage());
        }

        try {   
            int[] arr = {1, 2, 3};
            System.out.println(arr[6]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index out of bounds: " + e.getMessage());
        }
        finally {
            System.out.println("Cleanup operations can be performed here.");
        }

        System.out.println("Demonstrating Custom Exception:");
        try {
            register("Harsh RB", 18);
            register("Purushottam", 16);
        } catch (InvalidAgeException e) {
            System.out.println("Custom Exception Caught: " + e.getMessage());
        }
    }
}
```
### Output:

```bash
PS D:/JAVA> javac .\exp3.java
PS D:/JAVA> java Experiment3
File not found: myfile.txt (The system cannot find the file specified)
Array index out of bounds: Index 6 out of bounds for length 3
Cleanup operations can be performed here.
Demonstrating Custom Exception:
Registration successful for user: Harsh RB
Custom Exception Caught: User must be at least 18 years old.
```
## 7.2. Write a Java program on Random Access File class to perform different read and write operations.

### Source Code: `ex4.java` [view file](./exp4.java)

```java
import java.io.*;
class Experiment4 {
    public static void main(String[] args) {
    try {
        RandomAccessFile file = new RandomAccessFile("data.txt", "rw");
        String data1 = "Hello";
        String data2 = "World";
        file.writeUTF(data1);
        file.writeUTF(data2);

        file.seek(0);
        String readData1 = file.readUTF();
        String readData2 = file.readUTF();
        System.out.println("Data read from file:");
        System.out.println(readData1);
        System.out.println(readData2);

        file.seek(file.length());
        String newData = "Java!";
        file.writeUTF(newData);

        file.seek(0);
        readData1 = file.readUTF();
        readData2 = file.readUTF();

        String readData3 = file.readUTF();
        System.out.println("Data read from file after appending:");
        System.out.println(readData1);
        System.out.println(readData2);
        System.out.println(readData3);
        file.close();
    } catch (IOException e) {
        System.out.println("An error occurred: " + e.getMessage());
        e.printStackTrace();
    }
    }
}
```

### Output:

```bash
PS D:\java> javac .\exp4.java
PS D:\java> java Experiment4 
Data read from file:
Hello
World
Data read from file after appending:
Hello
World
Java!
```


## 3.1. Write a Java program to demonstrate the working of different collection classes. [Use package structure to store multiple classes].

### Source Code: [view folder](./exp5)

`CollectionsDemo.java` 
```java
package collections;
public class CollectionsDemo {
    public static void main(String[] args) {
        ListExample.main(args);
        SetExample.main(args);
        MapExample.main(args);
    }
}
```
`ListExample.java`
```java
package collections;
import java.util.ArrayList;
public class ListExample {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Plums");
        list.add("Pineapple");
        list.add("Watermelon");
        System.out.println("List Example:");
        for (String fruit : list) {
            System.out.println(fruit);
        }
    }
}

```

`MapExample.java`
```java
package collections;
import java.util.HashMap;
public class MapExample {
    public static void main(String[] args) {
        HashMap<Integer, String> map = new HashMap<>();
        map.put(1, "Grape");
        map.put(2, "Strawberry");
        map.put(3, "Orange");
        System.out.println("Map Example:");
        for (HashMap.Entry<Integer, String> entry : map.entrySet()) {
        System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

`SetExample.java`
```java
package collections;
import java.util.HashSet;
public class SetExample {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        set.add("Apple");
        set.add("Banana");
        set.add("Orange");
        set.add("Mango");
        System.out.println("Set Example:");
        for (String fruit : set) {
            System.out.println(fruit);
        }
    }
}
```

### Output:
```bash
D:\java\exp5> javac -d . ListExample.java
D:\java\exp5> javac -d . SetExample.java     
D:\java\exp5> javac -d . MapExample.java
D:\java\exp5> javac -d . CollectionsDemo.java
D:\java\exp5> java collections.CollectionsDemo  
List Example:
Plums
Pineapple
Watermelon
Set Example:
Apple
Mango
Orange
Banana
Map Example:
1: Grape
2: Strawberry
3: Orange
```

## 3.2. Write a program to synchronize the threads acting on the same object. [Consider the example of any reservations like railway, bus, movie ticket booking, etc.]

### Source Code: `exp6.java` [view file](./exp6.java)
```java
class TicketBookingSystem {
    private int availableTickets = 10; // Total tickets available

    // Method to book tickets, synchronized to handle concurrency
    public synchronized void bookTickets(String passengerName, int ticketsToBook) {
        if (ticketsToBook > availableTickets) {
            System.out.println("Sorry, " + passengerName + ". Not enough tickets available.");
            return;
        }

        // Simulating some delay to mimic real-world booking process
        try {
            Thread.sleep(100); // Introducing a small delay
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        // Booking tickets
        System.out.println(ticketsToBook + " ticket(s) booked for " + passengerName);
        availableTickets -= ticketsToBook;
        System.out.println("Remaining tickets: " + availableTickets);
    }
}

class TicketBookingExample {
    public static void main(String[] args) {
        TicketBookingSystem ticketSystem = new TicketBookingSystem();

        // Creating multiple threads to book tickets
        Thread thread1 = new Thread(() -> ticketSystem.bookTickets("Alice", 3));
        Thread thread2 = new Thread(() -> ticketSystem.bookTickets("Bob", 5));
        Thread thread3 = new Thread(() -> ticketSystem.bookTickets("Harsh", 4));
        Thread thread4 = new Thread(() -> ticketSystem.bookTickets("Carol", 2));

        // Start all threads
        thread1.start();
        thread2.start();
        thread3.start();
        thread4.start();

        // Wait for all threads to complete
        try {
            thread1.join();
            thread2.join();
            thread3.join();
            thread4.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}
```
### Output:
```bash
D:\Github\program-examples\resources\JAVA> java TicketBookingExample                                                                           
D:\Github\program-examples\resources\JAVA> javac exp6.java                                               
5 ticket(s) booked for Bob
Remaining tickets: 5
2 ticket(s) booked for Carol
Remaining tickets: 3
Sorry, Harsh. Not enough tickets available.
3 ticket(s) booked for Alice
Remaining tickets: 0
```


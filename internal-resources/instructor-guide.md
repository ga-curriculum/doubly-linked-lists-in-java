<h1>
  <span class="headline">Doubly Linked Lists in Java</span>
  <span class="subhead">Instructor Guide</span>
</h1>

## Solution for independent practice task 1
### Implementing a queue data structure using `LinkedList` class
```java
import java.util.LinkedList;

public class QueueExample {
    public static void main(String[] args) {
        LinkedList<String> queue = new LinkedList<>();

        queue.addLast("John");
        queue.addLast("Jane");
        queue.addLast("Mark");

        System.out.println("Queue: " + queue);

        System.out.println("Serving: " + queue.removeFirst());
        System.out.println("Updated Queue: " + queue);
    }
}
```

## Solution for independent practice task 2
### Implementing a stack data structure using `LinkedList` class
```java
import java.util.LinkedList;

public class StackExample {
    public static void main(String[] args) {
        LinkedList<String> stack = new LinkedList<>();

        stack.addFirst("Book 1");
        stack.addFirst("Book 2");
        stack.addFirst("Book 3");

        System.out.println("Stack: " + stack);

        System.out.println("Popping: " + stack.removeFirst());
        System.out.println("Updated Stack: " + stack);
    }
}
```
<h1>
  <span class="headline">Doubly Linked Lists in Java</span>
  <span class="subhead">Java's Official Implementation of Linked List</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able incorporate Java's `LinkedList` class as a doubly linked list in your programs.

## The `LinkedList` class
Java's `LinkedList` class offers a flexible, doubly linked list implementation for dynamic data storage. Instead of primitive variables, `LinkedList` has objects as data in its nodes.

The constructor syntax for creating a new `LinkedList` object is:
```java
LinkedList<Type> list = new LinkedList<>();
```

## Commonly used methods of `LinkedList` class
This list in a non-exhaustive list of methods of the `LinkedList` class.

|Method & Syntax|Description|Example|
|:---|:---|:---|
|`addFirst(E element)`|Inserts the specified element at the beginning of the `LinkedList` object.| `list.addFirst("Apple")`|
|`addLast(E element)` _or_ `add(E element)`|Appends the specified element to the end of the `LinkedList` object.|`list.addLast("Banana")`|
|`add(int index, E element)`|Inserts the specified element at the specified position in the `LinkedList` object. It also shifts the element currently at that position (if any) and any subsequent elements to the right (adds one to their indices).|`list.add(5,"Lemon")`|
|`removeFirst()`| Removes and returns the first element in the `LinkedList` object.|`list.removeFirst()`|
|`removeLast()`| Removes and returns the last element in the `LinkedList` object.|`list.removeLast()`|
|`remove(Object element)` | If the specified element object is present in `LinkedList` object, this method removes the element object wherever it is positioned and returns a boolean `true`. If such an element object doesn't exist in the list, it returns a boolean `false`. Please note that it works on only the first occurance of the element.|`list.remove("Apple")`|
|`remove(int index)`| Removes the element object in the specified index position, from the `LinkedList` object.|`list.remove(2)`|
|`getFirst()`|Returns the first element in the `LinkedList` object.|`list.getFirst()`|
|`getLast()`|Returns the last element in the `LinkedList` object.|`list.getLast()`|
|`get(int index)`|Returns the element at the specified position in the `LinkedList` object. It also shifts any subsequent elements to the left (subtracts one from their indices).|`list.get(2)`|
|`set(int index,E element)`|Replaces the element object at the specified position in the linked list with the specified element and returns the previously existing element object.|`list.set(5,"Orange")`|
|`contains(Object o)`|Returns boolean `true` if this `LinkedList` object contains the specified element object. Else, it returns `false`.|`list.contains("Banana")`|
|`isEmpty()`|Returns boolean `true` if the `LinkedList` object contains no elements.|`list.isEmpty()`|
|`size()`|Returns the number of elements the `LinkedList` object.|`list.size()`|
|`clear()`|Removes all of the elements from the `LinkedList` object.|`list.clear()`|

## Using `LinkedList` to write programs
### Example 1: Implementing a Queue
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

### Example 2: Implementing a Stack
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

### Example 3: Custom playlist creation
```java
import java.util.LinkedList;

public class PlaylistExample {
    public static void main(String[] args) {
        LinkedList<String> playlist = new LinkedList<>();

        playlist.add("Song A");
        playlist.add("Song B");
        playlist.add("Song C");

        System.out.println("Playlist: " + playlist);

        playlist.add(1, "Song D"); // Insert at specific position
        System.out.println("Updated Playlist: " + playlist);
    }
}
```



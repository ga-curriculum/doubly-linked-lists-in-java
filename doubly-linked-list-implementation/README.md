<h1>
  <span class="headline">Doubly Linked Lists in Java</span>
  <span class="subhead">Doubly Linked List Implementation</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able programmatically implement a doubly linked list data structure in Java.

## Defining the node class of a doubly linked list

The node of a doubly linked list must have one data item and two reference items - previous and next.

```java
class Node {
  int data;
  Node next;
  Node prev;

  // Constructor
  Node(int data) {
    this.data = data;
    this.next = null;
    this.prev = null;
  }
}
```

## Defining doubly linked list class and its components
A doubly linked list class can have the following components:
- **Attributes**: 
  - A **head** node that is the first node.
  - A **tail** node that is the last node.
- **Methods**:
  - A **constructor** method that initializes the head and tail node to `null`.
  - A method to **insert a node at the beginning** and make it the new head node.
  - A method to **insert a node at the end** and make a new tail node.
  - A method to **insert a node at a specific position** in the middle.
  - A method to **delete a node at the beginning** and make its next node as the new head node.
  - A method to **delete a node at the end** and make its previous node as the new tail node.
  - A method to **delete a node at a specific position** in the middle .
  - A **traverse forward** method to sequentially read all the data from head node to tail node.
  - A **traverse backward** method to sequentially read all the data from tail node to head node.
  - A **search** method to search and find a specific data item.
  - A **size** method to ascertain the number of nodes in the doubly linked list at any time during the program run.

## Demo of a doubly linked list implementation
```java
class DoublyLinkedList {
    private Node head;
    private Node tail;
    private int size;

    // Constructor
    public DoublyLinkedList() {
        this.head = null;
        this.tail = null;
        this.size = 0;
    }

    // Insert at the Beginning
    public void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = tail = newNode;
        } else {
            newNode.next = head;
            head.prev = newNode;
            head = newNode;
        }
        size++;
    }

    // Insert at the End
    public void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (tail == null) {
            head = tail = newNode;
        } else {
            newNode.prev = tail;
            tail.next = newNode;
            tail = newNode;
        }
        size++;
    }

    // Insert at a Specific Position
    public void insertAtPosition(int data, int position) {
        if (position < 0 || position > size) {
            throw new IllegalArgumentException("Invalid position");
        }

        if (position == 0) {
            insertAtBeginning(data);
            return;
        }
        if (position == size) {
            insertAtEnd(data);
            return;
        }

        Node newNode = new Node(data);
        Node temp = head;
        for (int i = 0; i < position - 1; i++) {
            temp = temp.next;
        }

        newNode.next = temp.next;
        newNode.prev = temp;
        temp.next.prev = newNode;
        temp.next = newNode;

        size++;
    }

    // Delete from the Beginning
    public void deleteFromBeginning() {
        if (head == null) {
            System.out.println("List is empty");
            return;
        }

        if (head == tail) { // Only one node
            head = tail = null;
        } else {
            head = head.next;
            head.prev = null;
        }

        size--;
    }

    // Delete from the End
    public void deleteFromEnd() {
        if (tail == null) {
            System.out.println("List is empty");
            return;
        }

        if (head == tail) { // Only one node
            head = tail = null;
        } else {
            tail = tail.prev;
            tail.next = null;
        }

        size--;
    }

    // Delete from a Specific Position
    public void deleteAtPosition(int position) {
        if (position < 0 || position >= size) {
            throw new IllegalArgumentException("Invalid position");
        }

        if (position == 0) {
            deleteFromBeginning();
            return;
        }
        if (position == size - 1) {
            deleteFromEnd();
            return;
        }

        Node temp = head;
        for (int i = 0; i < position; i++) {
            temp = temp.next;
        }

        temp.prev.next = temp.next;
        temp.next.prev = temp.prev;

        size--;
    }

    // Traverse Forward
    public void traverseForward() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }

    // Traverse Backward
    public void traverseBackward() {
        Node temp = tail;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.prev;
        }
        System.out.println();
    }

    // Search for a Value
    public boolean search(int key) {
        Node temp = head;
        while (temp != null) {
            if (temp.data == key) {
                return true;
            }
            temp = temp.next;
        }
        return false;
    }

    // Get the Size of the List
    public int getSize() {
        return size;
    }

}
```

## Demo of working with a doubly linked list 
Now, let's look at how we can use the above class as a doubly linked list object.
```java
public class DoublyLinkedListDemo {
    public static void main(String[] args) {
        DoublyLinkedList dll = new DoublyLinkedList();

        // Insertion
        dll.insertAtBeginning(10);
        dll.insertAtEnd(20);
        dll.insertAtPosition(15, 1);
        dll.insertAtEnd(25);

        // Traversals
        System.out.println("List after insertions (Forward):");
        dll.traverseForward();

        System.out.println("List after insertions (Backward):");
        dll.traverseBackward();

        // Deletions
        dll.deleteFromBeginning();
        System.out.println("After deleting from beginning:");
        dll.traverseForward();

        dll.deleteFromEnd();
        System.out.println("After deleting from end:");
        dll.traverseForward();

        dll.deleteAtPosition(1);
        System.out.println("After deleting at position 1:");
        dll.traverseForward();

        // Search and size
        System.out.println("Is 20 in the list? " + dll.search(20));
        System.out.println("Size of the list: " + dll.getSize());
    }
}
```
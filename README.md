# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Introduction to Doubly Linked Lists

## Introduction

Welcome to our exploration of linked lists! Today, we'll delve into a special variant of linked lists known as the
doubly linked list. This lesson will help you understand the structure of doubly linked lists and how they offer
additional capabilities compared to the classic linked list.

## Learning Objectives

By the end of this lesson, you will be able to:

1. Describe what a doubly linked list is and how it differs from a classic linked list.
2. Explain the elements of each node in a doubly linked list, including the data and two links (next and previous).
3. Demonstrate how to traverse a doubly linked list both forwards and backwards.
4. Discuss the operational advantages of doubly linked lists, such as ease of insertion and deletion at both ends, and
   why these features make doubly linked lists suitable for certain applications.

## Lesson Overview (60 minutes)

1. [Introduction to Linked Lists](#introduction-to-linked-lists)
2. [What is a Doubly Linked List?](#what-is-a-doubly-linked-list)
3. [Key Features](#key-features)
4. [Visual Representation](#visual-representation)
5. [Moving Forward and Backward](#moving-forward-and-backward)
6. [Summary and Key Takeaways](#summary-and-key-takeaways)

## Introduction to Linked Lists

Linked lists are a fundamental data structure in computer science, used to store collections of elements. Traditionally,
linked lists allow sequential access to its elements by moving forward from the first node. However, by enhancing the
basic structure, we can increase the flexibility of linked lists.

## What is a Doubly Linked List?

A doubly linked list is an advanced version of the classic linked list. Each node in a doubly linked list contains:

- **Data**: The value or data stored in the node.
- **Next Link**: A reference to the next node in the list.
- **Previous Link**: A reference to the previous node in the list.

This structure allows each node to connect to both its predecessor and successor in the list, enabling bidirectional
traversal of the list.

## Key Features

- **Bidirectional Traversal**: Unlike classic linked lists, doubly linked lists allow nodes to be traversed in both
  forward and backward directions. This is particularly useful in applications where navigation in either direction is
  frequent.
- **Enhanced Flexibility**: Operations such as insertion and deletion are more efficient at both ends of the list, as
  the list maintains references to both the first and last nodes.

## Visual Representation

![](assets/doubly-linked-list-01.png)

- The arrows represent the ability to traverse in both directions, with each node linked to both the next and the
  previous node.

## Moving Forward and Backward

The ability to move backward in a doubly linked list provides significant advantages:

- **Reverse Traversal**: Starting from the last node, you can traverse the list backwards to the first node, useful for
  reversing the list or performing backward searches.
- **Flexibility in Navigation**: You can easily move to previous nodes without needing to traverse from the head of the
  list, improving performance in many scenarios.

### Explanation

With a "classic" linked list, movement is limited to forward traversal. You start at the first node and follow the links
to reach subsequent nodes. This limitation stems from the fact that each node only knows about its successor, not its
predecessor.

In contrast, a doubly linked list enhances flexibility by allowing bidirectional movement. This means you can move both
forward and backward through the list. This is made possible because each node holds a reference not only to the next
node but also to the previous one. Such a structure is immensely useful in applications where reverse traversal of data
is required.

### Advantages of Doubly Linked Lists

- **Bidirectional Traversal**: Start at any node and move in either direction. This flexibility is particularly useful
  for complex data structures or algorithms that require frequent and efficient navigation of data.
- **Ease of Operations**: Insertions and deletions are more efficient, especially at the ends of the list, as you have
  direct access to both the first and last nodes.

## Implementation in Java

Here’s what the implementation of a doubly linked list looks like in Java:

### Node Definition

```java
package day02.doublylinkedlist;

public class DoublyNode {
    public DoublyNode next;
    public DoublyNode prev;
    public int value;

    public DoublyNode(int value) {
        this.value = value;
    }
}

package day02.doublylinkedlist;

public class DoublyLinkedList {

    DoublyNode head;
    DoublyNode tail;
    int size;

    // Method implementations
}
```

## Doubly Linked List Operations

```
package day02.doublylinkedlist;

public class DoublyLinkedList {

    DoublyNode head;
    DoublyNode tail;
    int size;

    // Method implementations
}
```

## Usage Example

```package day02.doublylinkedlist;

public class DoublyLinkedListDemo {
    public static void main(String[] args) {
        DoublyLinkedList doublyLinkedList = new DoublyLinkedList();
        // Demonstrations of creating, inserting, traversing, and deleting
    }
}
```

## Summary and Key Takeaways

### Summary

In this lesson, we explored the concept of doubly linked lists, a variant of the classic linked list that includes links
to both the next and the previous nodes. This structure allows for bidirectional traversal, which is a significant
enhancement over the classic linked list that only allows movement in one direction.

### Key Takeaways

1. **Bidirectional Traversal**: Doubly linked lists allow nodes to be traversed in both forward and backward directions,
   offering greater flexibility and efficiency in navigating the data.
2. **Operational Efficiency**: Operations such as insertions, deletions, and access from both ends of the list are more
   efficient, as there is no need to traverse the entire list to reach the previous elements.
3. **Enhanced Flexibility**: The ability to move backwards from any point in the list provides crucial advantages,
   especially in applications where reverse traversal is frequently required.

By understanding the structure and benefits of doubly linked lists, you are now better equipped to implement more
complex data structures that require efficient navigation and manipulation.

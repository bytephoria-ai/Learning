# 📚 Singly Linked List in Java

This repository contains a simple implementation of a **Singly Linked List** in Java. A singly linked list is a linear data structure where each element (node) contains a data part and a reference (link) to the next node in the sequence.

## 📌 Features

- Create a singly linked list
- Insert nodes at:
  - Beginning
  - End
  - Specific Position
- Delete nodes from:
  - Beginning
  - End
  - Specific Position
- Display the entire list
- Search for an element

## 🧠 What is a Singly Linked List?

A **Singly Linked List** is a linear data structure where each element (node) contains:
- **Data** – the value of the node
- **Next** – a pointer to the next node in the sequence
- 
## 📈Basic Structure:
```
Head -> [data | next] -> [data | next] -> ... -> null
```
## File Structure:
```
SinglyLinkedList/
├── Node.java // Defines the structure of a node
├── SinglyList.java // Implements singly linked list operations
└── Main.java // Main class to test the linked list
```
---

## 🧾 Code Explanation
## Singly linkedlist structure
### 📄 Node.java

```java
public class Node {
    int val;
    Node next;

    public Node(int val) {
        this.val = val;
        this.next = null;
    }
}
```
### 📄 Singly Linkedlist.java
```java
public class SinglyList {
    Node head;

    // Insert at the end
    public void insertAtEnd(int val) {
        Node newNode = new Node(val);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
    }

    // Display the linked list
    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.val + " -> ");
            temp = temp.next;
        }
        System.out.println("null");
    }
}
```
### Main.java
```java
public class Main {
    public static void main(String[] args) {
        SinglyList list = new SinglyList();
        list.insertAtEnd(10);
        list.insertAtEnd(20);
        list.insertAtEnd(30);
        list.display();  // Output: 10 -> 20 -> 30 -> null
    }
}
```


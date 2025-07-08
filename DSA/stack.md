# 📚 Stack Implementation in Java

This project demonstrates a simple stack data structure using an array in Java.  
The stack follows the **LIFO (Last-In, First-Out)** principle and includes core operations like push, pop, peek, and display.

---

## 📌 What is a Stack?

A **Stack** is a linear data structure that allows insertion and deletion only at one end, called the **top**.  
The last element added (pushed) is the first to be removed (popped).

---

## 🧠 Stack Operations

| Operation     | Description                              |
|---------------|------------------------------------------|
| `push(value)` | Adds an element to the top of the stack  |
| `pop()`       | Removes the top element from the stack   |
| `peek()`      | Returns the top element without removing |
| `isEmpty()`   | Checks if the stack is empty             |
| `display()`   | Prints all elements in the stack         |

---
## 📊 Stack Operations (Visual)
```
Initial Stack: []
Push(10)      => [10]
Push(20)      => [10, 20]
Pop()         => [10]   ← 20 is removed
Peek()        => 10
```
---

## 💻 Java Implementation

Stack structure:

```java
class MyStack{
    int size;
    int[] arr;
    int top;

    MyStack(int size){
        this.size=size;
        arr = new int[size];
        top = -1;
    }

```
Display operation logic:
```java
void display(){
        if(top == -1){
            System.out.print("Stack is empty");
            return;
        }

        for(int i=top;i>=0;i--){
            System.out.print(arr[i]+" ");
        }
        System.out.println();
        
    }
```
Full Explanation of display method:

I need to print value from stack
1) first of all check condition as top == -1 then print `Stack is empty`.
2) and then using looping for print the array in reverse order as `for(int i=top;i>=0;i--)`.

Push operation logic:

```java
void push(int data){
        if(top==size-1){
            System.out.print("Stack overflow");
            return;
        }
        arr[++top] = data;
}
```
Full Explanation of push method:

I need to push value into stack

 10 20 30  size = 3
1) first size = 3 top = -1 initially
2) data = 10 check condition (-1 == 2) then go to `arr[++top] = arr[0]` top = 0 → arr[0] = 10.
3) data = 20 check condition (0 == 2) then go to `arr[++top] = arr[1]`  top = 1 → arr[1] = 20.
4) data = 30 check condition (1 == 2) then go to `arr[++top] = arr[2]`  top = 2 → arr[2] = 30.
suppose if another element pushed in stack that can be overflow because it reach the `size = 3` here.
5) data = 40 check condition (2 == 2) then print `Stack is Overflow`

Pop operation logic:
```java
 int pop(){
        if(top == -1){
            System.out.print("Stack underflow");
            return -1;
        }
        return arr[top--];
    }
```
Full Explanation of pop method:

I need to pop value of first element in stack
1) first of all check condition as top == -1 then print `Stack is underflow`.
2) popped the value of first element in the stack as the condition as `arr[top--]`.

Peek operation logic:
```java
int peek(){
        if(top==-1){
            System.out.print("Stack is empty");
        }
        return arr[top];
    }
```
Full Explanation of peek method:

I need to peek value of first element in stack
1) first of all check condition as top == -1 then print `Stack is empty`.
2) peek the value of first element in the stack as the condition as `arr[top]`.

isEmpty operation logic:
```java
boolean isEmpty(){
        return top == -1;
    }
```
Full Explanation of isEmpty method:

I need to peek value of first element in stack
1) first of all check condition as top == -1 then print `True` or `False`.

main function logic:
```java
public class StackStru{
    public static void main(String[] args){
        MyStack s = new MyStack(3);
        s.push(10); 
        s.push(20); 
        s.push(30);
        s.display();
        s.pop();
        s.display();
        System.out.print(s.peek());
        System.out.print(s.isEmpty());
    }
}
```


# Experiment-19

# Aim :
To learn and implement queque(data structure) in C++ programming language

# Software Used : VS - Code 

# THEORY :
In C++, a queue is a type of data structure that operates on the First In, First Out (FIFO) principle, meaning that the first element added to the queue will be the first one to be removed. This is similar to a real-world queue, such as a line of people waiting for service.

Key Operations of a Queue:
1. push(): Add an element to the back of the queue.
2. pop(): Remove an element from the front of the queue.
3. front(): Access the front element (the oldest element).
4. back(): Access the last element (the most recent element).
5. empty(): Check if the queue is empty.
6. size(): Get the number of elements in the queue.

CODE :
```
// Queue

#include <iostream>
using namespace std;

#define size 5
#define ERROR -9999

class Queue {
    int rear, front, ar[size];

public:
    Queue() {
        rear = -1;
        front = -1;
    }

    void enqueue(int);
    int dequeue();
    void disp();
};

void Queue::enqueue(int num) {
    if (rear == size - 1) {
        cout << "Queue is full" << endl;
    } else {
        if (front == -1) {
            front = 0; // Initialize front when inserting the first element
        }
        ar[++rear] = num;
    }
}

int Queue::dequeue() {
    if (front == -1 || front > rear) {
        cout << "Queue is empty" << endl;
        return ERROR;
    } else {
        return ar[front++];
    }
}

void Queue::disp() {
    if (front == -1 || front > rear) {
        cout << "Queue is empty" << endl;
    } else {
        for (int i = front; i <= rear; i++) {
            cout << ar[i] << " ";
        }
        cout << endl;
    }
}

int main() {
    Queue q1;
    q1.enqueue(4);
    q1.enqueue(8);
    q1.enqueue(3);
    q1.disp();
    
    int val = q1.dequeue();
    cout << "Deleted element: " << val << endl;
    
    q1.disp();
}

```
OUTPUT :
![image](https://github.com/user-attachments/assets/90d50787-368b-460d-832b-bcaad4511f40)


CONCLUSION : We have learned and implemented Queue(data structure) 

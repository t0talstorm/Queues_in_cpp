# EXPERIMENT - QUEUES IN C++

## Aim: To study and implement the concepts of queues and queue operations in C++.

## Apparatus: VS Code or Online C++ Compiler

## Theory:

**Queue** is a fundamental linear data structure that follows the First In, First Out (FIFO) principle. In a queue, elements are inserted at one end (called the rear or back) and removed from the other end (called the front). It is similar to a real-world queue where the first person to join the line is the first person to be served. Queues are widely used in computer science for process scheduling, breadth-first search, buffering, and handling requests in web servers.

### Key Concepts:

1. **Queue Structure**: A linear data structure with two main pointers - front and rear.
   ```cpp
   class Queue {
       int arr[SIZE];
       int front, rear;
   public:
       Queue() {
           front = -1;
           rear = -1;
       }
   };
   ```

2. **Front Pointer**: Points to the first element in the queue (element to be removed next).
   ```cpp
   int front = -1;  // Initially queue is empty
   ```

3. **Rear Pointer**: Points to the last element in the queue (most recently added element).
   ```cpp
   int rear = -1;   // Initially queue is empty
   ```

4. **FIFO Principle**: First In, First Out - the element that enters first will be the first to exit.

### Queue Operations Syntax Pattern:

```cpp
class Queue {
    int arr[SIZE];
    int front, rear;
    
public:
    Queue();              // Constructor
    void enqueue(int x);  // Insert element at rear
    void dequeue();       // Remove element from front
    void display();       // Display all elements
    bool isEmpty();       // Check if queue is empty
    bool isFull();        // Check if queue is full
};
```

### Types of Queues:

1. **Simple Queue**: Basic FIFO queue with linear array implementation
2. **Circular Queue**: Queue where rear connects back to front when end is reached
3. **Priority Queue**: Elements are served based on priority rather than FIFO
4. **Double-ended Queue (Deque)**: Insertion and deletion allowed at both ends
5. **Input Restricted Queue**: Insertion only at rear, deletion at both ends
6. **Output Restricted Queue**: Insertion at both ends, deletion only at front

### Benefits of Queues:

- **Order Preservation**: Maintains the order of insertion
- **Efficient Operations**: O(1) time complexity for enqueue and dequeue
- **Memory Management**: Fixed size allocation with array implementation
- **Process Scheduling**: Natural fit for scheduling algorithms
- **Buffering**: Excellent for handling data streams and buffering
- **BFS Implementation**: Essential for breadth-first search algorithms
- **Real-time Systems**: Critical for handling requests in order

### Disadvantages of Queues:

- **Fixed Size**: Array implementation has limited capacity
- **Memory Waste**: Space once dequeued cannot be reused in simple queue
- **Random Access**: No direct access to middle elements
- **Memory Overhead**: Pointer overhead in linked list implementation

## Programs:

### 1. Basic Queue Implementation with Array

---

**File:** `queues.cpp`  
**Experiment ID:** QUE-01

**Description:** Demonstrates basic queue operations using array implementation, showcasing enqueue, dequeue, and display operations with proper overflow and underflow handling.

**Algorithm:**
1. **Enqueue Operation:**
   - Check if queue is full (rear == SIZE-1)
   - If full, display overflow message
   - If queue is empty, set front to 0
   - Increment rear and insert element at rear position
   - Display success message

2. **Dequeue Operation:**
   - Check if queue is empty (front == -1 or front > rear)
   - If empty, display underflow message
   - Otherwise, display element at front position
   - Increment front pointer to remove element

3. **Display Operation:**
   - Check if queue is empty
   - If empty, display appropriate message
   - Otherwise, traverse from front to rear and print all elements

4. **Main Function:**
   - Create queue object
   - Perform series of enqueue operations
   - Display queue contents
   - Perform dequeue operations
   - Demonstrate queue behavior with mixed operations

**Key Learning:** Understanding basic queue structure, FIFO principle, and handling of queue overflow and underflow conditions.

---

### 2. Circular Queue Implementation

---

**File:** `circular_queue.cpp`  
**Experiment ID:** QUE-02

**Description:** Implements circular queue to overcome memory wastage issue of simple queue, where rear pointer wraps around to beginning when it reaches the end, allowing reuse of freed space.

**Algorithm:**
1. **Circular Enqueue:**
   - Check if queue is full using modular arithmetic
   - Use (rear + 1) % SIZE to wrap around
   - Insert element and update rear pointer circularly

2. **Circular Dequeue:**
   - Check if queue is empty
   - Remove element from front
   - Update front pointer using modular arithmetic: (front + 1) % SIZE

3. **Full/Empty Conditions:**
   - Empty: front == rear (initially both are 0)
   - Full: (rear + 1) % SIZE == front

4. **Display Function:**
   - Traverse circularly from front to rear
   - Handle wraparound case properly

**Key Learning:** Understanding circular array concepts, modular arithmetic for wraparound, and efficient memory utilization in queue implementation.

---

## Key Learning Outcomes:

1. **Queue Fundamentals**: Understanding FIFO principle and queue structure
2. **Pointer Management**: Learning to handle front and rear pointers effectively
3. **Memory Management**: Comprehending array-based implementation and memory allocation
4. **Overflow/Underflow Handling**: Implementing proper error checking and handling
5. **Array Manipulation**: Working with arrays and index management
6. **Time Complexity**: Understanding O(1) operations for enqueue and dequeue
7. **Space Optimization**: Learning circular queue for better memory utilization
8. **Real-world Applications**: Connecting queue concepts to practical scenarios

## Applications:

- **Operating Systems**: Process scheduling, CPU scheduling, job queues
- **Network Management**: Packet queues in routers, bandwidth management
- **Web Servers**: Request handling, connection pooling, load balancing
- **Gaming**: Turn-based games, event handling, animation queues
- **Printing Systems**: Print job queues, spooling systems
- **Graph Algorithms**: Breadth-First Search (BFS) implementation
- **Simulation Systems**: Customer service simulation, traffic simulation
- **Buffer Management**: Keyboard buffers, I/O buffers, streaming data

## Advantages of Queues:

- **FIFO Guarantee**: Ensures first-come-first-served processing
- **Efficient Operations**: Constant time insertion and deletion
- **Natural Ordering**: Maintains chronological order of elements
- **Deadlock Prevention**: Helps prevent deadlock in resource allocation
- **Fair Scheduling**: Provides fair processing in multi-tasking systems
- **Buffer Implementation**: Excellent for temporary data storage
- **Synchronization**: Useful in multi-threaded programming

## Important Concepts:

- **Front Pointer**: Index of the element to be dequeued next
- **Rear Pointer**: Index where the next element will be enqueued
- **Queue Overflow**: Condition when queue is full and enqueue is attempted
- **Queue Underflow**: Condition when queue is empty and dequeue is attempted
- **Circular Implementation**: Technique to reuse freed memory space
- **Queue Size**: Maximum number of elements that can be stored
- **Queue Count**: Current number of elements in the queue

## Best Practices:

- **Initialize Pointers**: Always initialize front and rear to -1 or appropriate values
- **Boundary Checking**: Always check for overflow and underflow conditions
- **Clear Error Messages**: Provide meaningful error messages for exceptional cases
- **Memory Efficiency**: Consider circular queue for better space utilization
- **Consistent State**: Maintain queue state consistency across operations
- **Input Validation**: Validate input parameters before processing
- **Documentation**: Comment complex pointer manipulations clearly

## Common Queue Operations:

- **Enqueue**: Add element to the rear of the queue
- **Dequeue**: Remove element from the front of the queue
- **Front/Peek**: View the front element without removing it
- **IsEmpty**: Check if queue has no elements
- **IsFull**: Check if queue has reached maximum capacity
- **Size**: Get current number of elements in queue
- **Display**: Show all elements currently in queue

## Queue vs Other Data Structures:

| Aspect | Queue | Stack | Array | Linked List |
|--------|-------|-------|-------|-------------|
| **Access Pattern** | FIFO | LIFO | Random Access | Sequential |
| **Insertion** | Rear only | Top only | Any position | Any position |
| **Deletion** | Front only | Top only | Any position | Any position |
| **Use Cases** | Scheduling, BFS | Function calls, DFS | General storage | Dynamic storage |
| **Memory** | Fixed (array) | Fixed (array) | Fixed | Dynamic |
| **Performance** | O(1) enq/deq | O(1) push/pop | O(1) access | O(n) access |

## Queue Implementation Types:

```cpp
// Array-based Queue
class ArrayQueue {
    int arr[SIZE];
    int front, rear;
    // Operations...
};

// Linked List-based Queue
class LinkedQueue {
    struct Node {
        int data;
        Node* next;
    };
    Node* front;
    Node* rear;
    // Operations...
};

// Circular Queue
class CircularQueue {
    int arr[SIZE];
    int front, rear;
    int count;  // To distinguish full from empty
    // Operations...
};
```

## Queue State Visualization:

```
Initial State: front = -1, rear = -1
[ ][ ][ ][ ][ ]

After enqueue(10): front = 0, rear = 0
[10][ ][ ][ ][ ]

After enqueue(20), enqueue(30): front = 0, rear = 2
[10][20][30][ ][ ]

After dequeue(): front = 1, rear = 2
[ ][20][30][ ][ ]
```

## Common Queue Mistakes:

- **Incorrect Initialization**: Not properly initializing front and rear pointers
- **Missing Boundary Checks**: Forgetting to check for overflow and underflow
- **Pointer Management**: Incorrect increment/decrement of front and rear
- **Empty vs Full Confusion**: Mixing up conditions for empty and full queue
- **Index Out of Bounds**: Accessing array elements beyond valid range
- **Memory Waste**: Not considering circular queue for better space utilization

## Optimization Techniques:

- **Circular Implementation**: Reuse freed memory space efficiently
- **Dynamic Resizing**: Implement resizable queues for better flexibility
- **Memory Pool**: Pre-allocate memory blocks for better performance
- **Template Implementation**: Generic queue for different data types
- **Exception Handling**: Proper exception handling for error conditions
- **Thread Safety**: Implement locks for multi-threaded environments

## Testing Queue Functions:

- **Empty Queue Testing**: Test all operations on empty queue
- **Full Queue Testing**: Test enqueue on full queue
- **Single Element Testing**: Test with only one element
- **Boundary Testing**: Test with maximum capacity scenarios
- **Mixed Operations**: Test sequence of enqueue and dequeue operations
- **Stress Testing**: Test with large number of operations
- **Edge Cases**: Test with zero size, negative values, etc.

## Queue Applications in Real World:

- **CPU Scheduling**: Ready queue, waiting queue in operating systems
- **Network Buffers**: Router queues, network packet handling
- **Print Spooling**: Managing print jobs in order of submission
- **Call Centers**: Customer service queue management
- **Web Servers**: Request queue handling, connection management
- **Game Development**: Event queues, turn management
- **Streaming**: Audio/video buffering, data streaming
- **Simulation**: Queue simulation in banks, hospitals, traffic systems

## Performance Analysis:

```
Time Complexity:
- Enqueue: O(1) - Constant time insertion
- Dequeue: O(1) - Constant time deletion
- Display: O(n) - Linear time to show all elements
- Search: O(n) - Linear search through queue

Space Complexity:
- Array Implementation: O(n) - Fixed space allocation
- Linked List Implementation: O(n) - Dynamic space allocation
```

## Memory Management:

- **Static Allocation**: Fixed size array-based implementation
- **Dynamic Allocation**: Linked list-based implementation with malloc/new
- **Memory Reuse**: Circular queue implementation for efficient space usage
- **Garbage Collection**: Proper deallocation in dynamic implementations
- **Memory Leaks**: Avoiding memory leaks in pointer-based implementations
- **Cache Efficiency**: Array implementation generally more cache-friendly
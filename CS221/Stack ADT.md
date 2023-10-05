## Stack ADT

### Description

First in, last out. Imagine we have the following code:

```cpp
void main() {
    int a = circleArea(3);
}

int circleArea(int r) {
    return 3.14 * r^2;
}
```

Main calls circleArea, then has to wait for it to finish before it can return. Main is "first in", and "last out". We think of circleArea as 'stacked' on top of main.

We can think of the action always happening at the top of the stack. Items are added and removed from the top only.

### Definition: ADT

ADT stands for abstract data type. It describes a data collection as well as the operations that can be performed on this collection. Although we know the effects of the operations, we do not explicitly describe their implementations.

```cpp
template<class LIT>
class Stack {
    public:
        Stack(); // + copy, destructor etc.
        bool IsEmpty() const; 
        void Push(const LIT& e); // inserts at the top of the stack
        LIT Pop(); // removes and returns the top element
    private:
        // implementation goes here
}
```

### Implementation - Linked Lists

We could use a singly-linked list to implement a stack. Since all actions happen at the top of the stack, we only really need a head node, not a tail node. Any stack operations can be done in $O(1)$ time.

```cpp
template<class LIT>
class Stack {
    public:
        Stack(); // + copy, destructor etc.
        bool IsEmpty() const; 
        void Push(const LIT& e); // inserts at the top of the stack
        LIT Pop(); // removes and returns the top element
    private:
        struct Node {
            LIT data;
            Node* next; };
        Node* top;
        int size;      
};

template<class LIT>
bool Stack<LIT>::IsEmpty() const {
    return top == nullptr;
}

template<class LIT>
LIT Stack<LIT>::Pop() {
    assert(!isEmpty());
    LIT ret = top->data;
    Node* temp = top;
    top = top->next;
    size--;
    delete temp;
    return ret;
}

template<class LIT>
LIT Stack<LIT>::Push(LIT d) {
    Node* newnode = new Node(d);
    newnode->next = top;
    top = newnode;
    size++;
}
```

### Implementation - Arrays

Make the most recently occupied index the top of the stack. Elements are pushed into index 0, then 1, then 2, etc. Then when we want to pop, we just remove the element from the most recently occupied index.

```cpp
template<class LIT>
class Stack {
    public:
        Stack(); // + copy, destructor etc.
        bool IsEmpty() const; 
        void Push(const LIT& e); // inserts at the top of the stack
        LIT Pop(); // removes and returns the top element
    private:
        vector<LIT> items; 
};

template<class LIT>
bool Stack<LIT>::IsEmpty() const {
    return items.size == 0;
}

template<class LIT>
LIT Stack<LIT>::Pop() {
    assert(!isEmpty());
    LIT ret = items[items.size() - 1];
    items.pop_back();
    return ret;
}

template<class LIT>
LIT Stack<LIT>::Push(LIT d) {
    items.push_back(d); // we have no idea what happens in here
}
```

Note that the public interface of both the Linkedlist and array implmentations are exactly the same. However, a big problem of the array implementation is that it is limited by its size. If we push beyond the array size, we are forced to create a new array with increased size.

Let's imagine every time the array fills up, we add $c$ new spaces. If we want to push $n$ items, then we copy the array $k=\frac{n}{c}$ times. On average, each push is done in $O(n)$ time. So overall, over a sequence of $n$ operations, the total runtime complexity is $O(n^2)$. 

Let's imagine that we double the size of the list whenever it fills up. So it starts with one element, then two, then four, then eight, and so on. Then we have to copy $1 + 2 + 4 + ... + 2^{k-1}$ elements. We will make $2^k-1$ elements in total, and $k=\log(n)$. So the overall runtime is $O(n)$.

There are small benefits to using arrays, such as:
- Linked lists have some overhead in creating nodes
- Arrays use contiguous memory, so it is faster to access
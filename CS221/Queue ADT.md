## Queue ADT

### Description

Queues are FIFO (first in, first out). FIFO structures are called "fair" structures.

A queue needs to implement these methods (at least the first two):

- enqueue - insert at the back of the queue
- dequeue - remove an item from the front
- peek - return the item at the font
- is_empty - self explanatory

All of these can be implemented in constant time.

### Implementation of a linked list

In a singly linked list, where we have both head and tail pointers, inserting at the front and end can be done in $O(1)$.

But we need to consider that removing an element from a singly linked list is not always constant time! Removing it from the end takes $O(n)$ time. So we should remove from the head and insert at the tail for the implementation of the queue, since both of these operations can be done in constant time.

There is a special case where both the head and tail pointers point to the same element, when there is one element in the queue.

```cpp
template <class LIT>
class Queue {
    public:
        Queue();
        bool is_empty() const;
        void enqueue(const LIT &e);
        LIT dequeue();
    private:
        struct Node {
            LIT data;
            Node* next;
        };
        Node* front, *back;
}
```
## Singly linked lists

- Each node has value and a pointer to next node
- Terminates on null pointer
- We can keep a "sentinel node" which keeps track of the tail of the list, which makes insertion at the end a O(1) operation

## Doubly linked lists

- Now, we have pointers to both previous and next nodes
- This makes operations such as deleting the last node O(1), whereas they are O(n) in singly linked lists

## Linked lists are recursive
### Backwards printing
- Iteration is convenient for many list operations, but can be costly for a few.
- Consider we wanted to print the contents of a singly linked list in reverse:
```cpp
template <class LIT>
void PrintReverse(Node<LIT>* curr) {
    if (curr != null) {
        PrintReverse(curr->next); // ask the rest of the list to print itself.
        cout << curr->data << endl;
    }
}
```

#### Time complexity
- $T(n)=\begin{cases}1 & n=0 \\ T(n-1) + 2, &n >0 \end{cases}$
- $T(n-1) = T(n-2) + 2$
- Eventually, we see that we will have $T(n-n) + 2n$, which simplifies to O(n)

### Printing reverse odds
- Now we want to print every other element in the linked list, starting from the first element, backwards.

```cpp
template<class LIT>
void PrintReverseOdds(Node<LIT>* curr) {
    // no items in list
    if (curr == null) [
        return;
    ]

    // one item in list
    if (curr->next == null) {
        cout << curr->data << endl;
        return;
    }

    // else
    PrintReverseOdds(curr->next->next);
    cout << curr->data << endl;
}
```

### Reversing a linked list

- Can be done recursively. First we reverse the rest of the list, then point curr->next->next to curr, then point curr->next to null, then return result.

```cpp
template<class LIT>
Node<LIT>* Reverse(Node<LIT>* curr) {

}
```
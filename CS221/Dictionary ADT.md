## Dictionary

Dictionaries store ```key-value``` pairs. Given a key, it can lookup its corresponding value.

However, we are mostly interested in the keys. So let's look at a **Set**, which is an abstract data type that stores these keys.

## Set ADT

A set can store keys. These keys must be comparable. A set can quickly test for membership of a given key.

We need to implement this abstract type using a concrete type. We consider the following three operations:

- ```Search```
- ```Insert```
- ```Remove```

We have four options: Linked lists, unsorted arrays, sorted arrays, and ordered linked lists. Both linked lists and unsorted arrays require $O(n)$ time for search, $O(1)$ time for insert, and $O(n)$ for removal.

Sorted arrays take log time for search, but inserting comes at a greater cost. Sorted linked lists are just downright horrible, taking linear time for everything.
# Lesson 2:

## Creating a SinglyLinkedList:

- a singly list consists of nodes.
- first step is creating a *class Node*.
- a node is consisted of a value and a pointer to the _next_ value. to begin with we set it to _null_.

```js
class Node {
    constructor(value){
        this.val = value;
        this.next = null;
    }
}
```

- the second step is creating a *class SinglyLinkedList*.
- it contains:
    - a *head* which we will initially set to null, 
    - a *tail* which we will initially set to null 
    - a *length* which we will initially set to 0.

```js
class SinglyLinkedList{
    constructor(){
        this.head = null;
        this.tail = null;
        this.length = 0;
    }
}
```
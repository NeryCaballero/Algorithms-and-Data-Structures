# Lesson3: 

## Adding a push() method:
- push = inserting a node at the end of the list.
- the function accepts a value to create a new node.
- if the list is empty = has no head = head is null = length is 0:
    - sets the head and the tail to be the *newly created node*.
- otherwise = if there 1 or more nodes in the list:
    - sets the *next* property on the *existing tail* (last element) to be the newly created node.
    - sets the *tail* to be the newly created node.
- increments the lenght by one.
- returns the list (_represente by 'this'_)

```js
push(value) {
    var newNode = new Node(value);
    if(!this.head) {
        this.head = newNode;
        this.tail = this.head;
    } else {
        this.tail.next = newNode;       // pointer
        this.tail = newNode;            // tail
    }
    this.length++;
    return this;                        // list
}
```

## Putting it all together:

```js
class Node {
    constructor(value){
        this.val = value;
        this.next = null;
    }
}

class SinglyLinkedList{
    constructor(){
        this.head = null;
        this.tail = null;
        this.length = 0;
    }

    push(value) {
        var newNode = new Node(value);
        if(!this.head) {
            this.head = newNode;
            this.tail = this.head;
        } else {
            this.tail.next = newNode;       // pointer
            this.tail = newNode;            // tail
        }
        this.length++;
        return this;                        // list
    }
}

var list = new SinglyLinkedList;

list
SinglyLinkedList {head: null, tail: null, length: 0}

list.push(1);
SinglyLinkedList {head: Node, tail: Node, length: 1}
head: Node {val: 1, next: Node}
length: 3
tail: Node {val: 3, next: null}
__proto__: Object

list.push(2);
SinglyLinkedList {head: Node, tail: Node, length: 2}
head: Node {val: 1, next: Node}
length: 2
tail: Node {val: 2, next: null}
__proto__: Object


list.push(3):
SinglyLinkedList {head: Node, tail: Node, length: 3}
head: Node {val: 1, next: Node}
length: 3
tail: Node {val: 3, next: null}
__proto__: Object

​
```

- Pushing into a singly linked list is FAST and EASY, doent matter if there 0, 1 or a million items.
- we just take the curernt tail, update its pointer and move the tail one spot over.
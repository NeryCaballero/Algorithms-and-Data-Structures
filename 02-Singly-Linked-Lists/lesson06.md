# Lesson6: 

## Adding a unshift() method:
- unshift = inserting a node at the beginning of the list.
- the function accepts a value to create a new node.
- if the list is empty = has no head = head is null = length is 0:
    - sets the head and the tail to be the *newly created node*.
- otherwise = if there 1 or more nodes in the list:
    - sets *newly created node's* next property to be the current head. 
    - sets the *head* property to be the newly created node.
- increments the lenght by one.
- returns the list (_represente by 'this'_)

```js

unshift(value){
    var newNode = new Node(value);

    if(!this.head) {
        this.head = newNode;
        this.tail = this.head;
    } else {
        newNode.next = this.head;
        this.head = newNode;
    }
    
    this.length++;
    return this;
}
```

## Putting it all together:

``` js
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

    push(value){
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

    pop(){
        if(!this.head) return undefined;
        
        var current = this.head;
        var newTail = current;
        
        while(current.next){
            newTail = current;
            current = current.next
            
        }

        var poppedNode = current;
        
        this.tail = newTail;
        this.tail.next = null;

        this.length--;

        if(this.length === 0){
            this.head = null;
            this.tail = null;
        }

        return poppedNode;
    }

    shift(){
        if(!this.head) return undefined;
           
       var currentHead = this.head;
       var newHead     = currentHead.next;
   
       this.head = newHead;
       this.length--;
   
       return currentHead;
    }

    unshift(value){
        var newNode = new Node(value);

        if(!this.head) {
            this.head = newNode;
            this.tail = this.head;
        } 

        newNode.next = this.head;
        this.head = newNode;
        
        this.length++;
        return this;
    }
}

//test : 
let list = new SinglyLinkedList;
list.push(1)
list.push(2)
list.push(3)
list.push(4)

console.log(list)

list.unshift()
console.log(list)
```

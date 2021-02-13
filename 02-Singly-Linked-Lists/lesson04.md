# Lesson4: 

## Adding a pop() method:
- pop = removing the last node on the list.
- the function does not take in any value.
- if there are no nodes in the list = length is 0 = head is null:
    - return _undefined_.
- otherwise :
    - loop through the list until it reaches the tail.
    - store de current tail property in a variable.
    - set the tail to be the *2nd to last node*.
    - set the the new tail (*2nd to last node*)'s  *next* property to be _null_.
    - Decrement the length of the list by 1.
    - if the list only had one node = new length = 0:
        - set the head to be _null_.
        - set the tail to be _null_.
    - Return the value of the node removed.

``` js
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
}

//test : 
let list = new SinglyLinkedList;
list.push(1)
list.push(2)
list.push(3)
list.push(4)

console.log(list)

list.pop()
console.log(list)
list.pop()
console.log(list)
list.pop()
console.log(list)
list.pop()
console.log(list)
list.pop()
console.log(list)
``
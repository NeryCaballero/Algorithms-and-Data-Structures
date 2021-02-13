# Lesson5: 

## Adding a shift() method:
- shift = removing the first node on the list.
- the function does not take in any value.
- if there are no nodes in the list = length is 0 = head is null:
    - return _undefined_.
- otherwise :
    - store the current head property in a variable.
    - set the head property to be the the current head *next* property.
    - decrement the length by 1.
    - if the list only had one node = new length = 0:
        - set the head to be _null_.
        - set the tail to be _null_.
    - return the value of the node removed.


``` js 
shift(){
     if(!this.head) return undefined;
        
    var currentHead = this.head;
    var newHead     = currentHead.next;

    this.head = newHead;
    this.length--;

    if(this.length === 0){
        this.head = null;
        this.tail = null;
    }

    return currentHead;
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
}

//test : 
let list = new SinglyLinkedList;
list.push(1)
list.push(2)
list.push(3)
list.push(4)

console.log(list)

list.shift()
console.log(list)
```
# Lesson 2: 

## class methods

- From MDN Web Docs:
> The static keyword defines a static method or property FOR A CLASS. 
> Neither static methods nor static properties can be called on instances 
> of the class. Instead, THEY'RE CALLED ON THE CLASS ITSELF.
> Static methods are often utility functions, such as functions to 
> create or clone objects, whereas static properties are useful for 
> caches, fixed-configuration, or any other data you don't need to be 
> replicated across instances.


## to create a class method:
 - use the keyword *static* before the name of the method.

```js
class Point {
    constructor(x, y){
        this.x = x;
        this.y = y;
    }

    static distance(a, b) {
        const dx = a.x - b.x;
        const dy = a.y - b.y;

        console.log(Math.hypot(dx, dy));
    }
}

const p1 = new Point(5, 5);
const p2 = new Point(10, 10);

Point.distance(p1, p2)
```

- notice how we pass the method to the CLASS NAME.
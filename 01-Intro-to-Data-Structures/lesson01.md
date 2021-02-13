# Lesson 1 : 

## classes:
- Naming convention: should start with a Capital letter and be camelCased. 
- classes are blueprints that serve to create object known as instances.

## constructor() 
- is a method to instantiate new instances.
- provides the structure of the object.
- takes in values as arguments.
- asigns values to variables.

```js
class Student {
    constructor(name, lastName, age){
        this.firstName = name;
        this.lastName = lastName;
        this.age = age;
    }
}
```

- _'this'_ refers to the individual object that created from the class aka an instance.
- variables do not have to match the names of the arguments.
- values DO have to match the names of the arguments.

```js
let firstStudent = new Student('John', 'Doe', 18)
```
    
## to create a an instance:
- declare a variable
- pass by the 'new' keyword followed by the name-of-the-class
    followed by the values inside parethesis in the apropriate order.
- note that we do not call constructor at any time. 
- contructor() is executed when using the keyword 'new'.



## Instance methods:
- they are functions that live inside the class
- and provide functionalities to the instances.
- you can declare multiple instance methods.

```js
class Student {
    constructor(fName, lastName, age){
        this.firstName = fName;
        this.lastName = lastName;
        this.age = age;
    }

    fullName(){
        return `Your full name is ${this.firstName} ${this.lastName}`
    }
}

let firstStudent = new Student('John', 'Doe', 18)
firstStudent.fullName()
```

- in order to execute the method, use the syntax _instance.method()_.

```js
class Student {
    constructor(fName, lastName, age){
        this.firstName = fName;
        this.lastName = lastName;
        this.age = age;
        this.scores = [];
    }

    fullName(){
        console.log(`Your full name is ${this.firstName} ${this.lastName}`)
    }

    addScore(score){
        this.scores.push(score);
        console.log(this.scores)
    }
}

let firstStudent = new Student('John', 'Doe', 18)

firstStudent.fullName()

firstStudent.addScore(93)
```
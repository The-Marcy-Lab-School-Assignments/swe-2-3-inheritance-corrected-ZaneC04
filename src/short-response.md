# Short Responses

For this short response assignment, aim to write a response with the following qualities (your instructor will give you feedback on these areas):
- [] Addresses all parts of the prompt
- [] Accurately uses relevant technical terminology
- [] Is free of grammar and spelling mistakes (double check with grammarly!)
- [] Uses markdown to enhance readability (preview in VS Code with Command/Control + Shift + V)
- [] Is easy to comprehend

For each prompt below, write your response in the space provided. Aim to answer each prompt in 2-5 concise sentences. Make sure to preview your markdown to check how it is rendered before submitting.

## Prompt 1

In your own words, define what **inheritance** is in object-oriented programming. Then, explain what benefits it provides to developers who use it. Consider what problem it solves — what would be harder or messier without inheritance?

## Response 1  
**Inheritance** is the concept of **subclasses** that are able to reuse methods from a **superclass** using the `super` and `extends` keywords. The benefit it provides is allowing developers to follow the **DRY principle**, and reduces the amount of code needed in a program. Without inheritance, classes would need to repeat code that has already been written beforehand. 

## Prompt 2
---
Consider these classes:

```js
class Animal {
  eat() { return "eating"; }
}

class Dog extends Animal {
  bark() { return "woof"; }
}

class Puppy extends Dog {
  play() { return "playing"; }
}

const rex = new Puppy();
```

Explain what happens when `rex.eat()` is invoked. In your answer, describe the role of **inheritance** and the **prototype chain**.

## Response 2
When `rex.eat()` is invoked, the output would be `"eating"` since the `Puppy` class inherits the functionality of the `.eat()` method. Since `Puppy` is a subclass of `Dog` which is a subclass of `Animal`, the `Puppy` class is able to access the `.eat()` method because of the **prototype chain**.  This is because the `.prototype` property in each class which stores its methods, this means the reference of declared methods can be accessed by subclasses that do not have these methods declared in their own classes.

--- 

## Prompt 3

Look at these classes:

```js
class Employee {
  constructor(name, salary) {
    this.name = name;
    this.salary = salary;
  }
  getDetails() {
    return `${this.name} earns $${this.salary}`;
  }
}

class Manager extends Employee {
  constructor(name, salary, department) {
    // YOUR CODE HERE
  }
  getDetails() {
    // YOUR CODE HERE - should include both the Employee details 
    // AND the department info
  }
}
```

Complete the `Manager` class by filling in the `constructor` and `getDetails` methods. Explain why you need to use `super` in each method and what would happen if you didn't use it.

## Response 3
By using inheritance, here's the example code finished:
```js
class Employee {
    constructor(name, salary) {
        this.name = name;
        this.salary = salary;
    }
    getDetails() {
        return `${this.name} earns $${this.salary}`;
    }
}

class Manager extends Employee {
    constructor(name, salary, department) {
        super(name, salary)
        this.department = department
    }
    getDetails() {
      return `${super.getDetails()} in the ${this.department} department`
    }
}
```
The reason for using `super` in both the `constructor` and `getDetails()` properties is to be able to reuse the code in the `Employee` superclass. Since `Manager` is a subclass, we can use `super` to reuse the declarations of the properties (e.g `this.name`) and make use of the already written string in `getDetails()`.
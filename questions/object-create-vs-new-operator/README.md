# Question

## What is the difference between `new` Operator and `Object.create`?

# YouTube Video

[![youtube thumbnail](http://img.youtube.com/vi/W5IW3HPasp0/0.jpg)](http://www.youtube.com/watch?v=W5IW3HPasp0 "Object.create vs new keyword YouTube video")

## Answer

### `new` Operator

This is used to create an `Object` from `function` or `class`. It will also run the function or the contructor.

```js
const Car = function () {
  this.color = "blue";
  this.maxSpeed = 400;
};

const porshe = new Car();
const toyota = new Car();
```

```js
class Car {
  constructor() {
    this.color = "blue";
    this.maxSpeed = 400;
  }
}

const porshe = new Car();
const toyota = new Car();
```

### `Object.create`

It creates a new object, using an existing object as the prototype of the newly created object.

```js
const Car = function () {
  this.color = "blue";
  this.maxSpeed = 400;
};

const porshe = new Car();

const flyingPorsheCar = Object.create(porshe);
```

It can also be used to create an object that has no `prototype`

```js
const lib = Object.create(null);
```

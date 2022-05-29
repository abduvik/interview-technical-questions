# Question

## What are the possible ways to create an Object in Javascript?

# YouTube Video

## Answer

1. Simple JSON Object

```js
const shopCart = {
  items: 0,
  list: [],
};
```

2. Using `Object` constructor

```js
const shopCart = new Object();
```

3. Using `Function`

```js
const ShopCartClass = function () {
  this.items = 0;
  this.list = [];
};

const cart = new ShopCartClass();
```

4. Using `Class`

```js
class ShopCartClass {
  this.items = 0;
  this.list = [];
};

const cart = new ShopCartClass();
```

5. Using `Object.create(null)` to inherit from the `null` object and remove all `prototype` methods

```js
const cart = Object.create(null);
```

6. Using IIFE (Immediately Invoked Function Expression)

```js
const cart = new (function () {
  this.items = 0;
  this.list = [];
})();
```

# Question

## What is the difference between `call`, `apply` and `bind`?

# YouTube Video

[![youtube thumbnail](http://img.youtube.com/vi/Dxr3GgMZ5Ac/0.jpg)](http://www.youtube.com/watch?v=Dxr3GgMZ5Ac "Different Ways to Create Javascript Objects YouTube video")

## Answer

As a general note, these methods are really great when you would like to write Higher-Order-Functions and Functional Programming.

They are also helpful if you don't need to extend the prototype of the DOM or you would like to use methods that uses the `this` keyword.

Let's take this code as an intial setup code and the code below is the extra code

```js
const submitButton = document.getElementById("button");
const inputField = document.getElementById("input");

const onSubmitClicked = function (message, type) => {
  console.log(this.value, message, type);
};
```

> Note: using the arrow function won't work as it doesn't have context.

### `call`

It will invoke the method using the context passed to it as an argument.
It will take the method's parameters _as separate arguments_.

```js
submitButton.addEventListener("click", () => {
  setTimeout(() => {
    onSubmitClicked.call(inputField, "new message", "POST");
  }, 100);
});
```

### `apply`

It will invoke the method using the context passed to it as an argument.
It will take the method's parameters _as an array of values_.

```js
submitButton.addEventListener("click", () => {
  setTimeout(() => {
    onSubmitClicked.apply(inputField, ["new message", "POST"]);
  }, 100);
});
```

### `bind`

It will return a new method that uses the object as it's context.

```js
const onSubmitBinded = onSubmitClicked.bind(inputField);

submitButton.addEventListener("click", () => {
  setTimeout(() => {
    onSubmitBinded("new message", "POST");
  }, 100);
});
```

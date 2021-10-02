# Activity 3 - Hoisting and Scope

### Christian Alejandro Can Pérez

### Question 1

```
console.log("bar:", bar); // bar:undefined
bar = 15;
var foo = 1;
console.log(foo, bar); // 1 15
var bar;
```

- The first `console.log("bar:", bar);` outputs `bar:undefined`.
- The second `console.log(foo, bar);` outputs `1 15`.

### Question 2

```
var foo = 5;
console.log("foo:", foo); // foo: 5
var foo;
var bar = 10;
var bar;
console.log("bar:", bar); // bar: 10
var baz = 10;
var baz = 12;
console.log("baz:", baz); //baz: 12
```

- The first `console.log("foo:", foo);` outputs `foo: 5`.
- The second `console.log("bar:", bar);` outputs `bar: 10`.
- The third `console.log("baz:", baz);` outputs `baz: 12`.

### Question 3

```
function foo() {
  function bar() {
    return 5;
  }
  return bar();
  function bar() {
    return 10;
  }
}
console.log(foo()); // 10
```

- The `console.log(foo());` outputs `10`.

### Question 4

```
function foo() {
  var bar = "I'm a bar variable";

  function bar() {
    return "I'm a bar function";
  }
  return bar();
}
console.log(foo()); // TypeError: bar is not a function
```

- The `console.log(foo());` outputs `TypeError: bar is not a function`.

### Question 5

```
greeting(); //Good evening
var greeting = function () {
  console.log("Good morning");
};
greeting(); //Good morning

function greeting() {
  console.log("Good evening");
}
greeting(); //Good morning
```

- The first call to the function `greeting();` outputs `Good evening`.
- The second call to the function `greeting();` outputs `Good morning`.
- The third call to the function `greeting();` outputs `Good morning`.

### Question 6

```
var foo = 5;
console.log("foo:", foo); //foo: 5
var foo = 10;
console.log("foo:", foo); //foo: 10
```

- The first `console.log("foo:", foo);` outputs `foo: 5`.
- The second `console.log("foo:", foo);` outputs `foo: 10`.

### Question 7

```
console.log(foo()); // 3

function foo() {
  var bar = function () {
    return 3;
  };
  return bar();
  var bar = function () {
    return 8;
  };
}
```

- The `console.log(foo());` outputs `3`.

### Question 8

```
var x = "foo";
(function () {
  console.log("x: " + x); // undefined
  var x = "bar";
  console.log("x: " + x); // bar
})();
```

- The first `console.log("x: " + x);` outputs `undefined`.
- The second `console.log("x: " + x);` outputs `bar`.

### Question 9

```
function foo() {
  console.log("First");
}
foo(); // Second

function foo() {
  console.log("Second");
}
```

- The call to the function `foo()` outputs `Second`.

### Question 10

```
var foo = 5;

function baz() {
  foo = 10;
  return;

  function foo() {}
}
baz();
console.log(foo); // 5
```

- The `console.log(foo)` outputs `5`.

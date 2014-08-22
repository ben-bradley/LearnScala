# Scala vs. JavaScript

## Values/Variables

- Scala
```scala
val two = 1 + 1 // `two` is fixed
// `two = 1 + 2` would throw an error
var three = 1 + 2 // `three` is variable
// `three = 3` works
```

- JavaScript
```javascript
var two = 1 + 1; // `two` == 2
two = 'asdf'; // `two` == "asdf"
```

## Functions

### Basic

- Scala
```scala
def addOne(a: Int): Int = a + 1
```

- JavaScript
```javascript
function addOne(a) { return a + 1; }
```

### Anonymous Fns

- Scala
```scala
( (a: Int) => a + 1 )(2)
```

- JavaScript
```javascript
(function(a) { return a + 1; })(2)
```

### Partials

- Scala (pass by value!)
```scala
def adder(a: Int, b: Int) = a + b
val add2 = adder(2, _:Int)
add2(2) // 4
```

- JavaScript (pass by reference!)
```javascript
function adder(a, b) { return a + b; }
function add2(c) { return adder(2, c); }
add2(2); // 4
```

### Variable length arguments

- Scala
```scala
def capitalizeAll(args: String*) = {
  args.map { arg => arg.capitalize }
}

capitalizeAll("blargh", "honk") // ArrayBuffer(Blargh, Honk);
```

- JavaScript
```javascript
function capitalizeAll(args) {
  return args.map(function(term) {
    return term.toUpperCase();
  });
}

capitalizeAll([ 'blargh', 'honk' ]);
```

## Arrays

### `.map`

- Scala
```scala
Array("blargh", "honk").map { term => term.capitalize }
```

- JavaScript
```javascript
[ 'blargh', 'honk' ].map(function(term) { return term.toUpperCase(); });
```

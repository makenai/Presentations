# JavaScript Inheritence

---

## Why do you need inheritence?

```javascript
var cow = {
  eat: function() { console.log("yum") },
  poo: function() { console.log("poop") },
  moo: function() { console.log("moo") }
}

var chicken = {
  eat: function() { console.log("yum") },
  poo: function() { console.log("poop") },
  cluck: function() { console.log("cluck") }
}
```

---

## Don't repeat yourself

```javascript
var animal = {
  eat: function() { console.log("yum") },
  poo: function() { console.log("poop") }
}

var cow = {
  moo: function() { console.log("moo") }
}
Object.setPrototypeOf(cow,animal);

var chicken = {
  cluck: function() { console.log("cluck") }
}
Object.setPrototypeOf(chicken,animal);

cow.poo(); // poop

```

---

# [fit] JavaScript isn't classy

---

## I am a cow.

```javascript
cow.poop(); // ???
```

---

Does a cow know how to poo?

```javascript
cow.hasOwnProperty('poo') // false
```

## Shucks.

---

## But a cow is also an animal, right?

```javascript
Object.getPrototypeOf(cow) // Object {eat: function, poo: function}
```

## Yup.

---

## ..and an animal can poo, right?

```javascript
animal.hasOwnProperty('poo') // true
```

# Yay!

---

# POOP

---

# [fit] JavaScript isn't constructive.

---

```javascript

var Animal = function(name) {
  this.name = name;
}

Animal.prototype = {
  eat: function() { console.log("yum") },
  poo: function() { console.log("poop") }
}

var beast = new Animal('Keith');

console.log( beast.name ); // Keith

beast.eat(); // yum

```

---

![book](https://github.com/getify/You-Dont-Know-JS/raw/master/this%20&%20object%20prototypes/cover.jpg)

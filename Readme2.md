#### Continue Learning Notes - 2

###### Friday 10th May
+ I am working on Functions and Scopes in the *bootcamp pre-course* on Learn.co and next I am going to start Data Structures. I connected my Learn.co account to Github so all my progress and codes are available in there. Also I am using test-driven development using Mocha.

Here are few lines of my code:

```JavaScript
var animal = 'dog';

function myAnimal() {
  return animal;
}

function yourAnimal() {
  // How can we make sure that this function
  // and the above function both pass?
  // P.S.: You can't just hard-code 'cat' below
  var animal = "cat";
  return animal;
}

var funkyFunction = function() {
  return function() {
    return "FUNKY!";
  }
}

// We want to set theFunk equal to "FUNKY!" using our funkyFunction.
// NOTE: you only need to modify the code below this line.
var theFunk = funkyFunction()(); 
```

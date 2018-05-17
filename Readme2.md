#### Continue Learning Notes - 2

###### Thursday 10th May
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

###### Friday 11th and Saturday 12th May
+ I worked on the *bootcamp pre-course* and done around four lessons including scopes and arithmetic labs.

Here is a few lines of my code:
```JavaScript
var funkyFunction = function() {
  return function() {
    return "FUNKY!"
  }
}

// We want to set theFunk equal to "FUNKY!" using our funkyFunction.
// NOTE: you only need to modify the code below this line.
var theFunk = funkyFunction()()
```

+ I also started the Data Structures section. I worked on arrays and objects.

Here are some of my codes:

```JavaScript
function updateObjectWithKeyAndValue(object, key, value) {
  return Object.assign(object, {[key]: value});
}

function updateObjectWithKeyAndValue(object, key, value) {
  var newObject = Object.assign({}, object, {[key]: value});
  return newObject;
}

function destructivelyUpdateObjectWithKeyAndValue(object, key, value) {
  object[key] = value;
  return object;
}

function deleteFromObjectByKey(object, key) {
  var newObject = Object.assign({}, object);
  delete newObject[key];
  return newObject;
}

function destructivelyDeleteFromObjectByKey(object, key) {
  delete object[key];
  return object;
}
```
###### Sunday 13th, Monday 14th and Tuesday 15th May
I wasn't feeling well so I wasn't able to code.

###### Wednesday 16th May
+ Today I worked on loops and I am still working on loops lab which contains 3 exercises.

Here are few code lines:

```JavaScript
function forLoop(array) {
  for(var i = 0; i < 25; i++) {
    if(i === 1) {
      array.push("I am 1 strange loop.");
    } else {
      array.push(`I am ${i} strange loops.`);
    }
  }
  return array;
}

function whileLoop(n) {
  while(n > 0) {
    console.log(n);
    n--;
  }
  return "done";
}
```

###### Thursday 17th May
+ Today I am working on the rest of Data Structures section. I did the Beatles loops lab and I really enjoyed it and learned something new:
>* I can concatenate inside push method which I didn't know that I could do that until today.

Here are my codes from the lab:

```JavaScript
function theBeatlesPlay(musicians, instruments) {
  var arr = [];
  for(var i = 0; i < musicians.length, i < instruments.length ; i++) {
    arr.push(musicians[i] + " plays " + instruments[i]);
  }
  return arr;
}


function johnLennonFacts(array) {
  var i = 0;
  while( i < array.length) {
    array[i] += "!!!";
    i++
  }
  return array;
}


function iLoveTheBeatles(n) {
  var arr = [];
  do {
    arr.push("I love the Beatles!");
    n++
  } while(n < 15);
  return arr;
}
```

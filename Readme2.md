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
+ Also, I worked on the Deli counter lab which was a bit tough and I struggled to solve 2 out of 3 exercises.
>* The takeANumber function was a bit confusing especially the part that I had to push the name parameter to the katzDeliLine parameter in order to know the length of the deli.

```JavaScript
function takeANumber(katzDeliLine, name) {
  var katzDeli = [];
  katzDeliLine.push(name);
  katzDeli += "Welcome, " + name + ". You are number " + katzDeliLine.length + " in line.";
  return katzDeli;
}
```

>* The currentLine function I struggled with the second part of conditional statement and for loop and how to add a comma between the katzDeliLine array without adding the comma to the last index of array. This exercise took a while and coaching from Learn.on until I solved it. BUT it was a great challenge.

```JavaScript
function currentLine(katzDeliLine) {
  if(katzDeliLine.length === 0) {
    return "The line is currently empty.";
  } else {
    var newArray = [];
    var result = 'The line is currently: ';
    for(var i = 0; i < katzDeliLine.length; i++) {
      newArray.push(`${i+1}. ${katzDeliLine[i]}`);
    }
    result += newArray.join(", ")
    return result;
  }
}
```
###### Friday 18th May
+ I am working on Online Shopping Lab which has 5 functions to work on. I have done 2 until now and still working on the rest.

Here are my codes:

```JavaScript
function addToCart(item) {
 item = {
   itemName: item,
   itemPrice: Math.floor(Math.random() * 100 + 1)
 };
 cart.push(item);
 return `${item.itemName} has been added to your cart.`;
}


function viewCart() {
  var cartContents = "In your cart, you have ";
  var itemsArray = [];
  if (cart.length === 0) {
    return "Your shopping cart is empty.";
  } else {
    for(var i = 0; i < cart.length; i++) {
      itemsArray.push(`${cart[i].itemName} at $${cart[i].itemPrice}`);
    }
    if(cart.length > 1) {
      let lastItem = itemsArray.pop();
      cartContents += `${itemsArray.join(", ")}, and ${lastItem}`;
    } else {
      cartContents += itemsArray.join(", ");
    }
  }
  return cartContents + ".";
}
```

+ I did another 2 exercises in the Online Shopping Lab and I am still trying to figure out the last one.

```JavaScript
function total() {
  var total = 0;
  for(var i = 0; i < cart.length; i++) {
    total += cart[i].itemPrice;
  }
  return total;
}

function placeOrder(cardNumber) {
  var message = "Your total cost is ";
  if(cardNumber === undefined) {
    return "Sorry, we don't have a credit card on file for you."
  } else {
    message += `$${total()}, which will be charged to the card ${cardNumber}.`;
    cart.splice(0);
    return message;
  }
}
```
+ Finally I am done with the last function! It took ages to solve it with the help of 2 coaching chats.

```JavaScript
function removeFromCart(item) {
  var itemObject;
  for(var i = 0; i < getCart().length; i++) {
    if(getCart()[i].itemName === item) {
      itemObject = getCart()[i];
    }
  }
  if(itemObject) {
      let indexOfItem = getCart().indexOf(itemObject);
      getCart().splice(indexOfItem, 1);
    } else {
      return "That item is not in your cart."
    }
}
```

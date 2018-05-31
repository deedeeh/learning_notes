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

###### Sunday 20th May
+ I started *The DOM* section in the bootcamp pre-course and learned about traversing nested objects and DOM tree and done a lab with 4 exercises.

Here are few lines of code:

```JavaScript
function nestedTarget() {
  const target = document.querySelector("#nested .target");
  return target;
}

function increaseRankBy(n) {
  const lis = document.querySelectorAll(".ranked-list li");
  for(let i = 0; i < lis.length; i++) {
    lis[i].innerHTML = parseInt(lis[i].innerHTML)+n;
  }
  return lis;
}
```
+ I have also learned about breadth-first search algorithm... it is a bit hard to understand at the beginning but I believe with practice things will be better to understand.
There was an exercise that I used this algorithm to solve.

```HTML
<div id="grand-node">
        <div>
          <div>
            <div>
              <div>
                boo!
              </div>
            </div>
          </div>
        </div>
      </div>
```

```JavaScript
function deepestChild() {
  let node = document.querySelector("#grand-node");
  let nextNode = node.children[0];

  while(nextNode) {
    node = nextNode;
    nextNode = node.children[0];
  }
  return node;
}
```  

+ Today I went through something I have never seen before which is stopPropagation() event property and the difference between bubbling and capturing and how they trigger multiple events on the way up to the root(bubbling) or down to the target(capturing) and here stopPropagation() comes in handy. The only thing I was familiar with during this lesson is preventDefault() property.

Here are few lines of the codes from the lesson:

```JavaScript
const divs = document.querySelectorAll("div");
function bubble(e) {
  e.stopPropagation();
  console.log(this.firstChild.nodeValue.trim() + " bubbled")
}

for(let i = 0; i < divs.length; i++) {
  divs[i].addEventListener("click", bubble)
}
```

###### Monday 21st May
+ Today I worked on the last lesson in DOM section which is Konami Code Lab.

Here is my codes:

```JavaScript
function init() {
  let index = 0;
  document.body.addEventListener("keydown", function(e) {
    const key = e.key;

    if(key === codes[index]) {
      index++

      if(index === codes.length) {
        alert("Hurray!");

        index = 0;
      }
    } else {
      index = 0;
    }
  })
}
```
I like the refactoring solution on Learn.co that appears after passing and submitting my code. I always check it to see maybe different solution or if I can refactor my code.

I think the only differences here is using arrow function as the second argument for addEventListener and using the conditional ternary operator which I still get confused when I try to use it!

```JavaScript
function init() {
  let idx = 0

  document.body.addEventListener("keydown", (e) => {
    const key = e.key

    idx = (codes[idx] === key) ? ++idx : 0

    if (idx === codes.length) {
      window.alert("Hurray!");
      idx = 0
    }

  });
}
```

+ I think the rest of the day I will be preparing for behavioural interview questions and register on cv-library and co-hire because I am actively looking for jobs beside practising and learning new things.

###### Tuesday 22nd May
+ I was working on behavioural interview questions because I have an interview this week with Flatiron School Bootcamp admission team.

+ I started working on *jQuery* section in the pre-course bootcamp.  

Here are few codes from jQuery selectors lab:

```JavaScript
function lastImageSelector() {
  return $("div img:last");
}

function ninjaBabySelector() {
  return $("#baby-ninja");
}

function divSelector() {
  return $(".pics");
}

function firstListItem() {
  return $("#pic-list li:first-child");
}
```

+ I worked on the jQuery Event Listeners Lab which was really fun. This is the last lesson I am going to do today and I might go back to the interview questions again.

Here are few lines of my code:

```JavaScript
function getIt() {
  $("p").on("click", function() {
    alert("Hey!");
  });
}

function frameIt() {
  $("img").on("load", function() {
    $("img").addClass("tasty");
  });
}

function pressIt() {
  $("input:first-child").on("keydown", function(key) {
    if(key.which === 71) {
      alert("you have pressed G");
    }
  });
}
```

###### Wednesday 23rd May
+ I continued interview questions for the first half of the day.

+ I finished jQuery section and now I have one more task to do to finish *JavaScript Fundamentals* part, which is a project called Rock Dodger. It doesn't seem easy at all but hopefully will be able to do it, might not be able to finish it today tho.


###### Thursday 24th May
+ I started *Ruby Fundamentals* part which consists of many sections. I am doing today the introduction and next time I will start Debugging.

+ The rest of the time I will be doing interview questions.  

###### Sunday 27th May
+ I haven't been coding for the past 2 days cause of some circumstances. Today I worked on *Ruby Fundamentals* Debugging section. Mainly it was about the 4 types of error and how to read errors.

+ I started to work on the technical track for my technical interview for the bootcamp which consists of few labs and once I finish them I will book my technical interview.

+ Once I finish my technical track I will go back to the Rock Dodger project to finish the *Javascript Fundamentals* part in the pre-course track.

###### Tuesday 29th May
+ I worked on the technical track and finished it and I booked my technical interview for my admissions to the bootcamp.

+ I will start working on the Rock Dodger project.

###### Wednesday 30th May
+ Today I am working on *JavaScript Fundamentals Project* Rock Dodger. I am half way through the lab but it is not an easy one at all!

Lines of code with instructions:

```JavaScript
function checkCollision(rock) {
  // implement me!
  // use the comments below to guide you!
  const top = positionToInteger(rock.style.top)

  // rocks are 20px high
  // DODGER is 20px high
  // GAME_HEIGHT - 20 - 20 = 360px;
  if (top > 360) {
    const dodgerLeftEdge = positionToInteger(DODGER.style.left)

    // FIXME: The DODGER is 40 pixels wide -- how do we get the right edge?
    const dodgerRightEdge = dodgerLeftEdge + 40;

    const rockLeftEdge = positionToInteger(rock.style.left)

    // FIXME: The rock is 20 pixel's wide -- how do we get the right edge?
    const rockRightEdge = rockLeftEdge + 20;

   /*** Think about it -- what's happening here?
    * There's been a collision if one of three things is true:
    * 1. The rock's left edge is < the DODGER's left edge,
    * and the rock's right edge is > the DODGER's left edge;
    * 2. The rock's left edge is > the DODGER's left edge,
    * and the rock's right edge is < the DODGER's right edge;
    * 3. The rock's left edge is < the DODGER's right edge,
    * and the rock's right edge is > the DODGER's right edge
    ***/
    if ((rockLeftEdge < dodgerLeftEdge && rockRightEdge > dodgerLeftEdge) || (rockLeftEdge >= dodgerLeftEdge && rockRightEdge <= dodgerRightEdge) || (rockLeftEdge < dodgerRightEdge && rockRightEdge > dodgerRightEdge)) {
      return true
    }
  }
}
```
###### Thursday 31st May
+ Finallyyyyy!!! I finished the Rock Dodger lab and I am so happy! It is a great practice and I've learned many things during the *JavaScript Fundamentals* section. Now I can continue working on *Ruby Fundamentals* plus maybe working on JS in Udemy bootcamp that I was doing before the Learn.co pre-course.

Here are some lines of my code:

```JavaScript
function endGame() {
  clearInterval(gameInterval);
  for(let i = 0; i < ROCKS.length; i++) {
    ROCKS[i].remove();
  }
  window.removeEventListener('keydown', moveDodger);
  alert("YOU LOSE!");
}

function moveDodger(e) {
  // implement me!
  /**
   * This function should call `moveDodgerLeft()`
   * if the left arrow is pressed
   */
   if(e.which === LEFT_ARROW) {
     e.preventDefault();
     e.stopPropagation();
     moveDodgerLeft();
   }
   /**
   * and `moveDodgerRight()` if the right arrow is pressed
   * (Check the constants we've declared for you above.)
   * And be sure to use the functions declared below!
  */
  else if(e.which === RIGHT_ARROW){
    e.preventDefault();
    e.stopPropagation();
    moveDodgerRight();
  }
}
```

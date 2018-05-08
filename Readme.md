### MY LEARNING NOTES

#### Target:

+ Learn more Vanilla JS and document the outcome and share it on Github.
+ Create more projects to build my portfolio and learn through the process.

Currently I am doing a Web Developer Bootcamp on Udemy by Colt Steele who is a developer and bootcamp instructor.

The course covers Frontend which I have some of its skills and Backend which I know nothing about! It is a good opportunity to learn new technologies that will help me in my career and understand what happens under the hood.

###### Tuesday 6th of March
+ I did an *Image Blog* using HTML and CSS as part of the Bootcamp Intermediate CSS section and next I will be creating a Blog.

Here are few lines of my stylesheet:

```CSS
.title {
  margin-left: 1.66%;
  font-family: 'Raleway', sans-serif;
  font-weight: 800;
  font-size: 24px;
  text-transform: uppercase;
  border-bottom: 1px solid #000;
  width: 30%;
  padding-bottom: 20px;
}
```

+ I created a *Blog* using HTML5 and CSS and I really enjoyed building it and it didn't take time.

```HTML
<article>
  <p class="date">November 23 2015</p>
  <h1 class="heading">This is my first article</h1>
  <p class="border-left">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat ut enim ad minim veniam sed do eiusmod tempor.</p>
  <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt.</p>
  <p>Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem.</p>
</article>
```

```CSS
.date {
  color: #3498db;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: .2em;
}

.heading {
  color: #2c3e50;
  font-size: 2em;
  font-weight: 900;
  text-transform: capitalize;
  letter-spacing: 1px;
}

.border-left {
  border-left: 6px solid #bdc3c7;
  padding-left: 6px;
}
```

###### Wednesday 7th March
+ Today I am doing the Introduction to JavaScript as a quick reminder to JS because I haven't be coding regularly for some time. I did the primitive data types in addition to 2 simple exercises.

Next is JS Basics: Control Flow.

###### Thursday 8th March
+ Today I went off track by having a basic knowledge about *React* and the reason for that I am going to ReactFest 9 March 2018. I applied for the diversity ticket and I got one! I am excited!
+ A dear friend recommended to check React on the [beta.freecodecamp.org](https://beta.freecodecamp.org) and that is what I am doing today just React.
+ I've learned about JSX and creating React components.

Here are few lines of my code:

```JavaScript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>Hello React!</h1>
      </div>
    );
  }
};
```

###### Friday 9th March
+ Today I went to ReactFest which was awesomeeeeee!!! I am really glad I had the chance to attend this event.
+ I did continue some of the *Web Developer Bootcamp* JavaScript Basics: Control Flow. Here are some of the things I worked on:
>* Comparison operators & type coercion.
>* Logical operators & short circuit evaluation.
>* Truthy & Falsy values.
>* Conditional statements.

###### Sunday 29th April
+ I am back to coding after being away for a while and I finished the *Web Developer Bootcamp* JavaScript Basics: Control Flow section. I have worked on *while* and *for* loops and done few exercises.

Few lines of my code:

```JavaScript
//Print all odd numbers between 300 and 333

//for loop
for(var i = 300; i <= 333; i++) {
  if(i % 2 !== 0) {
    console.log(i);
  }
}

//while loop
var counter = 300;

while(counter <= 333) {
  if(counter % 2 === 1) {
    console.log(counter);
  }
  counter++;
}
```
+ I worked on JavaScript Basics: Functions and next will be scope and higher order functions.

Here are some code from Problem Set exercises:

```JavaScript
//isEven() takes a single numeric argument and returns true if even and false otherwise.

function isEven(num) {
  if(num % 2 === 0) {
    return true;
  } else {
    return false;
  }
}


//kebabToSnake() takes a single kebab-cased string argument and returns the snake_cased version.

function kebabToSnake(str) {
  //Used a var because replace returns a new copy of the string and not changing the original string
  var newStr = str.replace(/-/g, "_");
  return newStr;
}


//factorial() takes a single numeric argument and returns the factorial of that number.

function factorial(num) {
  //define a result variable
  var result = 1;
  //calculate factorial and store value in result
  for(var i = 2; i <= num; i++) {
    result *= i;
  }
  //return the result variable
  return result;
}
```
###### Monday 30th April
+ I worked on  JavaScript basics: Arrays and did a small version of a todo list exercise.

Here is the todo list:

```HTML
  <body>
    <h1>Todo List</h1>
    <ul>
      <li>&#34;new&#34; &#8211; Add A Todo</li>
      <li>&#34;list&#34; &#8211; View All Todos</li>
      <li>&#34;quit&#34; &#8211; Quit App</li>
    </ul>
  </body>
```

```JavaScript
var todos = ["Finish JS basics:Arrays"];

window.setTimeout(function() {
  var input = prompt("What would you like to do?");

  while(input !== "quit") {
    //handle input
    if(input === "list") {
      console.log(todos);
    } else if (input === "new"){
      //ask for new todo
      var newTodo = prompt("Enter new todo");
      //add to todos array
      todos.push(newTodo);
    }
    //ask again for new input
    input = prompt("What would you like to do?");
  }
  console.log("OK, YOU QUIT THE APP");
}, 500);
```
###### Tuesday 1st May
+ Today I spent couple of hours coding and the rest of the day was enjoying my birthday! I did continue the Arrays sections and finished array iteration with for loop and forEach method plus I learned about splice method.

+ Done todo list part 2 of the exercise where I used forEach and splice and did some refactoring.

```JavaScript
function listTodos() {
  console.log("**********");
  todos.forEach(function(todo, i) {
    console.log(i + ": " + todo);
  });
  console.log("**********");
}

function deleteTodo() {
    //ask for index of todo to be deleted
    var index = prompt("Enter index of todo to delete");
    //delete that todo
    todos.splice(index, 1);
    console.log("Deleted todo");
  }
```

###### Wednesday 2nd May
+ I worked on Array Problem Set which contains 4 exercises involves using functions with arguments, loops and conditional statements.

Here are couple of them:

```JavaScript
//isUniform() takes an array as an argument and returns true if all elements in
//the array are identical
function isUniform(arr) {
  var first = arr[0];
  for(var i = 1; i < arr.length; i++) {
    if(arr[i] !== first) {
      return false;
    }
  }
  return true;
}

//sumArray() accepts an array of numbers and returns the sum of all numbers in the array
function sumArray(arr) {
  var sum = 0;
  arr.forEach(function(num) {
    sum += num
  });
  return sum;
}
```

###### Thursday 3rd May
+ Today I am Working on JavaScript basics: Objects. Learned about the different ways for initialisation such as object literal notation, initialise a variable with curly braces and then add data and finally use the  keyword new Object(). Objects use key/value pairs to access data, update, add and delete.

+ There are few cases that I will need to use bracket notation instead of dot notation which are:
>* property names starts with a number.
>* property names with spaces
>* Lookup for a variable.
```JavaScript
var str = "name";
someObject.str //doesn't look for "name"
someObject[str] //does evaluate str and looks for "name"
```

+ I worked on a Movies Database Exercise using array of objects.

Here is my code:

```JavaScript
var movies = [
  {
    title: "Taxi",
    rating: 3.5,
    hasWatched: true
  },
  {
    title: "Finding Nemo",
    rating: 4.5,
    hasWatched: true
  },
  {
    title: "Phantom Thread",
    rating: 4,
    hasWatched: false
  }
];

movies.forEach(function(movie) {
  if(movie.hasWatched === true) {
    console.log('You have watched "' + movie.title + '" - ' + movie.rating + " stars");
  } else {
    console.log('You have not seen "' + movie.title + '" - ' + movie.rating + " stars");
  }
});
```

###### Friday 4th May
+ I learned about object methods and the reasons to use them such as namespace collision.
+ The use of the keyword *this* inside methods.

Next will be working on DOM Manipulation.

###### Saturday 5th May
+ I started to work on *DOM Manipulation* section and I did an exercise for different ways to select an element.

Here is my code:

```HTML
<body>
  <h1>I am an h1!</h1>
  <p id="first" class="special">Hello</p>
  <p class="special">Goodbye</p>
  <p>Hi Again</p>
  <p id="last">Goodbye Again</p>
  <script type="text/javascript" src="dom.js"></script>
</body>
```

```JavaScript
//Different ways to select the first p element

//best option for this case
var first = document.getElementById("first");
var second = document.querySelector("#first");
var third = document.querySelector("p");
var fourth = document.querySelector(".special");
var fifth = document.getElementsByClassName("special")[0];
var sixth = document.getElementsByTagName("p")[0];
```

+ I learned about classList property to add, remove and toggle elements, properties like textContent and innerHTML and the difference between them. Also, worked with getAttribute and setAttribute properties.

+ Next I am going to start *Advanced DOM Manipulation* and will work on exercises and a project to practise it.

###### Tuesday 8th May
+ Today I started *Advanced DOM Manipulation* and I worked on few tutorials and an exercise which is based on events Listeners.

Here are few lines of my code:

```HTML
<head>
    <meta charset="utf-8">
    <title>Color Toggle Exercise</title>
    <style type="text/css">
      .purple {
        background: purple;
      }
    </style>
  </head>
  <body>
    <button>CLICK ME!</button>
    <script type="text/javascript" src="script.js"></script>
  </body>
```

```JavaScript
var button = document.querySelector("button");
var body = document.querySelector("body");
var isPurple = false;

//1st solution
button.addEventListener("click", function() {
  if(isPurple) {
    body.style.background = "white";
  } else {
    body.style.background = "purple";
  }
  isPurple = !isPurple;
});

//2nd solution
button.addEventListener("click", function() {
  body.classList.toggle("purple");
});
```
+ I worked on *score keeper* project which is basically with very simple HTML and it was focusing on JS and its functionality.

Here are some of my codes:

```HTML
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Score Keeper Project 1</title>
    <link rel="stylesheet" href="scorekeeper.css">
  </head>
  <body>
    <h1><span id="p1_display">0</span> to <span id="p2_display">0</span></h1>
    <p>Playing to: <span id="winning_score">5</span></p>
    <input type="number">
    <button id="p1_button">Player One</button>
    <button id="p2_button">Player Two</button>
    <button id="reset">Reset</button>
    <script type="text/javascript" src="scorekeeper.js"></script>
  </body>
</html>
```

```JavaScript
var p1Button = document.getElementById("p1_button");
var resetButton = document.getElementById("reset");
var p1Display = document.querySelector("#p1_display");
var numInput = document.querySelector("input");
var winningScoreDisplay = document.querySelector("#winning_score");
var p1Score = 0;
var gameOver = false;
var winningScore = 5;

p1Button.addEventListener("click", function() {
if(!gameOver) {
  p1Score++;
  console.log(p1Score, winningScore);
  if(p1Score === winningScore) {
    p1Display.classList.add("winner");
    gameOver = true;
  }
}
p1Display.textContent = p1Score;
});

resetButton.addEventListener("click", function() {
  reset();
});

function reset() {
  p1Score = 0;
  p2Score = 0;
  p1Display.textContent = p1Score;
  p2Display.textContent = p2Score;
  p1Display.classList.remove("winner");
  p2Display.classList.remove("winner");
  gameOver = false;
}

numInput.addEventListener("change", function() {
  winningScoreDisplay.textContent = this.value;
  winningScore = Number(this.value);
  reset();
});
```

In the previous JS I added the player 1 to show my work without player 2 to make things short. And the winner class just to add green colour to whoever has reached the winning score.

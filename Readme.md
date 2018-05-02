### MY LEARNING NOTES

#### Example

+ Learn more Vanilla JS and document the outcome and share it on Github.
+ Build more projects to build my portfolio and learn through the process.

```JavaScript
function removeTransition(e) {
  if (e.propertyName !== 'transform') return;
  e.target.classList.remove('playing');
}
```

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

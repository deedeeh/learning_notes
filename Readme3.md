#### Continue Learning Notes - 3

###### Friday 1st June
+ Today I am working on *Methods* in Ruby and I am learning about TDD and Rspec and how testing makes your code flexible and helps to write code that is robust.

Here are few lines of the codes for Rspec:
```Ruby
require_relative '../current_age_for_birth_year.rb'

describe "current_age_for_birth_year method" do
it "returns the age of a person based on the year of birth" do
    age_of_person = current_age_for_birth_year(1984)

    expect(age_of_person).to eq(19)
  end
end
```
And here is to pass the tests:

```Ruby
def
  current_age_for_birth_year(birth_year);
  2003 - birth_year
end
```

###### Sunday 3rd June
+ I worked on the rest of Ruby *Methods* section and I leaned about default arguments and required arguments. I also learned how to use array elements with string interpolation instead of having the data stored in variables especially when it is a list of data.

Here are few lines of my codes:

```Ruby
def display_board(board)
  puts " #{board[0]} | #{board[1]} | #{board[2]} "
  puts "-----------"
  puts " #{board[3]} | #{board[4]} | #{board[5]} "
  puts "-----------"
  puts " #{board[6]} | #{board[7]} | #{board[8]} "
end
```
I also worked on 2 tests in Rspec.

```Ruby
board = ["O", "O", "O", "O", "O", "O", "O", "O", "O"]

    output = capture_puts{ display_board(board) }
    rows = output.split("\n")

    expect(rows[0]).to eq(" O | O | O ")
    expect(rows[1]).to eq("-----------")
    expect(rows[2]).to eq(" O | O | O ")
    expect(rows[3]).to eq("-----------")
    expect(rows[4]).to eq(" O | O | O ")
```

###### Monday 4th June
+ I started to work on *Color Game Project* in the web developer bootcamp on Udemy and it is been great so far! I am going to add this project on Github.

```HTML
<body>
  <h1>The Great <span id="colorDisplay">RGB</span> Color Game</h1>

  <div>
    <span id="message"></span>
  </div>
  <div id="container">
    <div class="square"></div>
    <div class="square"></div>
    <div class="square"></div>
    <div class="square"></div>
    <div class="square"></div>
    <div class="square"></div>
  </div>
  <script type="text/javascript" src="colorGame.js"></script>
</body>
```
```javascript
for(let i = 0; i < squares.length; i++) {
 //add initial colors to squares
 squares[i].style.backgroundColor = colors[i];

 //add event listeners to squares
 squares[i].addEventListener("click", function() {
   //grab color of clicked square
   var clickedColor = this.style.backgroundColor;
   //compare color to pickedColor
   if(clickedColor === pickedColor) {
     messageDisplay.textContent = "Correct!";
     changeColors(clickedColor);
   } else {
     this.style.backgroundColor = "#232323";
     messageDisplay.textContent = "Try again!";
   }
 });
}
```
+ I worked on *Command Line Applications* section in Ruby and it is been great learning about it for the first time. Usually a CLI greets the user, ask for input, capture and store that input and then do something with it and have it as output.

```Ruby
#!/usr/bin/env ruby
require_relative "../lib/greeting.rb"

# code your CLI here!
puts "Hi! I'm HAL, what's your name?"
name = gets.strip
greeting(name)
```

I finished the *Command Line Interface* section and the last lab was a tic tac toe project. It was fun to work on it!

Here is the Lib/move.rb file:

```Ruby
def display_board(board)
  puts " #{board[0]} | #{board[1]} | #{board[2]} "
  puts "-----------"
  puts " #{board[3]} | #{board[4]} | #{board[5]} "
  puts "-----------"
  puts " #{board[6]} | #{board[7]} | #{board[8]} "
end

# code your input_to_index and move method here!

def input_to_index(user_input)
  return user_input.to_i - 1
end

def move(board, index, character="X")
  board[index] = character;
end
```

Here is the bin/move file:

```Ruby
#!/usr/bin/env ruby

require_relative '../lib/move.rb'

# Code your CLI Here

puts "Welcome to Tic Tac Toe!"

board = [" ", " ", " ", " ", " ", " ", " ", " ", " "];

puts "Where would you like to go?"

input = gets.strip

index = input_to_index(input)

move(board, index)

display_board(board)
```

###### Tuesday 5th June
+ I worked on *Logic and Conditionals* section in Ruby pre-course bootcamp. I learned that everything in Ruby is truthy except false and nil are falsey. I also learned about boolean operators (!, &&, || ) and comparison operators.

Next time I am working on this section I will be working on 3 labs to practice what I've learned so far.

+ I went through my code for the technical track and checked the solution on Learn.co and comparing it to my code so I understand if there are different and better ways to implement my code. MY TECHNICAL INTERVIEW IS TOMORROW!

###### Wednesday 6th June
+ I was preparing for my technical interview and reading about the interview process and then I had my technical interview which consisted of 2 parts: the 1st part was explaining my Deli Counter Lab code and the 2nd part I was asked to improve one of the functions in the lab. Within a week I will know the result of the interview and if I got accepted in the bootcamp!

+ I worked on 2 labs in the *Logic and Conditionals* section in Ruby that explains Rspec with DSL (describe, it, expect, to, eq), TDD and lots of practice with conditional statements.

Here are few lines of my code:

```Ruby
def fizzbuzz(input)
  if input % 3 == 0 && input % 5 == 0
    "FizzBuzz"
  elsif input % 3 == 0
    "Fizz"
  elsif input % 5 == 0
    "Buzz"
  else
    print "nil"
  end
end
```
```Ruby
def position_taken?(board, index)
  if (board[index] == " " || board[index] == "" || board[index] == nil)
    false
  else
    true
  end
end
```

###### Friday 8th June
+ I worked on the last lab in *Logical & Conditionals* section in Ruby Fundamentals, Valid Tic Tac Toe Move. Next is *Loops* section.

Here is the lab code:

```Ruby
def valid_move?(board, index)
  if index.between?(0, 8) && !position_taken?(board, index)
    true
  end
end
```
+ I have an interview next week and I have done my research today on the company. Still will be working on interview questions in the next few days.

+ The rest of the day I will working on the Color Game Project.

###### Saturday 9th June
+ I worked on the rest of the Color Game Project. It was mostly fixing some of the functionalities and refactoring code.

You can find the project in my repositories on Github with the title *Color_Game_Project*.

+ I started working on *Loops* section in Ruby. I've learned about loop, while and until keywords and the difference between each one of them especially the until is the inverse of while loop. I did one lab for this section and there are 2 more to go.

Here are my codes:

```Ruby
def using_while
  levitation_force = 6

  #your code here
  while levitation_force < 10
    puts "Wingardium Leviosa"
    levitation_force += 1
  end
end
```

```Ruby
def using_until
  levitation_force = 6

  #your code here
  until levitation_force == 10
    puts "Wingardium Leviosa"
    levitation_force += 1
  end
end
```
+ The rest of the day I will be working on interview questions.

###### Sunday 10th June
+ I worked on Tic Tac Toe Turn lab in *Loops* section and it was fun working on it. I still have 1 more lab to finish loops.

Here is my new code:

```Ruby
def turn(board)
  puts "Please enter 1-9:"
  user_input = gets.strip
  index = input_to_index(user_input)
  if valid_move?(board, index)
    move(board, index)
  else
    turn(board)
  end
  display_board(board)
end
```
+ I also worked on *Intro to jQuery* in the online web developer bootcamp and I have few more lessons to finish until I start *Advanced jQuery* section. I will create a repository on Github for small projects related to this course.

###### Tuesday 12th June
+ I worked on the last lab in *Loops* section and now I am ready for the next section *Iteration*

Here is my code from the lab:

```Ruby
def play(board)
  count_turns = 0;
  while count_turns < 9
    turn(board)
    count_turns += 1
  end
end
```
+ I done few interview questions today as well.

###### Wednesday 13th June
+ Today I worked on interview questions and still have some more to work on until next week. 

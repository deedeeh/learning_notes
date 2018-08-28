#### Continue Learning Notes - 9

###### Monday 20th August
+ I worked on *__Tic Tac Toe Game Status__* lab where I practised boolean & search enumerables such as `detect` & `all?` plus I used logical operators; `&&`, `||` and not operator `!`.

Here is my solution:

```Ruby
# this is all the possible winning combinations for tic tac toe
WIN_COMBINATIONS = [
  [0,1,2],
  [3,4,5],
  [6,7,8],
  [0,3,6],
  [1,4,7],
  [2,5,8],
  [0,4,8],
  [2,4,6]
  ]

# It returns the winning combination if it is true otherwise returns false.
def won?(board)
  WIN_COMBINATIONS.detect do |win_combination|
    if board[win_combination[0]] == board[win_combination[1]] && board[win_combination[1]] == board[win_combination[2]] && position_taken?(board, win_combination[0])
      win_combination
    end
  end
end

board.all? {|move| move == "X" || move == "O"}
end

def draw?(board)
  full?(board) && !won?(board)
end

def over?(board)
  draw?(board) || won?(board)
end

def winner(board)
  if won?(board)
    board[won?(board).first]
  end
end
```
>* `#first` => returns the first element, or the first n elements, of the array. If the array is empty, the first form returns nil, and the second form returns an empty array.

I checked Learn.co solution and it almost the same as mine.

###### Thursday 23rd August
+ I am working on *__TicTacToe.rb__* lab which is the last lab in *__Tic Tac Toe__* section.

+ I finished lots of methods but still have 1 more to do `#play` which is the main one for the CLI application.

```Ruby
def input_to_index(user_input)
  user_input.to_i - 1
end

def move(board, position, token)
  board[position] = token
end

def position_taken?(board, position)
  board[position].include?("X") || board[position].include?("O")
end

def valid_move?(board, position)
  position.between?(0,8) && !position_taken?(board, position)
end

def turn_count(board)
  count = 0
  board.each {|cell| count += 1 if cell == "X" || cell == "O"}
  count
end

def current_player(board)
  count = turn_count(board)
  count.even? ? "X" : "O"
end

def turn(board)
  puts "Please enter 1-9:"
  user_input = gets.chomp
  index = input_to_index(user_input)
  if valid_move?(board, index)
    move(board, index, current_player(board))
    display_board(board)
  else
    turn(board)
  end
end

def won?(board)
  WIN_COMBINATIONS.detect do |win_combination|
    if board[win_combination[0]] == board[win_combination[1]] && board[win_combination[1]] == board[win_combination[2]] && position_taken?(board, win_combination[0])
      win_combination
    end
  end
end

def full?(board)
  board.all? {|cell| cell == "X" || cell == "O"}
end

def draw?(board)
  full?(board) && !won?(board)
end

def over?(board)
  full?(board) || won?(board)
end

def winner(board)
  if win = won?(board)
    board[win.first]
  end
end
```

>* One of Learn.co methods that used a `#count` which I haven't used before with a block is `turn_count(board)`
```Ruby
def turn_count(board)
  board.count {|token| token == "X" || token == "O"}
end
```
>>* This method is much easier & shorter than mine.
>>* They didn't have to create var count and then return it at the end plus increment it in the block.

+ I've learned about `between?(min, max)` which is a *comparable* and we use it to check if a value is between a range.
```Ruby
3.between?(1, 5)               #=> true
6.between?(1, 5)               #=> false
'cat'.between?('ant', 'dog')   #=> true
'gnu'.between?('ant', 'dog')   #=> false
```

Comparable:
---
>* The Comparable *mixin* is used by classes whose objects may be ordered.
>* The class must define the `<=>` operator, which compares the receiver against another object, returning -1, 0, or +1 depending on whether the receiver is less than, equal to, or greater than the other object.
>* If the other object is not comparable then the <=> operator should return *nil*.
>* Comparable uses `<=>` to implement the conventional comparison operators (`<`, `<=`, `==`, `>=`, and `>`) and the method `between?`

+ I worked on the last `#play`, I passed all the tests and lastly tested the CLI for the app, it works perfectly!

My solution:

```Ruby
def play(board)
  display_board(board)
  until over?(board)
    turn(board)
    break if draw?(board)
  end
  if won?(board)
    puts "Congratulations #{winner(board)}!"
  elsif draw?(board)
    puts "Cat's Game!"
  end
end
```
Learn.co:

```Ruby
def play(board)
  while !over?(board)
    turn(board)
  end
  if won?(board)
    puts "Congratulations #{winner(board)}!"
  elsif draw?(board)
    puts "Cat's Game!"
  end
end
```

>* Most of the method is created with helper methods that I've created perviously.
>* The steps are as following:
>>* After greeting the player the board is displayed then it asks the user for a number between 1-9
>>* Each player(X & O) will have his turn until the game is over.
>>* After each turn the method checks if it is a draw and if that is true it breaks the loop.
>>* If a player wins, a message will be printed to congratulate him/her and if it is a draw; which means the board is full & there is no winner, it prints the message "Cat's Game!"  

>* Learn.co used `while` instead of `until` and they used not operator for the condition so while the game is not over keep running turn method.
>* They didn't check if it is a draw after each turn and break if it is a draw otherwise continue with turn.
>>* I tried this `#play` method instead of mine and I get an infinite loop plus this error message `rspec ./spec/02_play_spec.rb:63 # ./lib/tic_tac_toe.rb #play checks if the gameis draw after every turn`
>>* I believe I will stick with mine!

+ I've seen the word *__stubbing__* today for the 2nd or 3rd time since I've started the prep & prework courses.
>* We can stub the functionality of any method to behave exactly as we would like for this test to function and create the conditions that allow us to specify functionality.
>* This technique of faking or hardcoding the return value and behaviour of a method is called *Mocking* or *Stubbing*.
>* It's a bit of an advanced technique in testing & I don't need to worry about it but it is good to understand what is stubbing for my own knowledge.

###### Friday 24th August
+ I started working on *__Intro to Object Oriented__* and *__Classes & Instances__*. I am working on *__Intro to Classes & Instances__* lesson.

###### Tuesday 28th August
+ I am learning about classes which create new bundles of information regarding individual objects every time a new object is added. Think of a class like the blueprint that defines how to build an object.
>* The class is different from an individual object just as the blueprints that show how to build a house are not the actual house.
>* A Ruby class both contains the instructions for creating new objects and has the ability to create those objects.
>* Calling `.new` on the class name is like getting a brand new object from an assembly line which produces a series of similar objects based on the same class template.

```Ruby
class Dog
  # some code to describe a dog
end
```
>* The `Dog` class is defined with the `class` keyword, followed by the class name and closed with an `end`.
>* The body of this class is between the `class` and `end` keywords.
>* Class names begin with *capital letters* because they are stored in Ruby constants.
>>* If your class name contains two words, the name should be *CamelCased*.

```Ruby
class Dog
end

fido = Dog.new
fido #=> #<Dog:0x007fc52c2d7d20>
```
>* once we've defined our `Dog` class with the `class` keyword, we immediately can bring to life new individual dogs, the variable `fido` which points to a *new instance* of a dog.
>* On the `Dog` class, we call the `.new` method and that will *instantiate* a new dog.
>>* *Instantiate* means bringing a new object to life, a new individual, like a particular dog, like Snoopy or Lassie or Rover.
>>* Each particular dog is an individual that was *instantiated* when we called `Dog.new` to birth it into our world of programming.
>* We call these individuals, each specific dog or version of our class, __instances__.
>>* An instance is a single occurrence of an object.
>>* Instances refer to the individual objects produced from the class.
>* Every time you make an instance of a class, Ruby tells you that the return value is something that looks like `#<Dog:0x007fc52c2cc588>`
>>* This syntax is called __Ruby Object Notation__ and it's just the default way that Ruby communicates to you that you are dealing with an object or instance of a particular class.
>>* The `Dog:0x007fc52c2cc588` tells you that the object is an instance of `Dog` and the `0x007fc52c2cc588` is called its object identifier and it basically means this is *where the object lives inside your computer*.
>>* Each of these instances are totally *unique*, even though they are all born from `Dog`.

Summary:
---
>* Classes are the blueprints that define the behaviour and information our objects will contain.
>* They let us manufacture and instantiate new instances.

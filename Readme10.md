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

+ I worked on *__Classes & Instances Lab__* which contains 2 files in lib directory and each one of them require to add a class definition and then instantiate instances from that class in local variables.

```Ruby
class Person
end

adele_goldberg = Person.new
alan_kay = Person.new
```

+ I've started working on *__Instance methods__* section which contains a lesson & a lab.
>* __The behaviour of objects__
>>* We know that classes act as a factory for our objects, capable of instantiating new instances.
>>* How do we ask the object to do something?
>>* We send objects messages asking them to perform an operation or task through a syntax known as *"Dot Notation"*.

```Ruby
class Dog
end

fido = Dog.new #=> #<Dog:0x007fc52c2cc588>

fido.object_id #=> 70173135795280
```
>* The `#object_id` method simply tells you the object's identifier in your computer's memory (the place where all things live in your computer).
>* In dot notation, we call the __object__ that received the method message the __"receiver"__ and we call the __method__ the __"message"__.

```Ruby
# The receiver is this very string      # reverse is the message
"Strings are instances and objects too".reverse
```
>* One interesting method provided is the `#methods` method that returns an array of all the methods and messages an object responds to.

I thought of objects being like biological cells and/or individual computers on a network, only able to communicate with messages. - *Alan Kay*

>* __Building Your Own Instance methods__
>>* We're used to defining methods already with the `def` keyword. If we place this method definition within the body of a class, that method becomes a specific behaviour of instances of that class, not a generic procedure we can just call whenever we want.
>>* We call the methods defined within the object's class __Instance Methods__ because *they are methods that belong to any instance of the class*.

```Ruby
class Dog
  # Class body

  # Instance Method Definition
  def bark
    puts "Woof!"
  end
end

fido = Dog.new
fido.bark #> "Woof!"
```
>* Objects can only do what we teach them to do via the code we write and the methods we define.
>>* For example, currently, Dogs do not know how to sit.

```Ruby
class Dog
  def bark
    puts "Woof!"
  end
end

fido = Dog.new
fido.bark #> "Woof!"
fido.sit # NoMethodError: undefined method `sit' for #<Dog:0x007fa4e9a9e8a0>
```

>* Instance methods, the methods that belong to particular instances of particular classes, are *not globally evocable* like procedural methods. They cannot be called without an instance.

```Ruby
class Dog
  def bark
    puts "Woof!"
  end
end

fido = Dog.new

# Let's try just calling bark without fido
bark # NameError: undefined local variable or method `bark' for main:Object
```
>* __Classes as Blueprints__
>>* The ability to define methods and behaviours in our classes for our instances makes Ruby classes behave not just as factories, capable of instantiating new individual instances, but also as a *blueprint*, defining what those instances can do.

+ I worked on *__Instance Methods Lab__* where i practised building classes & instances methods.
```Ruby
class Dog
  def bark
    puts "Woof!"
  end
  def sit
    puts "The Dog is sitting"
  end
end
```
+ I am working on *__Object Properties__* section and the 1st lesson is *__Instance Variables__*
>* When we build objects through our own classes we know we can *add behaviour to the objects* through *instance methods*.
>* But how do we give our objects data? How do we give objects attributes or properties?
>>* *Local variable* can only be accessed in a specific, local environment.
>>* A local variable that is defined inside one method, for example, *cannot be accessed by another method*.
>>* In order to get around this limitation, we can use __instance variables__ inside our Ruby classes.
>>* An __instance variable__ is a variable that is accessible in any instance method in a particular instance of a class.

>* Let's say we have a class called `Dog` that is responsible for producing individual dog objects. We want each dog to be able to have a name and show its name.

```Ruby
class Dog
  def name=(dog_name)
    this_dogs_name = dog_name
  end

  def name
    this_dogs_name
  end
end
```
>>* Here we've defined two instance methods, the `name=`, or "name equals" method, and the `name` method.
>>* The first method takes in an argument of a dog's name and *sets* that argument equal to a variable, `this_dogs_name`.
>>* The second method is responsible for *reporting*, or *reading* the name.
>>* The methods act as mechanisms to expose data from inside of the object to the outside world.
>>* Our two methods therefore are responsible for *"setting"* and *"getting"* an individual dog's name.

>* If I add this code and then run the file `ruby dog.rb`

```Ruby
lassie = Dog.new
lassie.name = "Lassie"

lassie.name #=> "Lassie"
```
>>* This should create a new dog instance, give it a name (Lassie) and try to access- or read- its name.
>>* When I run the file I should see an error message `'name': undefined local variable or method 'this_dogs_name'`
>>* Looks like the `#name` method doesn't know about the `this_dogs_name` variable from the `#name=` method.
>>* That is because `this_dogs_name` is a __local variable__. A local variable has a __local scope__. That means that it *cannot* be accessed outside of the method in which it is defined.

#### Instance Variable:
>* We define an instance variable by prefacing the variable name with an `@` symbol.
>* Instance variables are *bound* to an instance of a class. That means that the value held by an instance variable is specific to whatever instance of the class it happens to belong to.
>*  Instance variables *hold information* about an instance, usually an attribute of that instance, and can be called on throughout the class, without needing to be passed into other methods as arguments (as would be the case with local variables).

```Ruby
class Dog
  def name=(dog_name)
    @this_dogs_name = dog_name
  end

  def name
    @this_dogs_name
  end
end

lassie = Dog.new

lassie.name = "Lassie"

puts lassie.name
```
>* Now we will be able to see `Lassie` outputted to my terminal.
>>* Why did it work? Inside the `#name=` method, we set the value of `@this_dogs_name` equal to whatever string is passed in as an argument.
>>* Then, we are able to *call* on that same instance variable in a totally separate method, the `#name` method.

Conclusion
---
>* Using instance variables frequently to pass information around the instance methods of a class.
>* Think of instance variables as the containers for instance-specific information.
>* The ability of instance variables to *store information* and be accessible within different instance methods is one of the things that makes it possible for us to create *similar*, but *unique* objects in object oriented Ruby.

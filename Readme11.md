#### Continue Learning Notes - 9

###### Continue: Tuesday 28th August

>* __The Abstraction of Instance Methods__
>* In Ruby, it is possible to simply set an instance variable with the following method:
```Ruby
kanye.instance_variable_set(:@name, "Yeezy")
```
>* It is also possible to simply retrieve an instance variable from an object with the following method:
```Ruby
kanye.instance_variable_get(:@name)
  => "Yeezy"
```
Since this is the case, __why do we even use instance setter and getter methods?__

>* In fact, there are a number of reasons:
>>* *Syntactic Vinegar* vs. *Syntactic Sugar*
>>>* The first reason is a __stylistic__ one but it is important.
>>>* As object-oriented Rubyists, we care about our program's readability and design.
>>>* The above method is ugly. It places a verb at the end of the method name. The weird grammar of this method should remind us not to use it.
>>>* This technique of purposely naming methods in a hard to use manner is called __syntactic vinegar__.
>>* *Exposing Literal Variables* vs. *Abstracting Attributes*
>>>* The `instance_variable_set` method depends on a literal, concrete variable, `@name`.
>>>* It exposes it directly to the person executing our code. This is bad practice because it forces our program to rely directly on the `@name` variable.
>>* __Why is this so terrible?__
>>>* What if we want our program to store both a first and last name.
>>>* Let's do a quick refactor of our Person class.

```Ruby
class Person

  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  #...

end
```
>* Our program has some added functionality. We could imagine collecting all of our instances of `Person` and sorting them by last name, for example.
>>* Now, any other part of our program that was calling `instance_variable_get(:@name)` is broken!
>>* Additionally, any part of our program that is calling `instance_variable_set(:@name)` isn't taking advantage of our new first name and last name functionality.
>>* Allowing our code to rely on an instance variable directly created a program that is not flexible.
>>* If our program contains multiple occurrences of `instance_variable_get(:@name)` and `instance_variable_set(:@name)`, we would have to hunt down *each* and *every* one and change them to accommodate our shift to using both a first and a last name.
>>* Instead of writing code that depends on instance (or any type of) variables, we *write methods* that contain instance variables.
>>* This is a form of abstraction, whereas the instance variable `@name` is a *literal value*. The literal value reference, the variable `@name`, may change as our application grows and we want our application to seamlessly accommodate that change.

Let's create abstraction: the `#name=` and `#name` setter and getter instance methods:
```Ruby
class Person

  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  def name=(full_name)
    first_name, last_name = full_name.split
    @first_name = first_name
    @last_name = last_name
  end

  def name
    "#{@first_name} #{@last_name}".strip
  end

end
```
>* We can change the content of these methods according to our needs, without needing to hunt down every appearance of them in our program and change them as well, like we would need to do with our `instance_method_set` and `instance_method_get` usages.

---

###### Wednesday 29th August
+ I worked on *__Object Attributes Lab__* where I practice to create classes, methods inside those classes with instance variables to write & read the added attributes.

```Ruby
class Person
  def name=(person_name)
    @name = person_name
  end

  def name
    @name
  end

  def job=(person_job)
    @job = person_job
  end

  def job
    @job
  end
end

# Extra work
ashley = Person.new

ashley.name = "Ashley"
ashley.job = "Web Developer"

puts "Hello, my name is #{ashley.name} and I am a #{ashley.job}."
```
+ I am working on *__Object Lifecycle__*
section where I will be learning about `#initialize` and work on a lab to practice its use.
>* I've learned about creating new instances of a class and sets that object equal to a variable and if we want to give our class attributes we can create a method to write & another one to read that attribute.
>* But for example most dogs are born with a breed, not assigned a breed afterwards.
>>* How can we model the behavior of dogs being born with a breed in our `Dog` class?
>>* `#initialize` method let us assign an individual dog a breed *automatically upon creation*, or *instantiation*.
>>* If we want *each* instance of our class to be created with certain attributes, we must define an `#initialize` method.
>>* An `#initialize` method is a method that is *called automatically* whenever `#new` is used.
>* Let's define our `#initialize` method to contain the functionality of the `#breed=` method, so that a dog instance will get a breed assigned to it right away when it is created, without us having to explicitly use the `#breed=` method.

```Ruby
class Dog
  def initialize(breed)
    @breed = breed
  end

  def breed=(breed)
    @breed = breed
  end

  def breed
    @breed
  end
end
```
Now we can call `#new`

```Ruby
lassie = Dog.new("Collie")

lassie.breed #=> "Collie"
```
>* When `#new` is called with an argument, it will pass that argument (or arguments) to the `#initialize` method and invoke that method. The code in `#initialize` will then run, using any arguments from `#new`.
>* The initialize method is what's called a *callback method*, because it is automatically invoked every time the `#new` method is used to create a new instance of the class.
>* Think of the initialize method as a *constructor method*. A constructor method is invoked upon the creation of an instance of a class and used to help define the instance of that class.
>* Every time you type `Dog.new("some breed")`, a new dog instance is created that has a breed of "some breed".

+ I completed *__Object Initialize Lab__* and here is my code for one of the classes:

```Ruby
class Dog
  def initialize(name, breed="Mutt")
    @name = name
    @breed = breed
  end
end
```
>>* In this class I created an `#initalize` method that accepts 2 arguments, the 2nd one is a default argument which is optional to add a breed and if not it is going to be "Mutt".
>>* Then I stored each of these arguments in its own instance variable.
>>* If I want to extend my code I can create the setter & getter methods so once I have new instances I can read these objects or edit attributes values.

+ I worked on *__Object Models__* lab where I created a class `Dog` with a setter and a getter methods for a dog's name plus bark method.

```Ruby
# Your code goes here!
class Dog

  def name=(name)
    @name = name
  end

  def name
    @name
  end

  def bark
    puts "woof!"
  end

end
```

+ And now I will continue the *__Web developer bootcamp__* on Udemy that I haven't finished yet. I am in *section 18* which is a __Todo List Project__
>* I will be using jQuery, HTML & CSS with some slide animations.

---

###### Thursday 30th August
+ I've started with *__OO Tic Tac Toe__* section in my bootcamp prep and the lesson here shows the difference between __Procedural Programming__ & __Object Oriented Programming__
>* In programming we have data and we have the procedures or instructions for operating on that data.
>>* In __procedural programming__, data and procedures, or instructions, are *two separate* things.
>>* In __object-oriented programming__, we have units of code that contain *both* data and instructions, such that an "object" operates on its own data structure.
>* Here is an example of procedural implementation:

```Ruby
board = Array.new(9, " ") # Creates an array with 9 elements filled with " "

def current_player(board)
  turn_count(board) % 2 == 0 ? "X" : "O"
end

def turn_count(board)
  board.count{|token| token == "X" || token == "O"}
end

def display_board(board)
  puts " #{board[0]} | #{board[1]} | #{board[2]} "
  puts "-----------"
  puts " #{board[3]} | #{board[4]} | #{board[5]} "
  puts "-----------"
  puts " #{board[6]} | #{board[7]} | #{board[8]} "
end
```
>>* Each of our methods must take the board array in as an argument and operate on that array.
>>* Here, our data structure, the board array, is operated on by each method.
>>* The data is separate from the behaviour or operations. In fact, the board array is so separate from the behaviours defined in our method that the *only indication* that our data and our methods are related is the fact that the board array is defined in the same general area as our methods.
>>* We constantly have to pass around the board array to every method. This is tedious and potentially very troublesome as any method can modify that variable and continue passing it around, thus causing errors in our program.

__What's so bad about procedural approach?__
>* We don't want to manage our data through proximity and arguments, we want to teach our objects to manage their own data.
>* What happens if we want to grow our tic tac toe game by adding more data or more behaviours? Our program gets *messy*, fast.
>* The more we add different data and behaviours that are linked only by proximity or via arguments, the more *confusing* and *buggy* our program is likely to be.

>* Here is how we use object oriented programming:

```Ruby
class TicTacToe
  def initialize(board = nil)
    @board = board || Array.new(9, " ")
  end

  def current_player
    turn_count % 2 == 0 ? "X" : "O"
  end

  def turn_count
    @board.count{|token| token == "X" || token == "O"}
  end

  def display_board
    puts " #{@board[0]} | #{@board[1]} | #{@board[2]} "
    puts "-----------"
    puts " #{@board[3]} | #{@board[4]} | #{@board[5]} "
    puts "-----------"
    puts " #{@board[6]} | #{@board[7]} | #{@board[8]} "
  end
end
```

__What's so great about object-oriented approach?__
>* Every method became easier to understand.
>* They no longer require arguments and instead can rely on the *internal state* of the object.
>>* The board array is a property of an instance of the TicTacToe game.
>>* The `@board` instance variable, and the data that is stored in it, is attached to the instance of the game that is playing out at a given point in time.
>>* The *state* of the game, i.e. who is winning, what squares have been filled in, is expressed by the content of the `@board` variable, which itself is a property of the given instance of `TicTacToe`.
>>* The methods of our `TicTacToe` class are also part of an object.
>>* When we called `TicTacToe.new` and create a new instance of the class (and start a new game), that instance, that tic tac toe object, has properties, like the `@board` variable, that describe its state.
>>* That tic tac toe instance will also have methods that allow it to enact behaviours and operate on the data stored in its properties.
>* Our tic tac toe object has the whole package––attributes that contain data describing the state of the object and methods that enact behaviours on that data.
>* Not only our code is now more *organised* and *easier to read* and *understand*, it is also *accommodating* of future growth and change.

#### Moving from Procedural to Object-Oriented
>*  The things you want to look for when refactoring procedural code into object-oriented code are:
>>* Find any data the methods rely on.
>>* Is this data related to the core functionality of our program? If so, think about where this data belongs.
>>>* Should you pass it in as an argument to an `#initialize` method?
>>>* Can the class you are writing create the data structure itself?
>>* Are your methods passing data around as arguments?
>>>* Could this data instead be made into an *instance variable*?
>>* Is there any code that isn't contained in a method?
>>>* Could that code be placed inside a method in your class and therefore become behaviour that belongs to your object?

__Anything that works procedurally can also work in an object-oriented fashion and being able to move between these two styles of programming is crucial.__

+ I worked on *__OO Tic Tac Toe__* lab where I refactored my previous Tic Tac Toe CLI game from procedural code to object-oriented code.

```Ruby
class TicTacToe

  def initialize(board = nil)
    @board = board || Array.new(9, " ")
  end

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

  def display_board
    puts " #{@board[0]} | #{@board[1]} | #{@board[2]} "
    puts "-----------"
    puts " #{@board[3]} | #{@board[4]} | #{@board[5]} "
    puts "-----------"
    puts " #{@board[6]} | #{@board[7]} | #{@board[8]} "
  end

  def input_to_index(user_input)
    user_input.to_i - 1
  end

  def move(index, token)
    @board[index] = token
  end

  def position_taken?(index)
    @board[index] == "X" || @board[index].include?("O")
  end

  def valid_move?(index)
    index.between?(0,8) && !position_taken?(index)
  end

  def turn_count
    @board.count {|cell| cell == "X" || cell == "O"}
  end

  def current_player
    turn_count.even? ? "X" : "O"
  end

  def turn
    puts "Please enter 1-9:"
    user_input = gets.chomp
    index = input_to_index(user_input)
    if valid_move?(index)
      move(index, current_player)
      display_board
    else
      turn
    end
  end

  def won?
    WIN_COMBINATIONS.detect do |win_combination|
      if @board[win_combination[0]] == @board[win_combination[1]] && @board[win_combination[1]] == @board[win_combination[2]] && position_taken?(win_combination[0])
        win_combination
      end
    end
  end

  def full?
    @board.all? {|cell| cell == "X" || cell == "O"}
  end

  def draw?
    full? && !won?
  end

  def over?
    full? || won?
  end

  def winner
    if winner = won?
      @board[winner.first]
    end
  end

  def play
    puts "Welcome to Tic Tac Toe!"
    display_board
    until over?
      turn
      break if draw?
    end
    if won?
      puts "Congratulations #{winner}!"
    elsif draw?
      puts "Cat's Game!"
    end
  end

end
```
And this is in the bin/tictactoe where I instantiated an instance of `TicTacToe` class.

```Ruby
tictactoe = TicTacToe.new

tictactoe.play
```
>* I want to mention few differences between my code & Learn.co:

```Ruby
def full?
  @board.all? {|cell| cell == "X" || cell == "O"}
end

def full?
   @board.all?{|square| square != " " }
 end
```
>>* Instead of doing a comparison for each cell, I can say if cell not equal to empty.

>* A part of `#play` method could be refactored as following:

Learn.co code:

```Ruby
puts winner ? "Congratulations #{winner}!" : "Cat's Game!"
```

Instead of my code:

```Ruby
if won?
  puts "Congratulations #{winner}!"
elsif draw?
  puts "Cat's Game!"
end
```

>>* With this ternary operator I can save around 5 lines of code.

+ Now I am done with *__Ruby Fundamentals__* section in bootcamp prep & finally is an *__interview prep__* section in this course in order to completed it.

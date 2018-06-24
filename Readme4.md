#### Continue Learning Notes - 4

######  Wednesday 20th June
+ I started working on Ruby *Variables & Methods* section and I have already done many of the lessons and labs which were part of the pre-course as well. I commit all my labs to my Github account and pull request to its master repository learn-co-students/prework.

This is my code from dice roll lab:

```Ruby
# Create method `roll` that returns a random number between 1 and 6

def roll
  rand(1..6)
end

# Bonus practice using an array
def roll
  (1..6).to_a.sample
end
```
+ Today I learned about Pry library for the 1st time which is a REPL incapsulated in the program by a line of code  `binding.pry` which will freeze the program and enter in a REPL environment so I can understand what I have done so far in my program and it will just return data before the  `binding.pry` but not after it. It is a more flexible REPL than IRB.

```Ruby
require 'pry'

def prying_into_the_method
	inside_the_method = "We're inside the method"
	puts inside_the_method
	puts "We're about to stop because of pry!"
	binding.pry
	this_variable_hasnt_been_interpreted_yet = "The program froze before it could read me!"
	puts this_variable_hasnt_been_interpreted_yet
end

prying_into_the_method
```
The previous code will freeze at  `binding.pry` line and if we want to check the variable  `inside_the_method` it will return the phrase assigned to it but if we want to check  `this_variable_hasnt_been_interpreted_yet` it will return nil cause the program freezed before this defined variable.

+ I completed the *Variables & Methods* section plus *Simple Math* and *Booleans* sections. The Simple Math lab had some exercises to practise arithmetic operators.

I learned about integers and floats in Ruby so if I have  `9 / 2` I should expect  `4.5` as a result but the program will return  `4` . In order to have a float as a result I should have 2 floats or at least one float in the division example so  `9.0 / 2` or  `9.0 / 2.0` then I will have the  `4.5`. I really enjoyed working on this part.

The *Booleans* section it was mostly a quiz with multiple choices using logical and comparison operators.   

+ I worked on the rest of *jQuery intro* in Web Development Bootcamp on Udemy and then I created a repository on Github with the exercise in this section.

```html
  <div>Div 1</div>
  <div class="highlight">Div 2</div>
  <div id="third">Div 3</div>
  <div class="highlight">Div 4</div>
```
```JavaScript
  $("div").css("background", "purple");
  $(".highlight").css("width", "200px");
  $("#third").css("border", "3px solid orange");
  $("div:first-of-type").css("color", "pink");
```
######  Thursday 21st June
+ I worked on operators and conditionals lab in *Conditionals* section, which introduces ternary operator.

```Ruby
def not_safe?(speed)
	speed > 60 || speed < 40 ? true : false
end
```
I also learned about *statement modifiers* for the first time which allows to put a conditional at the end of a statement.

Learn.co example:

```Ruby
this_year = Time.now.year
puts "Hey, it's 2015!" if this_year == 2015
```
The string will be printed if `this_year == 2015` otherwise it won't be printed.

We can also use `unless`

```Ruby
this_year = Time.now.year
puts "Hey, it's not 2015!" unless this_year == 2015
```
The string will be printed unless `this_year == 2015` then it will stop.

+ I am working on the rest of this section which is a lesson and a quiz then I will start working on *Looping*.

######  Friday 22nd June
+ I started *Looping* section and I worked on `loop` & `times` constructs. This part mostly includes labs which is a great way to practice and understand more my code.

+ I also worked on `while` and `until` looping which isn't the 1st time to learn about them.

######  Saturday 23rd June
+ I am working on just labs for the rest of *Looping* section. I already practised `break` and when to use it and also how to get standard input from user with `gets` and we use another keyword next to it `chomp` which removes the new line we have if we just use `gets` so we use `gets.chomp` and we usually store user input in a variable.

Here is my code:

```Ruby
def levitation_quiz
	#your code here
	loop do
	  puts "What is the spell that enacts levitation?"
	  answer = gets.chomp
	  break if answer == "Wingardium Leviosa"
	end
	puts "You passed the quiz!"
end
```  

+ Today is the first time to learn about `for` looping in Ruby. I have done a lab using it and I worked on a lab which includes all of the looping constructs so I could be able to know the difference between them.  

```Ruby
def loop_iterator(number_of_times)
  phrase = "Welcome to Flatiron School's Web Development Course!"
  counter = 0
  loop do
    puts phrase
    counter += 1
    break if counter == number_of_times
  end
end


def times_iterator(number_of_times)
  phrase = "Welcome to Flatiron School's Web Development Course!"
  number_of_times.times do
    puts phrase
  end
end


def while_iterator(number_of_times)  
  phrase = "Welcome to Flatiron School's Web Development Course!"
  counter = 0
  while counter < number_of_times
    puts phrase
    counter += 1
  end
end


def until_iterator(number_of_times)  
  phrase = "Welcome to Flatiron School's Web Development Course!"
  counter = 0
  until counter == number_of_times
    puts phrase
    counter += 1
  end
end


def for_iterator(number_of_times)
  phrase = "Welcome to Flatiron School's Web Development Course!"
  for number in 1..number_of_times do
    puts phrase
  end
end
```

+ Today is the 1st time to do a countdown with `while` loop and to learn about a new method `sleep`

```Ruby
def countdown(n)
  counter = n
  while counter >= 1
    puts "#{counter} SECOND(S)!"
    counter -= 1
  end
  return "HAPPY NEW YEAR!"
end

def countdown_with_sleep(n)
  counter = n
  while counter >= 1
    puts "#{counter} SECOND(S)!"
    counter -= 1
    sleep 5
  end
  return "HAPPY NEW YEAR!"
end
```
The previous code could be a bit better like not having a variable counter and just do `while n >= 1` so I could remove a line of code which is useless. Also the naming of the argument could be more self explanatory like `seconds_to_midnight` like what Learn.co has in the solution.

+ I learned about stubbing which refers to the fake implementation of a method. Learn.co explanation of stubbing for `puts` and `gets` - we will stub the `puts` method to trick our test suite into thinking the stdout file has received the `puts` method and to trick our test suite into recognising that the `gets` method has been used.

+ I am working on the last lab __Blackjack CLI__ and I passed 11 tests and still have 4 more tests to pass.  

######  Sunday 24th June
+ I started my day working on *__Advanced jQuery__* as part of the Web Developer Bootcamp on Udemy.

I learned about jQuery events and the most common ones are `click()`, `keypress()` and `on()`. The first 2 events take an argument which is usually an anonymous function but the `on()` takes 2 arguments, the 1st one is the type of event and the 2nd is a function.

I also worked on jQuery effects such as `fadeIn()` and it could take 2 arguments, the 1st one duration and the 2nd is a function that will be called when the fadeIn complete. `fadeOut` has the same concept. Also, there is `fadeToggle` takes 2 arguments as well so if the element is fadeOut it will fadeIn when we call the method and vice versa.

There is a 3rd argument could be added as well which is easing (A string indicating which easing function to use for the transition.) and the default is swing.

+ I finished the *__Looping__* section in prework track. I was working yesterday on the same lab, which is __Blackjack CLI__ and still had 4 more tests that I worked on today. I had few struggles:

>* Calling a method which has a conditional statement and here I used a helper method to do a comparison. I didn't know why it is not working until I got through the code with a technical coach on Learn.co and I notice that I am calling the helper method twice with different values so I thought about assigning the helper method to a variable and then use that variable with my `if` statement.

This is my solution:

```Ruby
def hit?(current_card_total)
  # code hit? here
  prompt_user
  user_input = get_user_input
  if user_input == "s"
    current_card_total
  elsif user_input == "h"
    current_card_total += deal_card
  else
    invalid_command
  end
end
```
After I passed the tests I get to check the Learn.co solution and I really liked it because it is more efficient and works really well with the game.

```Ruby
def hit?(card_total)
  prompt_user
  input = get_user_input
  until input == 'h' || input == 's'
    invalid_command
    prompt_user
    input = get_user_input
  end
  if input == 'h'
    card_total += deal_card
  elsif input == 's'
    card_total
  end
end
```
So all the `#invalid_command` return is a string `puts "Please enter a valid command"`
but the program doesn't ask the question again and gets user input so that is why using `Until` loop was an awesome idea.

>* The last method was `#runner` which includes many of the helper methods in the file I just struggled with the order of the code but it makes sense to me once I got an explanation from a coach and I went through the code out loud.

```Ruby
def runner
  # code runner here
  welcome
  cards = initial_round
  until cards > 21
    cards = hit?(cards)
    display_card_total(cards)
  end
  end_game(cards)
end
```

+ I am working on *__Arrays & Iteration__* section in prework track and so far I have learned so much about arrays; how to create, manipulate and retrieve data from arrays.

>* There are 2 ways to create an array; literal constructor `array = []` and Class constructor `array = Array.new`.
>* There are lots of methods to add and remove array elements:
  >>* Add to the end of an array with shovel method; `<<` shovel operator so if we have an array of animals `animals << "tigers"` or `push()` which takes an argument so in here will be `animals.push("tigers")`  
  >>* Add to the beginning of an array with `unshift()` so we will have `animals.unshift("monkeys")`
  >>* Remove from the end of an array with `pop` and Remove from the beginning with `shift` and here we don't need to pass any arguments we don't even need the brackets after the method.
  >>* We can also use `delete` which returns the element or elements with the given value. `animals.delete("monkeys")` now the array will delete that element and if there is another element called monkeys it will delete it as well.
>* We check how many elements in an array with `count` so we do `animals.count`
>* There are some methods to check the array or elements of the array such as `inspect` which returns a string containing a human-readable representation of an object. So `animals.inspect` will return an array of strings.
>* Retrieve items from an array with an index so arrays start with 0 and not 1 like humans counting and always the indexes are less than count by one. We can also check an item index by using `index()` and it will return at which index is the item we passed as an argument. There is `include?()` which returns a boolean if the item is included in the array. At last we can use `first` to retrieve 1st item or `last` to retrieve last item.

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

---

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

---

######  Friday 22nd June
+ I started *Looping* section and I worked on `loop` & `times` constructs. This part mostly includes labs which is a great way to practice and understand more my code.

+ I also worked on `while` and `until` looping which isn't the 1st time to learn about them.

---

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

---

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

---

######  Monday 25th June
+ Today I am working on *__Arrays & Iteration__* section which is mostly got labs. I will try to finish most of it today.

>* I learned about array methods such as `sort` and `reverse` which returns the operation you did on an array but it doesn't alter it (change it permanently) unless using a Ruby convention `!` next to `sort!` and `reverse!`.
>* Other methods like `size` which returns the length of the array and I think I have seen another method `count` that does the same job.

+ I knew the difference between *Looping* and *Iteration* so looping when I tell my program to do something a certain number of times but iteration occurs when I have a collection of data (array for example) and I want to operate on each element in the collection.

>* We can have different ways to iterate over an array such as using `loop` with an `if` statement, do a comparison and if it is false just use `break` keyword.

Learn.co 3 different examples but same result:

```Ruby
basket = ["apple 1","apple 2","apple 3","apple 4","apple 5","apple 6","apple 7","apple 8","apple 9","apple 10"]
```

```Ruby
apples_in_basket = basket.size # Step 1
apples_taken_out = 0 # Step 2

loop do # Step 3
    if apples_taken_out < apples_in_basket
        # Step 4
        puts "Taking out #{basket[apples_taken_out]}"
        apples_taken_out += 1
    else
        # Step 5
        break
    end
end
```
>* I believe we can use `while` and `until` which is a bit more abstract way to do iteration.

```Ruby
apples_in_basket = basket.size # Step 1
apples_taken_out = 0 # Step 2

# Step 3 + 4
while apples_taken_out < apples_in_basket
    puts "Taking out #{basket[apples_taken_out]}"
    apples_taken_out += 1
end
```

>* The most abstract iteration is using `each` so you will have more precise and less code. It doesn't alter the array so you need store the result in a variable if you want to a have an updated version of the original array.

```Ruby
# Step 1,2,3,4,5
basket.each do |apple|
    puts "Taking out #{apple}"
end
```
Here is the lab I worked on to practice `each` method

```Ruby
def square_array(array)
  # your code here
  updated_array = []
  array.each do |x|
    updated_array.push(x ** 2)
  end
  return updated_array
end
```
I figured out that I can do it this way and write less code:

```Ruby
def square_array(array)
  # your code here
  updated_array = []
  array.each {|x| updated_array << x ** 2}
  updated_array
end
```

+ I learned about array manipulation with different methods:
 >* `concat()` which adds the items of an array to another.
 >* `insert(index, item)` which inserts an item to the index we specify.
 >* `uniq` which removes any duplicates in an array.
 >* `flatten` which adds dimensional arrays into just 1 array so for example `array = [1, 2, [3, [4, 5], 6], 7, 8]` when we use this method `array.flatten` it should return `[1, 2, 3, 4, 5, 6, 7, 8]`.
 >* `delete(item)` which deletes the item we specify in the array.
 >* `delete_at(index)` which deletes the item in the array at the index we passed in.

 ---

######  Tuesday 26th June
+ I am practising `each` in different labs and after I pass the lab I check the solution of Learn.co and they are using `map` which takes an item and a block and returns a new array. Also we can use the `!` convention to make the changes to the original array and not returning an updated copy.

+ In the solution for *__Badges and Schedules__* lab I have seen method chaining such as `assign_rooms(attendees).each_with_index.map` so I believe checking other solutions is an awesome thing where I can learn about new ways of solving the problem.

---

######  Wednesday 27th June
+ I worked on just 1 lab,  *__Implementing Primes__* and I really enjoyed the challenge because I didn't really understand at the beginning what is a Prime but I googled it and seen couple of math videos and then started to solve the problem. Maybe my solution isn't the best but it is a good start!

Here is my code:

```Ruby
def prime?(num)
  range = (2..num-1).to_a
  is_prime = true
  range.each do |i|
    if num % i == 0
      is_prime = false
    end
  end
  if num < 2
    is_prime = false
  end
  return is_prime
end
```
It took me a while to solve this lab but I've learned so much.

---

######  Thursday 28th June
+ I worked on the *__Deli Counter__* lab in Ruby prework and I thought it is going to take a while to solve it like it happened in JS but it seemed that I have learned so many things when I solved that lab in JS so I passed the tests in less than I expected which is awesome!

I checked the Learn.co solution and I have many similar code as the platform, maybe just few differences I will share them in here.


```Ruby
# My solution
def line(katz_deli)
  line = []
  if katz_deli.size == 0
    puts "The line is currently empty."
  else
    katz_deli.each_with_index do |person, index|
      line << "#{index + 1}. #{person}"
    end
    puts "The line is currently: #{line.join(" ")}"
  end
end

# Learn.co solution
def line(deli)
  if deli.empty?
    puts "The line is currently empty."
  else
    current_line = "The line is currently:"
    deli.each.with_index(1) do |person, i|
      current_line << " #{i}. #{person}"
    end
    puts current_line
  end
end
```
There is no big difference in the previous lab except I stored each set of `i` and its `person` as a string separately in an array and then used `join` to add them together but Learn.co stored it in a string and the added to the end of the string the `i` and `person`.

```Ruby
# My solution
def now_serving(katz_deli)
  if katz_deli.count == 0
    puts "There is nobody waiting to be served!"
  else
    until katz_deli.count == 0
      puts "Currently serving #{katz_deli.shift}."
      break
    end
  end
end

# Learn.co solution
def now_serving(deli)
  if deli.empty?
    puts "There is nobody waiting to be served!"
  else
    puts "Currently serving #{deli.first}."
    deli.shift
  end
end
```
The `#now_serving` didn't need any looping so I believe I shouldn't used it so I have more clean and less code.

I've seen for the first time `empty?` method which returns true if self contains no elements. It is so useful when I need to check if my array is empty instead of using comparison.

+ I finished the last lab, *__Oxford Comma__* in *__Arrays & Iteration__* section and as usual I checked the solution for Learn.co which was a bit different than mine especially using `insert` method in the `elsif` statement.

Here is the lab code:

```Ruby
# My solution
def oxford_comma(array)
  if array.length == 1
    puts array.join
  elsif array.length == 2
    puts array.join(" and ")
  else
    last = array.pop
    puts "#{array.join(", ")}, and #{last}"
  end
end

# Learn.co solution
def oxford_comma(array)
  if array.length == 2
    return "#{array[0]} and #{array[1]}"
  elsif 2 < array.length
    array[-1].insert(0, "and ")
  end
  array.join(", ")    
end
```
I know there is more than 1 way to solve a problem and I am really glad that Learn.co show their solution after passing the lab.

+ Next is *__Enumerables__* section!

---

######  Friday 29th June
+ Today I am working on *__Enumerables__* and I am learning about the meaning of enumerator and its methods to use with data collections specially on arrays and hashes.

>* Enumerators allow for iterative actions on data structures specially over arrays and hashes.
>* Hashes another type of collection. It stores data in associated pairs like a dictionary stores a collection of words and their definitions.
>* Enumerator methods allow us to iterate over every member of a collection and *do something to each* member of that collection.
>> Advantages:
>>* clean code (not repeating ourselves)
>>* efficient when we don't know how many elements we have in an array or hash and we can always update that collection.
>>* When we have a long list
>* Some of the very common methods that I will be using all the time are:
>>* `each` which I already worked with many times. It returns the original array so if we want to see the block result we need to add `puts` or if we want to return a new array we need to make a new "placeholder" (array or hash) in memory and within the method definition, and then return that new placeholder as the last line of the method.
>>* `collect` & `map` are identical in functionality and are similar to `each` with one distinct difference: a *new array* is returned, *not* the original one.
>>* `select` & `find` are very similar so `select` returns a new collection containing all of the elements in the passed collection in which the block's conditional is `true` but `find` instead returns only the *first* item for which it is `true`.
>>* `delete if` on the other hand will delete from the collection any items that return `true` for a certain condition.
>>* `any?` will return `true` if the code block evaluates to `true` for *any* element in that collection.

Check the following example for `select` and `find`:

```Ruby
cool_nums = [1, 2, 3, 4, 5]

def even_nums(nums)
 nums.select do |x|
   x.even?
 end
end

even_nums(cool_nums)
#=> [2, 4]


def first_even_nums(nums)
  nums.select do |x|
    x.even?
  end
end

even_nums(cool_nums)
#=> 2
```

+ I worked on *__Reverse Each Word__* lab and it required to solve the lab 1st with `each` and then use `collect` but the tests will pass with `collect`. In my solution I created an empty array which I didn't need to unless I was using `each` but with `collect` it will return a new array anyway. Learn.co used chaining methods which made the solution in 1 line.

```Ruby
#My solution
def reverse_each_word(sentence)
  reversed = []
  sentence.split.collect {|word| reversed << word.reverse}
  reversed.join(" ")
end

#Learn.co solution
def reverse_each_word(sentence)
  sentence.split.collect {|word| word.reverse}.join(" ")
end
```

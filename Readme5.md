#### Continue Learning Notes - 4

######  Monday 2nd July
+ I finished the *__Cartoon Collections__* lab and I used `collect`, `map`, `find` and `include?` and `each_with_index` methods.

```Ruby

def roll_call_dwarves(dwarves)
  dwarves.each_with_index do |dwarves, i|
    puts "#{i+1} #{dwarves}"
  end
end

def summon_captain_planet(array)
  array.collect {|item| item.capitalize + "!"}
end

def long_planeteer_calls(array)
  array.map do |item|
    return item.length > 4 ? true : false
  end
end

def find_the_cheese(array)
  cheese_types = ["cheddar", "gouda", "camembert"]
  array.find do |cheese|
    cheese_types.include?(cheese)
  end
```
+ Today I've learned new methods such as `start_with?` which returns true if string starts with one of the prefixes given, and `any?` which passes each element to the given block. The method returns true if the block ever returns a value other than false or nil.

+ `yield` keyword, when used inside the body of a method, will allow you to call that method with a block of code and pass the torch, or yield, to that block. It is what happens under the hood with enumerators like `each` and `collect`.

```Ruby
def yielding
  puts "the program is executing the code inside the method"
  yield
  puts "now we are back in the method"
end
```
and to call it with a block:

```Ruby
yielding { puts "the method has yielded to the block!" }
```
We can use the curly brackets `{}` or the `do..end` to create a block with `yield`. It can also take parameters. If you use `yield` and give it an argument, it will pass that argument to the block and that data will become available to the code in the block.

```Ruby
def yielding_with_arguments(num)
  puts "the program is executing the code inside the method"
  yield(num)
  puts "now we are back in the method"
end
```

```Ruby
yielding_with_arguments(2) {|i| puts i * 2}
```

+ I've learned about Closures: blocks, Procs and Lambdas.

######  Tuesday 3rd July
+ I am practising `yield` and return the original array or return a new array. I am building the functionality of `each` and `collect`.

Here are the exercises:

```Ruby
def my_each(array)
  # code here
  i = 0
  while i < array.length
    yield array[i]
    i += 1
  end
  array
end
```
In the previous method it takes one argument and it loops through the array then we have the `yield` keyword which gives us the flexibility to add some operations and create my own methods such as `each`. Also, it returns the original array.

```Ruby
def my_collect(array)
  new_array = []
  i = 0
  while i < array.length
    new_array << yield(array[i])
    i += 1
  end
  new_array
end
```
`#my_collect` also takes one argument and it loops through the array and it returns a new array by pushing `yield` with array elements.

######  Saturday 7th July
+ Today I am working on the rest of the *__Enumerables__*. I started with a lab to create my own `select` method and then I will start few lessons and a quiz.

```Ruby
def my_select(collection)
  # your code here!
  new_collection = []
  i = 0
  while i < collection.length
    if yield(collection[i])
      new_collection << collection[i]
    end
    i += 1
  end
  new_collection
end
```
+ Refresher notes about variables and scopes:
>* Variables in Ruby don't hold object values such as `str = "Hello"` instead it contains a reference to a string object.
>* Methods create their own scope. By default, any variable from outside a method will be unavailable inside that method. Local variables created inside a method "fall out of scope" once we are outside that method.
>* Methods can take arguments and they act as a gateway into a method body, allowing a variable to be passed into its local scope from the external scope that calls the method.

+ Pass by reference VS. pass by value:
>* When you pass in a variable, you're not passing in a value. You're passing in a reference to an object.
>* Primitive data like integers, floats, fixnums, and symbols require a fixed, small amount of memory.
>* When you pass around an integer, you are passing around the actual value.
>* Objects that can grow and change, like arrays and strings, are never a fixed size.
>* They are instead always accessed by a reference pointer in order to save memory use in a program. Passing around objects means passing around this reference pointer.

+ Mutability: because passing by references allows the object to be of any size, objects like strings and arrays can change; they are said to be "mutable". This means that if you pass such a variable into a method, the method can operate on the value of that variable and change its value while still keeping the reference intact.

```Ruby
def change_the_array(array, string)
  array << string
end

some_words = ["hi", "there"]
change_the_array(some_words, "quizmaster")

puts some_words.inspect
  #=> ["hi", "there", "quizmaster"]
```
+ Different datatypes and their mutability:
>* string, array and hash *pass by reference*.
>* Integers, floats, fixnums and booleans *pass by value*

+ Last lesson in this section explains how `sort` works under the hood.
>* We can compare *strings* with greater than `>` and less than `<` operators. If we compare strings using these operators, the comparison operator will look at the first letter of each string and compare their locations in the alphabet.
>* Letters later in the alphabet are considered greater than letters earlier in the alphabet.
>* The sort method yields to a block with two elements. That block is the comparator, so it should compare the two elements and return `0` if they *are the same*,`-1` if *the first is less than the second*, and `1` if *the first is greater than the second*.

```Ruby
array = [7, 3, 1, 2, 6, 5]

array.sort do |a, b|
  if a == b
    0
  elsif a < b
    -1
  elsif a > b
    1
  end
end

# will start with the first 2 elements and compare them and return the following and it will keep doing that until we have the final result.
#=> [3, 7, 1, 2, 6, 5]
```

+ After understanding how the `sort` method works we can introduce a level of abstraction by using *"spaceship operator"* `<=>` and it is also called __combined comparison operator__
>* returns `0` if the first operand equals the second,
>* returns `-1` if the first operand is less than the second, and
>* returns `1` if the first operand is greater than the second.

+ By default `sort` is case sensitive. It will prioritise strings that are capitalised.

```Ruby
dishes = ["steak", "apple pie", "vegetable soup"]

#sort it by default from least to greatest
dishes.sort
#or
dishes.sort do |a, b|
  a <=> b
end

#=> ["apple pie", "steak", "vegetable soup"]

#To reverse the order to be from greatest to least, we will need the block in order to do that
dishes.sort do |a, b|
  b <=> a
end

#=> ["vegetable soup", "steak", "apple pie"]
```
+ Today I started *__Intro to Hashes__* section where it covers many lessons and labs.
>* I can create a Hash with literal constructor `my_hash = {}` or with Class constructor `my_hash = Hash.new`.
>* Hashes store data in an associated manner. With a hash, we can group our data into the necessary categories.
>* Think of a dictionary or an address book. This allows us to store more complex collections of information than the arrays we've seen so far.
>* Hashes are structured with keys and values. *Each key/value pair makes up one unit in the hash*. The entire collection of key/value pairs, which are comma separated, is enclosed in curly braces `{ }`.
>* Keys in hashes can be any type of data: strings, integers or symbols. They are set equal to their associated values by using the `=>` symbol, known for this use as the *"hash-rocket"* (because it looks like a little rocket shooting off towards the right).

```Ruby
hash = {"key" => "value", "another_key" => "another value"}
```
With hashes we are able to store data in an organised and understandable manner.
>* You can use each key once, otherwise you will overwrite the value if you have an existing key with the same name so you can't have duplicates.
>* Each key/value pair describes a unique attribute or unit of information. A person doesn't have two names, in reality.
>* The data structure we are creating should mirror the real-world entity we are trying to describe. The uniqueness of our hash keys reflects that.
>* __Retrieve data from hashes__ with square brackets, is referred to as *"bracket method"*, and we give the name of the key [key]
>* __Adding keys and values to hashes__ hashes use the *"bracket-equals"* method to add data. The syntax `hash["new_key"] = "New Value"`

Retrieve data:

```Ruby
pets = {"cat" => "Maru", "dog" => "Pluto"}

pets["cat"]
#=> "Maru"
```

Hashes are not numbered lists. The data stored in them is not indexed by number, but instead associated to a unique key. Consequently a hash has no concept of the "end of the list", like an array. So the `<<` method, which tells the array to find the end of the list and add the new item to the next index, can't work on a hash. That is why we use `[]=`

+ I am learning about *symbols* and why they are useful as hash keys because of their immutability. Syntax `:i_am_a_symbol` and a symbol is similar to a string, but with one primary distinction: a *symbol can't be changed*. __Symbols are unique__.
>* *__Strings are mutable__*, meaning that we can manipulate them in various ways by adding, removing, or replacing characters.
>* Every time you create a string, it creates a new object in memory, even if the string text is identical to another one you've already created.
>* Ruby has to store each of them separately because any one of them may change in the future.
>* `object_id` a handle that Ruby uses to track it in memory. It will print different id for each string even if they are exactly the same. `puts "Steve".object_id` will print a different id than `puts "Steve".object_id` and it will do the same even if I test it many times.

```Ruby
name = "Steven"
same_as_name = "Steven"

name.object_id == same_as_name.object_id
  #=> false

# Stored in 2 different locations in memory
```
>* *__Symbols are immutable__* this means that its state can't be modified after it is created and it will always be the same size in memory.

```Ruby
name = :steven
same_as_name = :steven
name.object_id == same_as_name.object_id
  #=> true
```

Keys do not need to be mutable. Since they don't need to be mutable, and since mutable objects like strings take up more space in memory, we use immutable, memory-saving symbols as hash keys.
>* Hashes could be written this way with symbols `flatiron_school = {:instructor => "Isaac Newton"}`
>* In Ruby 1.9, we were introduced with the option of forgoing the hash-rocket `=>` when writing key/value pairs when the key is a symbol so `flatiron_school = {instructor: "Isaac Newton"}`. This way is recommended when using symbols as keys.

+ Hashes I've seen until now each key points to a single value. Hashes are so useful, however, because they can be multi-dimensional, or nested.
>* A key in a hash can point to a value that is a collection of objects, i.e. an array or even another hash.
>* Nested Hashes are likely to encounter them any time you find yourself working with a large collection of information. In particular, you will encounter these data structures when working with data you will pull from APIs.
>* API stands for "Application Programming Interface" and here refers to the way in which organisations, companies and governments will expose their data to the public for use.
>* the data you get back from them will be in the form of a nested hash that can contain information about thousands of records.

One of the most common nested data structures you'll see when working with APIs is an array of hashes.

+ I am practising nested hashes and I have done 2 labs and still working on the rest.

```Ruby
def monopoly_with_fourth_tier
	#copy and past the monopoly hash you build in the previous method. We're going to add stuff to it here!
	monopoly = {
	  :railroads => {
	    pieces: 4,
	    names: {
	      reading_railroad: {"mortgage_value" => "$100"},
	      pennsylvania_railroad: {"mortgage_value" => "$200"},
	      b_and_o_railroad: {"mortgage_value" => "$400"},
	      shortline: {"mortgage_value" => "$800"}
	    },
	    rent_in_dollars: {one_piece_owned: 25, two_pieces_owned: 50, three_pieces_owned: 100, four_pieces_owned: 200}
	  }
	}
end
```
In the previous lab I tried to use the *hash_bracket* and the colon `:` method after the key when using symbols so instead of `:key => "value"` I did `key: "value"`

######  Monday 9th July
+ I worked on a *Simple Nesting* lab where I practised retrieve, update and add data.

Here is one exercise:

```Ruby
def adding_matz
# add the following information to the top level of programmer_hash
# :yukihiro_matsumoto => {
#   :known_for => "Ruby",
#    :languages => ["LISP, C"]
# }

	programmer_hash =
 		{
        :grace_hopper => {
          :known_for => "COBOL",
          :languages => ["COBOL", "FORTRAN"]
        },
        :alan_kay => {
          :known_for => "Object Orientation",
          :languages => ["Smalltalk", "LISP"]
        },
        :dennis_ritchie => {
          :known_for => "Unix",
          :languages => ["C"]
        }
     }

  programmer_hash[:yukihiro_matsumoto] = {known_for: "Ruby", languages: ["LISP", "C"]}

  programmer_hash
end


def dennis_ritchies_language
	programmer_hash =
 		{
        :grace_hopper => {
          :known_for => "COBOL",
          :languages => ["COBOL", "FORTRAN"]
        },
        :alan_kay => {
          :known_for => "Object Orientation",
          :languages => ["Smalltalk", "LISP"]
        },
        :dennis_ritchie => {
          :known_for => "Unix",
          :languages => ["C"]
        }
     }
     # first method to return a string not an array
     programmer_hash[:dennis_ritchie][:languages].first
end
```  
+ Next I will be using `each` to iterate over hashes. Inside the iteration we have access to both the key and the value. We can `puts` out the key and value of a single pair. The return value, however, is always the original hash. `each` returns the original collection on which you are calling the method.

```Ruby
hash = {key1: "value1", key2: "value2"}

hash.each do |key, value|
  puts "#{key}: #{value}"
end
```
```Ruby
key1: value1
key2: value2
 => {:key1=>"value1", :key2=>"value2"}
```
+ `start_with?()` returns true if `str` starts with one of the prefixes given.

```Ruby
# passengers = {
# suite_a: "Amanda Presley",
# suite_b: "Seymour Hoffman",
# suite_c: "Alfred Tennyson",
# suite_d: "Charlie Chaplin",
# suite_e: "Crumpet the Elf"
# }

def select_winner(passengers)
  # add the code snippet here!
  winner = ""
  passengers.each do |suite, name|
    if suite == :suite_a && name.start_with?("A")
      winner = name
    end
  end
  winner
end
```
+ `collect` to iterate over hashes. It is used to collect the values of the hash's keys and/or collect data that we've operated on over the course of an iteration.

+ I worked on another lab *Key for min value* and there was some restrictions to use methods such as `#key`, `#values`, `#min`, `#sort_by`, etc...
The purpose of this lab is to create my own method.

```Ruby
def key_for_min_value(name_hash)
  min_value = 0
  key_for_min = nil
  name_hash.each do |key, value|
    if min_value > value || min_value == 0
      min_value = value
      key_for_min = key
    end
  end
  key_for_min
end
```
I had to grape a pencil and paper to explain to myself the iteration process and how when we call this method it will return the *key for min value*.

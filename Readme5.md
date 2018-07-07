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

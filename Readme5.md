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

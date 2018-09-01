#### Continue Learning Notes - 7

######  Thursday 19th July

+ I continued working on *__HTML5__* and today I've learned about:
>* Embedding audio so the tag is `<audio></audio>` and it takes attribute `src` for location.
>>* Different browser render supports different file types and that is why we provide the browser with `<source>` which is just an opening tag.
>>* Its attributes `src` & `type` - for instance `src="audio.mp3"` & `type="audio/mp3"`
>* Embedding video so the tag is `<video></video>` and its attribute `src`
>>* The same idea as `<audio` and the multiple file types so working with `<source` to add multiple files, each file with its own `<source>`.
>>* Its attributes `src` & `type` so example `src="movie.mp4"` & `type="video/mp4"`.
>* There is a converter for videos, audios, etc..., *miro video converter*. It contains different file types.  

---

######  Monday 23rd July
+ Today I continued the rest of *__Front-End HTML5__* section which contained a code along lab and a lesson full of resources to check.

+ I've learned about semantic containers, google map and practised videos and its different resources such as mp3 & ogv:
>* `<iframe></iframe>` with attributes `src`, `height`, `width` and `style`.
>* `<video></video>` and `source` with its attributes `src` and `type` and in the lab it was `type="video/mp3"` and `type="video/ogg"`
>* `<header></header>` represents a container for introductory content or a set of navigational links.
>* `<nav></nav>` tag defines a set of navigation links, only for major block of navigation links.
>* `<section></section>` is a thematic grouping of content, typically with a heading.
>>* Examples of sections would be chapters, the tabbed pages in a tabbed dialog box, or the numbered sections of a thesis.
>>* A Web site's home page could be split into sections for an introduction, news items, contact information.
>* `<footer></footer>` element represents a footer for its nearest ancestor sectioning content or sectioning root element.
>>* A footer typically contains information about its section such as who wrote it, links to related documents, copyright data, and the like.
>>* Footers don’t necessarily have to appear at the end of a section, though they usually do.
>>* When the footer element contains entire sections, they represent appendices, indexes, long colophons, verbose license agreements, and other such content.
>* `<figure></figure>` specifies self-contained content, like illustrations, diagrams, photos, code listings, etc.
>>* While the content of the `<figure>` element is related to the main flow, its position is independent of the main flow.
>>* If removed it should not affect the flow of the document.
>* `<figcaption></figcaption>` tag defines a caption for a `<figure>` element. It can be placed as the first or last child of the `<figure>` element.

---

######  Tuesday 24th July
+ I worked on *__Keys of Hash__* lab in *__More on Hashes__* section.

This is in spec repo:

```Ruby
let(:animals) { {"sugar glider"=>"Australia","aye-aye"=> "Madagascar","red-footed tortoise"=>"Panama","kangaroo"=> "Australia","tomato frog"=>"Madagascar","koala"=>"Australia"} }
```

Here is my solution:

```Ruby
class Hash
  def keys_of(*arguments)
    # code goes here
    result = []
    self.each do |k, v|
      arguments.map {|value| result << k if value == v}
    end
    result
  end
end
```
Learn.co solution:

```Ruby
class Hash
  def keys_of(*args)
    map {|key, value| args.include?(value) ? key : nil }.compact
  end
end
```
In Learn.co code I didn't know that I can use *map* or any other method inside the instance of a class without joining it to an argument. So the *map* works on `Hash.new` which is our example an hash of animals.

+ I've learned so many things today:
>* *Monkey patching* is the practice of re-opening and modifying pre-existing classes.
>>* It is generally avoided. You don't want to mess with the implementation of the objects and methods native to Ruby. It could get messy, fast.
>* `class` is the blueprint from which individual objects are created. In object-oriented terms, we say that your bicycle is an instance of the class of objects known as bicycles.
>>* To create a class you always start with the keyword *class* followed by the name of the class.
>>* The name of the class should always be in CamelCase.
>>* You terminate a class by using the keyword *end*.
>* `self` is a special variable that points to the object that "owns" the currently executing code. Ruby uses self everywhere:
>>* For instance variables: `@myvar`
>>* For method and constant lookup.
>>* When defining methods, classes and modules.
>>* So in this lab `self` belongs to `Hash.new` class which is a Hash of animals.
>* splat operator `*` has almost endless uses. But the main idea is that whenever you don’t want to specify the number of arguments you have, you would use a splat operator.
>* `compact` I have seen it couple of times before but every time it feels like I see it for the first time. It returns a copy of self with all nil elements removed. Usually it is used with `map` or `collect`.
>* Variables in Ruby Class are *4 types*:
>>* __Local Variables -__  are the variables that are defined in a method. Local variables are not available outside the method. They begin with a lowercase letter or _ .
>>* __Instance Variables -__ are available across methods for any particular instance or object. That means that instance variables change from object to object. They are preceded by the at sign @ followed by the variable name.
>>* __Class Variables -__ are available across different objects. A class variable belongs to the class and is a characteristic of a class. They are preceded by the sign @@ and are followed by the variable name.
>>* __Global Variables -__ Class variables are not available across classes. If you want to have a single variable, which is available across classes, you need to define a global variable. The global variables are always preceded by the dollar sign $.

+ I am working on *__Collections Practice__* lab which is the last lab in *__More on Hashes__* section.
>* It contains 8 methods and I've done 4 of them and still have 4 more to do.

my solution:
```Ruby
def begins_with_r(tools)
  result = nil
  tools.each {|tool| result = tool.start_with?("r")}
  result
end

def contain_a(elements)
  elements.collect do |element|
    element if element.include?("a")
  end.compact
end

def remove_non_strings(elements)
  elements.map {|element| element if element.class == String}.compact
end
```
Learn.co solution for `#begins_with_r` & `remove_non_strings`
```Ruby
def begins_with_r(array)
  flag = true
  array.each do |element|
    flag = false if element[0] != "r"
  end
  flag
end

def remove_non_strings(array)
  container = []
  array.each do |element|
    container << element if element.is_a?(String)
  end
  container
end
```
>* First time to see `is_a?(class)` returns true if class is the class of obj, or if class is one of the superclasses of obj or modules included in obj.

I am pretty sure there are built-in methods that I can use to make my code shorter and cleaner that is why I always check Learn.co solutions after I pass the lab.

I solved the following lab but I am extremely curious to see how Learn.co done it.

```Ruby
def first_wa(elements)
  elements.each_with_index do |element, index|
    if element.class == Symbol
      elements.delete_at(index)
      elements.insert(index, element.to_s)
    end
  end
  elements.collect {|str| str if str.start_with?("wa")}.compact.first
end
```
+ New learning outcomes:
>* `uniq` returns a new array by removing duplicate values in self. If a block is given, it will use the return value of the block for comparison.
>* Using `count` with *array* returns the number of elements.
>>* If an argument is given, counts the number of elements which equal *obj* using ==.
>>* If a block is given, counts the number of elements for which the block returns a true value.

```Ruby
def count_elements(elements)
  new_arr = elements.uniq
  new_arr.collect do |element|
    count = elements.count(element)
    #Here we add a new symbol key (:count) to each existing element with the value of count for each one
    element[:count] = count
    element
  end
end
```
---

###### Wednesday 25th July
+ I worked on the rest of the *__Collections Practice__* lab which is the final lab in this section. Next is *__First Application__* section.

+ I've learned about few methods in the next 3 methods.
>* `merge` returns a new hash containing the contents of other_hash and the contents of hash.
>>* If no block is specified, the value for entries with duplicate keys will be that of other_hash.
>>* Otherwise the value for each duplicate key is determined by calling the block with the key, its value in hash and its value in other_hash.

```Ruby
def merge_data(keys, data)
  result = []
  keys.each do |name|
    data.each do |object|
      object.each do |k, v|
        result << name.merge(v) if k == name[:first_name]
      end
    end
  end
  result
end
```
```Ruby
def find_cool(objects)
  objects.collect do |obj|
    obj[:temperature] == "cool" ? obj : nil
  end.compact
end
```
```Ruby
def organize_schools(schools)
  result = {}
  schools.each do |school, location|
    school_location = location[:location]
    result.has_key?(school_location) ? result[school_location] << school : result[school_location] = [school]
  end
  result
end
```
+ I finished the first project *__Jukebox CLI__* and it was so fun to work on it. I still have an advanced exercise which is a bonus and I will work on it for more practice.
>* `unless` isn't the first time to use but I always get confused how it works.
>>* Executes code if conditional is false.
>>* If the conditional is true, code specified in the else clause is executed.
>* I also used *switch statement* to make the last method work.

Here is my solution:

```Ruby
def list(songs)
  songs.each_with_index {|song, i| puts "#{i+1}. #{song}"}
end

def play(songs)
  puts "Please enter a song name or number:"
  user_song = gets.chomp
  if list(songs).include?(user_song)
    puts "Playing #{user_song}"
  else
    puts "Invalid input, please try again"
  end
end

def run(songs)
  help
  puts "Please enter a command:"
  user_input = gets.chomp
  unless user_input == "exit"
    puts "Please enter a command:"
  else
    case user_input
    when "list"
      list(songs)
    when "play"
      play(songs)
    when "help"
      help
    when "exit"
      exit_jukebox
    end
  end
end
```
Note about bin repo:
>* The executable file in bin is a Ruby file, but the ".rb" extension has been left off.
>>* The ".rb" extension is not mandatory for Ruby files, it is just a nice thing to have for the purposes of identifying the type of the file.
>>* However, it is a convention to leave the file extension off of executable files, which comes from true binary files that contain pure machine code (1's and 0's) rather than human readable source code like Ruby.

Note about Stubbing:
>* I've seen this term before but it is a bit confusing that is why I am going through it again.
>>* Stubbing refers to the fake implementation of a method.
>>* In the context of this test suite, we will stub the `gets` method call that our program relies on to obtain user input and feed it back into the application.
>>* In this way, we can simulate the CLI and effectively test our app.

+ New learnings:
>* *squiggly heredoc* which is `<<~` we can finally multiline strings in a nice manner.
>>* Instead of adding `puts` to each string we can do this:

```Ruby
def help
  help = <<~HELP
    I accept the following commands:
    - help : displays this help message
    - list : displays a list of songs you can play
    - play : lets you choose a song to play
    - exit : exits this program
  HELP
  puts help
end
```
+ Here is the difference between my solution and Learn.co solution:

```Ruby
def play(songs)
  puts "Please enter a song name or number:"
  user_song = gets.chomp
  if list(songs).include?(user_song)
    puts "Playing #{user_song}"
  else
    puts "Invalid input, please try again"
  end
end
```
```Ruby
def play(songs)
  puts "Please enter a song name or number:"
  song_to_play = gets.chomp
  if (1..9).to_a.include?(song_to_play.to_i)
    puts "Playing #{songs[song_to_play.to_i - 1]}"
  elsif songs.include?(song_to_play)
    puts "Playing #{song_to_play}"
  else
    puts "Invalid input, please try again"
  end
end
```
My solution didn't check if the user inserts a number for the song but Learn.co done that.
>* They created an array from a range and then checked if it includes the user input after it is changed to an integer.
>* `#{songs[song_to_play.to_i - 1]}"` this line is to get the user input from the songs array and -1 because index of songs starts from 0 and we have our range array starts from 1 to 9.
>* The rest of the method is the same as my solution.
>* The Learn.co solution is more efficient than mine cause it tests different ways of the user input.

Last method in this lab there are few differences between my solution and Learn.co one:

my solution:

```Ruby
def run(songs)
  help
  puts "Please enter a command:"
  user_input = gets.chomp
  unless user_input == "exit"
    puts "Please enter a command:"
  else
    case user_input
    when "list"
      list(songs)
    when "play"
      play(songs)
    when "help"
      help
    when "exit"
      exit_jukebox
    end
  end
end
```
Learn.co solution:

```Ruby
def run(songs)
  # help

  input = ""
  while input
    puts "Please enter a command:"
    input = gets.downcase.strip
    case input
    when 'list'
      list(songs)
    when 'play'
      list(songs)
      play(songs)
    when 'help'
      help
    when 'exit'
      exit_jukebox
      break
    else
      help
    end
  end
end
```
>* They used `gets.downcase.chomp` instead of `gets.chomp`.
>* They used `while` and I used `unless`
>* They created an empty string and then stored the user input in this string.
>* I didn't know where exactly to use `break` but as I see from Learn.co they used it after the user `exit` the app.
>* I can't seem to use `break` with `unless` and I am not sure the reason behind that!
>* I was just reading right now that break is not defined outside a `for` or `while` loops. That explains it.

My `#run` solution passes all tests but the app isn't working properly in CLI. After debugging with the help of a coach on Learn.co, here is the correct code:

```Ruby
def run(songs)
  user_input = ""
  help
  unless user_input == "exit"
    puts "Please enter a command:"
    user_input = gets.downcase.chomp
    case user_input
    when "list"
      list(songs)
    when "play"
      list(songs)
      play(songs)
    when "help"
      help
    when "exit"
      exit_jukebox
      exit
    else
      help
    end
  end
```

---

###### Thursday 26th July
+ I worked on *__Guessing CLI__* lab and I also extended the app for more practice and more fun!

+ It is an CLI app where the user gets a message to type a number between 1 and 6 if the user gets the correct guess, he/she gets a message you guessed a correct number if not he/she gets the computer guess. And then the user is asked if he wants to play again.

Here is my solution:

```Ruby
def run_guessing_game
  user_input = ""
  random_num = rand(1...6).to_s
  puts "Guess a number between 1 and 6."
  while user_input != "exit"
    user_input = gets.chomp
    case user_input
    when "exit"
      puts "Goodbye!"
      exit
    when random_num
      puts "You guessed the correct number!"
      puts "Do you want to play again?"
      puts "Please type yes or no."
      user_answer = gets.downcase.chomp
      if user_answer == "yes"
        run_guessing_game
      elsif user_answer == "no"
        puts "Goodbye!"
        exit
      else
        puts "Invalid answer, please type a correct answer"
        run_guessing_game
      end
    else
      puts "The computer guessed #{rand(1...6)}."
      puts "Do you want to play again?"
      puts "Please type yes or no."
      user_answer = gets.downcase.chomp
      if user_answer == "yes"
        run_guessing_game
      elsif user_answer == "no"
        puts "Goodbye!"
        exit
      else
        puts "Invalid answer, please type a correct answer"
        run_guessing_game
      end
    end
  end
end
```
Learn.co solution:

```Ruby

def run_guessing_game
  input = ""
  while input
    puts "Guess a number between 1 and 6."
    input = gets.downcase.chomp
    random_number = rand(1..6).to_s
    case input.chomp
    when random_number
      puts "You guessed the correct number!"
    when 'exit'
      puts "Goodbye!"
      break
    else
      puts "The computer guessed #{random_number}."
    end
  end
end
```
I have done some changes in the app as you can see from comparing my code with Learn.co code.

+ I started on the new section *__Advanced Hashes__* which is the last one in *__Intro to Ruby!__* I worked on *__Pigeon Organizer__* and I've learned new things from this lab such as:
>*  Conditional assignment: `||=` operator which checks first, if your value is already set. If it returns nil, it will assign the first value on the right side which doesn't return nil or false.
>>* In our case `result[name] ||= {}` it will check if the value is already set for name and if it is not it will set a hash for it.
>>* And it did the same for the array `result[name][category] ||= []`

Here is my solution:

```Ruby
def nyc_pigeon_organizer(data)
  # write your code here!
  result = {}
  data.each do |category, data_items|
    data_items.each do |attributes, names|
      names.each do |name|
        if result[name] == nil
          result[name] = {}
          result[name][category] = [attributes.to_s]
        elsif result[name][category] == nil
          result[name][category] = [attributes.to_s]
        else
          result[name][category] << attributes.to_s
        end
      end
    end
  end
  result
end
```
In the above solution I am checking if it is nil then I will do something to my code. If name doesn't have a hash then I will insert a hash. If category is nil then I add the category and its value, and if I already have a category and value for it then I push the new value to the array.

Learn.co solution:

```Ruby
# One of Learn.co solutions. I really like it!
def nyc_pigeon_organizer(data)
  result = {}
  data.each do |category, data_items|
    data_items.each do |attributes, names|
      names.each do |name|
        result[name] ||= {}
        result[name][category] ||= []
        result[name][category] << attributes.to_s
      end
    end
  end
  result
end
```
This one is much more simple than mine and all they had to do is to use the `||=` operator.

There is another answer from Learn.co where they used `each_with_object({})` and this is the first time I see this method.
>* I think the only difference here is adding the result variable as an object instead of initialising the variable by itself at the beginning.
```Ruby
def nyc_pigeon_organizer(data)
  data.each_with_object({}) do |(key, h), result|
    h.each do |value, names|
      names.each do |name|
        result[name] ||= {}
        result[name][key] ||= []
        result[name][key] << value.to_s
      end
    end
  end
end
```

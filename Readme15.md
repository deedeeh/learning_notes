#### Continue Learning Notes - 15

###### Continue: Monday 10th September

+ After doing some Ruby, it is time for doing the rest of the *__Command Line__* course on Codeacademy & we will start with *Redirecting Input & Output*.
>* Through redirection you can direct the input and output of a command to and from other files and programs, and chain commands together in a pipeline.
>* __standard input__ =>  abbreviated as `stdin`, is information inputted into the terminal through the keyboard or input device.
>* __standard output__ => abbreviated as `stdout`, is the information outputted after a process is run.
>* __standard error__ => abbreviated as `stderr`, is an error message outputted by a failed process.
>* Redirection reroutes standard input, standard output, and standard error to or from a different location.
>* `echo "Hello"` => command accepts the string "Hello" as *standard input*, and echoes the string "Hello" back to the terminal as *standard output*.
>* `>` => command redirects the standard output to a file.
>>* `echo "Hello" > hello.txt` here `"Hello"` is entered as the standard input.
>>* The standard output `"Hello"` is redirected by `>` to the file hello.txt.
>>* __Note__ that `>` *overwrites* all original content in a file
>>>* `cat oceans.txt > continents.txt` the continents.txt file will be overwritten and you will only see the content of oceans.txt as `stdout` in the continents.txt
>* `cat hello.txt` => The `cat` command outputs the contents of a file to the terminal.
>* `>>` => takes the standard output of the command on the left and appends (adds) it to the file on the right.
>>* `cat file1 >> file2` so here the output data of file1 will have the original contents of file2 with the content of file1 appended to it.
>* `<` => takes the standard input from the file on the right and inputs it into the program on the left.
>* `|` => is a "pipe". The `|` takes the standard output of the command on the left, and pipes it as standard input to the command on the right.
>>* ` cat volcanoes.txt | wc`
>>>* `wc` => stands for "word count"
>>>* Here the output of `cat volcanoes.txt` is the standard input of `wc`. in turn, the `wc` command outputs the number of lines, words, and characters in `volcanoes.txt`, respectively. (17  26  204)
>>* Multiple `|`s can be chained together like `cat volcanoes.txt | wc | cat > islands.txt`  
>>>* Here the standard output of `cat volcanoes.txt` is "piped" to the `wc` command. The standard output of `wc` is then "piped" to `cat`. Finally, the standard output of `cat` is redirected to `islands.txt`.
>* `sort` => takes the standard input and orders it alphabetically for the standard output.
>>* `cat lakes.txt | sort > sorted-lakes.txt`
>>>* Here, the command takes the standard output from `cat lakes.txt` and "pipes" it to `sort`. The standard output of `sort` is redirected to `sorted-lakes.txt`.
>* `uniq` => stands for "unique" and filters out adjacent, duplicate lines in a file.
>>* `uniq deserts.txt`
>>>* Here `uniq deserts.txt` filters out duplicates of "Sahara Desert", because the duplicate of 'Sahara Desert' *directly* follows the previous instance. (next to each others)
>>>* The "Kalahari Desert" duplicates are *not adjacent*, and thus remain. (not near to each others)
>>* `sort deserts.txt | uniq > uniq-deserts.txt`
>>>* A more effective way to call `uniq` is to call `sort` to alphabetize a file, and "pipe" the standard output to `uniq`.
>>>* Here by piping `sort deserts.txt` to `uniq`, all duplicate lines are alphabetized (and thereby made *adjacent*) and filtered out.
>>>* Here we simply send filtered contents to `uniq-deserts.txt`, which you can view with the `cat` command.
>* `grep` => stands for "*global regular expression print*". It searches files for lines that match a *pattern* and returns the results. It is also *case sensitive*.
>>* `grep Mount mountains.txt`
>>>* Here, grep searches for "Mount" in mountains.txt.
>>* ` grep -i Mount mountains.txt`
>>>* enables the command to be *case insensitive*.
>>>* Here, `grep` searches for capital or lowercase strings that match `Mount` in mountains.txt.
>>* `grep -R Arctic /home/ccuser/workspace/geography`
>>>* `grep -R` => searches all files in a directory and outputs *filenames* and *lines* containing matched results. `-R` stands for "recursive".
>>* `grep -Rl Arctic /home/ccuser/workspace/geography`
>>>* `grep -Rl` searches all files in a directory and outputs *only filenames* with matched results.
>* `sed` =>  stands for "stream editor". It accepts standard input and modifies it based on an expression, before displaying it as output data. It is similar to "find and replace".
>>* `sed 's/snow/rain/' forests.txt`
>>>* `s` => stands for "substitution". it is always used when using `sed` for substitution.
>>>* `snow` => the search string, the text to find.
>>>* `rain` => the replacement string, the text to add in place.
>>>* __Importantly__, the above command will only replace the first instance of "snow" on a line.
>>* `sed 's/snow/rain/g' forests.txt`
>>>* `g` => This expression stands for "global"
>>>* Here sed searches `forests.txt` for the word "snow" and replaces it with "rain", *globally*.
>>>* All instances of "snow" on a line will be turned to "rain".

+ I've done couple of projects on codeacademy and a quiz to practise redirecting (I/O). I still have 1 more section left *__Configuring The Environment__* which I find it the hardest of them all! I will work on it probably tomorrow.

---

###### Tuesday 11th September

+ Today I am doing more Ruby, just reading blogs, watching videos and trying different things out. If I encountered a new information I will note it down.
>* Went over methods, hashes, classes & OOP. Nothing really new that I haven't seen before.

+ I might work on *__Configuring The Environment__* in Command Line, even though, I believe it is too advanced materials & I won't be using it regularly or maybe at all. I won't take notes if I work on this section in codeacademy except the extremely useful info that I will use it all the time.
>* I don't want to go into many details but I will briefly share few quick notes.
>* The *environment* refers to the preferences and settings of the current user.
>* `nano` => command line text editor used to configure the environment. We can open a file and add content like greeting `Hello, Dina` to it or create aliases.
>>* You can interact with it only through keyboard (you will have a list of shortcuts at the bottom of the text editor when you access it).
>>* So we do `nano file_name` then a text editor in terminal will open.
>>* There I can add text, save it and then exit nano.
>* To activate the text we do `source file_name` so it won't have to exit the current session and make the command or changes available to it.
>* `~/.bash_profile` => is where environment settings are stored. You can edit this file with nano.
>* `alias` => allows to create keyboard shortcuts for commonly used commands (to make our life easier).
>* *environment variables* => are variables that can be used across commands and programs and hold information about the environment.
>>* `export VARIABLE="Value"` sets and exports an environment variable.
>>* `USER` is the name of the current user.
>>>* `echo $USER` => __Note__ that `$` is always used when returning a variable's value.
>>* `PS1` is the command prompt.
>>* `HOME` is the home directory. It is usually not customized.
>>* `PATH` returns a colon separated list of file paths. It is customized in advanced cases.
>>* `env` returns a list of environment variables.

+ This is the end of the *__Command Line__* course on Codeacademy. I might be doing more of this topic in the next few days on Udemy.

---

###### Wednesday 12th September

+ I am doing more Ruby OOP and I have come across few methods that I've seen many times before but I didn't decide to check it but it is time to do that.
>* `#inject` => The `inject` method in Ruby is most commonly used with arrays, with the enumerable module and with converting array elements into hashes. Here are the possible ways of using it from a [blog post](http://blog.jayfields.com/2008/03/ruby-inject.html) by *Jay Fields*:
>>* __Summing Numbers__ It is the most common example for using inject. You have an array of numbers and you want the sum of those numbers.
```Ruby
[1, 2, 3, 4].inject(0) { |result, element| result + element } # => 10
```
>>>* The block will be executed once for each element contained in the object that inject was called on ([1,2,3,4] in our example).
>>>* The argument passed to inject will be yielded as the first argument to the block, the first time it's executed.
>>>* The second argument yielded to the block will be the first element of the object that we called inject on & etc...
>>>* So, the block will be executed 4 times, once for every element of our array ([1,2,3,4]).
>>>* The return value of the block will be yielded as the result argument the next time the block is executed.
>>>* That's the very long version of how inject works, but you could actually __shortcut__ one of the block executions by *not passing an argument* to inject. The argument to `inject` is optional.
```Ruby
[1, 2, 3, 4].inject { |result, element| result + element } # => 10
```
>>>* The first time the block executes the first argument (result) will be set to the first element of the enumerable (1) and the second argument (element) will be set to the second element of the enumerable (2). Check the above example.
>>>* In this case the block will only need to be executed 3 times, since the first execution will yield both the first and the second element.
>>* __Building a Hash__ you may have an array that contains keys and values as pairs, but it's really just an array of arrays. In that case, `inject` is a nice solution for quickly converting your array of arrays into a hash.

```Ruby
hash = [[:first_name, 'Shane'], [:last_name, 'Harvie']].inject({}) do |result, element|
  result[element.first] = element.last
  result
end

hash # => {:first_name=>"Shane", :last_name=>"Harvie"}
```
>>* As the example shows, start with an empty hash (the argument to inject) and iterate through each element in the array adding the key and value one at a time to the result.

>* __Building an Array__ Enumerable gives you many methods you need for manipulating arrays.
>>* For example, if want all the integers of an array, that are even, as strings, you can do so chaining various methods from Enumerable.
```Ruby
[1, 2, 3, 4, 5, 6].select { |element| element % 2 == 0 }.collect { |element| element.to_s } # => ["2", "4", "6"]
```
>>* Chaining methods of Enumerable is a solution but as the chain gets longer it is better to use `inject`
>>* The `inject` method allows to handle everything needed without having to chain multiple independent methods.
```Ruby
array = [1, 2, 3, 4, 5, 6].inject([]) do |result, element|
  result << element.to_s if element % 2 == 0
  result
end
array # => ["2", "4", "6"]
```
>* A convenient way to use this method is with a symbol for an operation.
```Ruby
[1, 2, 3, 4].inject(:+)
```
>>* returns the sum of everything in the array, or in this example 10

>* `reduce` => It is an alias for `inject` so it does exactly the same job.
>* `max_at` => Returns the object in enum that gives the maximum value from the given block.
If no block is given, an enumerator is returned instead.
>>* max_by {|obj| block } → obj
>>* max_by → an_enumerator
>>* max_by(n) {|obj| block } → obj
>>* max_by(n) → an_enumerator
```Ruby
a = %w(albatross dog horse)
a.max_by { |x| x.length }   #=> "albatross"
```
>>* If the n argument is given, maximum n elements are returned as an array. These n elements are sorted by the value from the given block, in descending order.
```Ruby
a = %w[albatross dog horse]
a.max_by(2) {|x| x.length } #=> ["albatross", "horse"]
```

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

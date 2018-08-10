#### Continue Learning Notes - 8

###### Thursday 9th August
+ I worked on the last lab, *__Zhw Shoes__*, in *__CSS Page Layout__* and this is the end of *__Intro to HTML/CSS __* section.
>* The lab had all of the HTML and almost all CSS styles except positioning of wrapper divs.
>* It was required to have 3 columns grid for the content.
>* I had 2 margins between these columns each was `2.25%` and I did subtract the total of the margins from `100%` then divide it by 3.
>* I used `float` & `width` properties a lot and also `clearfix` & `clear` as classes.
>* It was really great to work on that lab I've learned so much about columns and positioning.
>* I still need to practice more on this area cause sometimes it is confusing to work with `float`, `position`, `clearfix` and `clear`.

Check *__hs-zhw-shoes-layout-prework__* repo for my code in *layout.css* file and I added few ids or classes in the *HTML* file such as `deals`, `no-margin-right` and `details_layout`. Also added `clear` and `clearfix` in divs.

+ My next and last section in this prework course is *__ Advanced BASH & Git__*. I started working on *__BASH__* and it is first lesson *__Understanding PATH__*.
>* As a programmer I have to be really comfortable working on command line to move around my filesystem and apply commands like create, edit, move, delete, etc... and as a mac user I will be using *BASH* to do that.
>* Briefly *BASH* is a command processing program that reads the input you type into your command line and does things with it.
>* This lesson is about *PATH* and that is what I want to have the spotlight on:
>>* When BASH starts, it creates an environment for your shell session by executing commands from a few different scripts. These include `~/.bash_profile`, `~/.bash_login`, and `~/.bash_rc`. Since BASH looks in your `.bash_profile` *first*, you should be setting most of your environment variables and methods there.
>>* `~/.bash_profile` is characterised  by a dollar sign followed by a variable name. Environment variable names consist of all uppercase letters such as `$PATH`
>>>* `$PATH` is a colon-separated list of paths.
>>>* Each path is just the location of a directory (or "folder") on your system.
>>>* When you type a command into your command-line, you are running a program.
>>>* When your computer receives a command to run a program, it will search for that program in the directories listed in your `$PATH` and the directories are checked in order.
>>>* As soon as BASH finds what it’s looking for, it’ll execute the command and stop travelling down the PATH.
>>* The PATH environment variable is like a map that BASH consults every time you tell it do something.
>>* It’s important to remember that BASH will __stop looking__ for a program or script once it finds a match, so the sequence of directories in your PATH is __important__.

>* To check the `$PATH` directories type `echo $PATH` in BASH.
>* I will have a list of filepaths separated by `:` and if I want to have each filepath on a new line I can do `echo $PATH | tr ":" "\n"`
>>* `tr` is a command in Unix-like operating system.
>>>* It's an abbreviation of translate, indicating its operation of replacing or removing specific characters in its input data set.
>>>* The `utility` reads a byte stream from its standard input and writes the result to the standard output.
>>>* It can be used with UNIX pipes `|` to support more complex translation.
>>>* The rest of the command is to replace the colon with new line.
>>* `utility` is a computer software helps to manage, maintain and control computer resources. Operating systems typically contain the necessary tools for this, but separate utility programs can provide improved functionality.
>* To check manually in which file path I have 'ruby' program I can do `ls DIRECTORY_NAME | grep 'ruby'`
>>* This command means list the file/files contain 'ruby' in this directory (DIRECTORY_NAME).
>>* `grep` is a command-line utility for searching plain-text data sets for this lines that match a regular expression.
>>>* It stands for *Global regular expression print*
>>>* Function: search for *PATTERN* in each *FILE* or standard input.
>>* To have the same output as the one we've done manually we can type `which ruby` and the filepath should match.

###### Friday 10th August
+ I am learning about *BASH* commands in *__BASH Review__* lesson.
>* `ls` => lists all folders & files in the current directory.
>* `touch` => to create a file, next to it is the file name and you can create a hidden file by adding a dot at the beginning of the file name.
>* `-al` => This is called flags and you can use it on most Unix commands. If I use it with `ls -al` it means list all folders and files including hidden ones `-a` in a long format `l`.
>* *Flags* => Flags in Unix-like commands are uncountable, Every commands have own and different flags which print different information in different formats.
>* `echo` => printing to the screen.
>* `>>` => redirecting output into a file, for ex. `echo "I'm printing to the screen >> visible"`
>* `cat` => short for *concatenate* and it allows us to create single or multiple files, view contain of file, concatenate files and redirect output in terminal or files. `cat visible` will print in terminal the sentence we redirect it in file visible in the above example.
>* `mv` => rename files so `mv visible something_else` and to print the content of the file we can do `cat something_else`
>* `mv` => is also can be used to move file.
>* `rm` => remove file and we can also use it with hidden files.
>* `mkdir` => make directory so we type the command and next to it the name of the directory.
>* `cd` => change directory and we use it to move around directories.
>* Unix process and how to kill them:
>>* Look for them using `ps aux` and we will pipe those results into grep giving it something to look for `| grep ruby`
>>>* `ps` short for process status and it is used to provide information about the currently running processes, including their process identification numbers (PIDs).
>>>* a = show processes for all users.
>>>* u = display the process's user/owner.
>>>* x = also show processes not attached to a terminal.
>* `kill` plus the PID number next to it to do the same job as `pkill` except it has the process PID number and it will just kill it.
>* `pkill` it looks for a process and it kills it if it finds it, for ex. `pkill ruby` it will look for ruby process and it will kill it.
>* __Executable Shell program:__
>>* *shebang* tells the program loader what command to use to execute the file. So when you run `./myscript.rb`, it actually translates to `/usr/local/bin/ruby -w ./myscript.rb.`
>>* `#!/bin/sh` => is an executable  representing the system shell.
>>* Using `chmod +x FILENAME` on a file (your script) only means, that you'll make it executable.
>>>* `chmod` meaning change mode.
>>>* `+x` meaning adds executable flag to the file.
>* `export` => is a built-in command of the bash shell. It is used to mark a shell variable for export to child processes.

*I still don't really understand the part related to shebang `#!/bin/sh` and run a program using `chmod +x`. Also, to run our program file no matter where we go.
I need to check resources in order to fully understand this part.*

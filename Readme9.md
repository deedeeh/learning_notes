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

#### Continue Learning Notes - 9

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

---

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

---

###### Saturday 11th August
+ I am currently working on *__Git__* section as part of *__Advanced BASH & Git__*. I am doing *__Thinking Ahead: Github as career differentiator__* lesson and I've came up with some notes to check for every project/repo in Github:
>* __Project Structure and Organisation:__
>>* In regards to architecture and design, make sure it easy to figure out where to go in the project to locate the various functional areas and layers.
>>* Use relevant and well known *design patterns/file structure*.
>* __Description & Tags:__
>>* Every project including Flatiron School projects should have a description. Have a small, one-sentence description.
>>* Descriptions should include a few sentences about *functionality*, *languages* and/or *major tools* used. Be concise while explaining what the project is about.
>>* They should also include a *link to a live site* (at one point or another every final project should be hosted).
>>>* If your live site is buggy, make sure to video a demo of yourself using the project before the site comes down.
>>>* Add that instead of a live link.
>>* Make sure descriptions are up-to-date by adding/editing it on projects repo.
>* __ReadMe:__
>>* All projects should have a ReadMe attached (gifs are highly recommended).
>>* It can include wireframes or videos demonstrating app design and/or functionality.
>>>* This differs from a description as it should be *longer*, and about app functionality.
>>* ReadMes can also include *links to live apps* - if Front End and Back End are broken into separate repos, provide a link to the other relevant portion.
>>* If you wrote a *blog post* about your project, *link it* here.
>>* Make sure ReadMes are up-to-date by adding/editing it on projects repo.

#### BONUS Tips
>* __Tests:__
>>* Building out tests is impressive — especially at a junior level.
>>* [Check out this article](https://www.toptal.com/qa/how-to-write-testable-code-and-why-it-matters) for tips on how to write testable code and why it matters.
>* __Comments on Code:__
>>* In a great code base, you’ll see a line about each code before writing the method, giving a description of what it does.
>>* On the next project start adding in comments - this will prepare you for working on a common code base at your future developer gig, and demonstrate to employers that you’re ready to collaborate effectively.

### General Tips for Github:
+ Fill out *ALL* Profile Information
>* Full Name
>* Bio (if nothing else, Full Stack Web Developer)
>* URL (to something! blog, personal portfolio, etc - preferably something with contact info)
>* Email (personal choice)
>* Company
>* Location
>>* Recruiters use search tools and filter out profiles based on location. Having this information on your profile makes it easy for them to find you.
>* Picture (*professional*: think LinkedIn)

+ Pin Projects to the Top of Profile
>* Highlight your most impressive, large and/or recent projects to the top of your GitHub page.
>* Having small projects is okay, but try to make them diverse. Having projects using different languages or technologies will show that you possess a variety of skills.

+ Commit Often
>* Make consistent (daily) contributions to your Github profile.
>* Think *GREEN BOXES!* Your daily activity will show potential employers your level of activity each day, week, month - and commits should be frequent!

+ Contribute to Open Source Projects.
>* This shows that you can work well with a community, you know how to dive into large codebases and can adapt to different coding standards.
>* Having pull requests/issues/reviews visible on your profile makes you stand out.

+ Have Clean, Easy to Read Code on Your GitHub
>* Functions should be responsible for one thing in general.
>* Keep your code modular and DRY (‘Don’t Repeat Yourself’).
>* Keep methods small, and create a chunk you can reuse in different places and stack in different orders.
>* Stay away from ‘copy and paste.

__Your GitHub should communicate that you can build purposeful, meaningful apps and features.__

+ The next lesson is *__Git Todo__* where I will set up an SSH key that will allow to communicate with Github using the SSH protocol.
>* One of the benefits of this is that it will allow to communicate securely with Github without having to type in your password.

+ Also this lesson contains a tutorial for creating the most basic git repository possible and adding it to the online service Github. At the end of this tutorial, you will have 1 copy of your repository on your computer and 1 copy of your repository on Github.
>* Git is a "distributed source control management system".
>* It helps programmers to control and manage changes being made to a collection of files and their contents.
>* It is a critical tool for all software development teams.  
>* It is *"distributed"* in the sense that many copies of a given repository can exist, but each copy can *operate independently* of any other copies.
>>* `mkdir Directory_name` and now we have a new directory(folder).
>>* `cd Directory_name` to change the directory we are in.
>>* To check the present working directory run `pwd`.
>>* To create an empty file in your current directory `touch README.md`
>>* To check the directories or files in the current directory run `ls`.
>>* Now we will start using Git:
>>>* `git init` it initialises the git repository, or in other words, it creates a directory called ".git" which contains some stuff that git needs.
>>>* If you type in `ls` the `.git` file won't appear because it is a hidden file but if I run `ls -a` it shows all files including hidden ones.
>>>* Everything that makes your git repository a git repository is in this directory! This means that if you were to delete the ".git" directory then this directory would no longer be a git repository.
>>>* Now you have to tell git which files you would like to keep track of by `git status` and this says you have a file "not staged" for commit.
>>>* In git, you have to stage the files that you want git to keep track of because it's not always the case that you want to keep track of all the changes you just made and we can do that by `git add README.md`
>>>* Now lets commit the changes by `git commit -m "Initial commit"`. Once you do so, the new README.md file will be in your git repository.
>>>>* `commit` => Commits are the building blocks of a git repository.They represent a set of changes made to the contents of the repository.
>>>>* `-m` => the -m option to commit indicates that you are providing a message to go along with this particular commit.
>* Github is an online service that augments the experience of using git.
>>* Go to repositories on your Github account then click the green button *New* on the right hand side.
>>* Insert the name of the repo and select the *private* option. __DO NOT__ check the box that says "initialise this repository with a README". Then "Create repository".
>>* You will be taken to the "git-todo" repository page and be shown the view for a repository with no content.
>>>*  This is because our new Github repository doesn't know about the commits on our computer yet!
>>* We have an *existing repository on our computer*, so paste the 2 lines in that section in to your terminal within the "git-todo" repository directory.
>>>* Make sure to toggle the SSH tab and copy that and paste it like that `git remote add origin git@github.com:username/git-todo.git`
>>>>* Tells your git repository where on the internet your Github repository lives.
>>>* Then `git push -u origin master`
>>>>* Instructs your git repository to send it's commits to the Github repository!

---

###### Sunday 12th August
+ I am working on *__Git Flow__* lab where I will practice working with Git and Github.
>* `git branch` => to check on which branch I am in.
>* `git branch NEW-BRANCH` => to add a new branch.
>*  `git checkout NEW-BRANCH` => to switch to that branch.
>* Now you can add/edit my code then I will merge it with master branch if I am satisfied about my code.
>>* `git checkout master` => to switch to master.
>>* `git merge NEW-BRANCH` => to merge those changes to master branch.
>>*  `git push origin master` => update to master branch on my remote repo.
>>* To check if this push worked,  visit my fork of this repo on Github.
>* After merging to master and pushing this remotely I can now delete my branch if I don't need it anymore by `git branch -d NEW-BRANCH`
>* I can then check if this was successfully deleted by `git branch`

---

###### Monday 13th August
+ I am working on how to create a merge conflict and how to fix those conflicts in order to be able to stage, commit and merge my work.
>* I can have 2 branches and then merge one of them to the other. If both have same content I will get a message "Automatic merge failed; fix conflicts and then commit the result."
>* I will have to check which file have the conflicts by `git status` then I will open that file and fix that.
>* Then delete the arrows, HEAD and ===

```HTML5
<<<<<<< HEAD
HTML for polar bear
=======
HTML for walrus
>>>>>>> add-walrus
```
>* After fixing the file I will `git add` then `git commit` those changes.
>* To check my *unmerged paths* I will type `git status` then I can merge it by `git merge BRANCH_NAME`

---

###### Tuesday 14th August
+ I have a problem with IDE, I can't work on *__Git Flow__* lab because IDE is always disconnecting but my internet connection is working good with everything else from youtube to online movies! I posted a question on Learn.co about this and still waiting for an answer.

+ I am working now on *__Git Review__* lesson until the IDE problem is fixed.
>* `git pull origin master` => is to download all the files and directories locally from remote repo.
>* `git commit -am file-name` => is when I want to add and commit with 1 command line.
>* `git branch -v` => to see the last commit on each branch.
>* `git branch --merged` => to see which branches are already merged into the branch you’re on.
>* `git branch --no-merged` => to see all the branches that contain work you haven’t yet merged in.
>* `echo "I'm steven" >> steven` => it means print "I'm steven" in steven file.
>* `git diff` => what changes exactly in the file are made.
>* `git reset` => reset current HEAD to the specified state.
>>* `--hard` => resets the index and working tree. Any changes to tracked files in the working tree since <commit> are discarded.
>>* `--keep` => resets index entries and updates files in the working tree that are different between <commit> and HEAD. If a file that is different between <commit> and HEAD has local changes, reset is aborted.
>* The rest of the lesson is reviewing `mkdir folder-name`, `touch file-name`, `git init`, `git status`, `git add .`, `git commit -m file-name`, `git branch`, `git branch branch-name`, `git checkout branch-name`, `git merge file-name`, `git push`, `git push origin master` and there are many others but those are the common ones.

+ I worked back on bootcamp prep track that I've left to start *__Web Development Fundamentals__* prework which I must complete before starting my bootcamp in Sept. I am doing that now until I have this IDE disconnected issue solved then I can do my 2 Git labs. I am planning to finish bootcamp prep as well before starting in Sept.

+ I completed under *__Iteration__* section in *__Ruby Fundamentals__* a lab called *__Tic Tac Toe Current Player__* where I worked with `each` to iterate over the board as my given argument and I also practiced modulo operator and learned about `even?` & `odd?` which does the same job as modulo.

my solution:

```Ruby
def turn_count(board)
  counter = 0
  board.each do |element|
    if element.include?("X") || element.include?("O")
      counter += 1
    end
  end
  counter
end

def current_player(board)
  turn_count(board).even? ? "X" : "O"
end
```
Both methods on Learn.co were the same as mine except a commented method that used `#count`.
>* `count → int` => returns the number of elements.
```Ruby
ary = [1, 2, 4, 2]
ary.count                  #=> 4
```
>* `count(obj) → int` => if an argument is given, counts the number of elements which equal obj using ==.
```Ruby
ary.count(2)               #=> 2
```
>* `count { |item| block } → int` => if a block is given, counts the number of elements for which the block returns a true value.
```Ruby
ary.count { |x| x%2 == 0 } #=> 3
```
>>* The bellow method was given a block to count the tokens if it "X" or "O".
>>* It is shorter and cleaner than my method.

```Ruby
def turn_count(board)
  board.count{|token| token == "X" || token == "O"}
end
```

---

###### Wednesday 15th August
+ I finally worked on *__Git Flow__* lab after having a bad connection. I've learned so many about git and Github especially with the quiz they had in the spec folder. I am going to review some of the git commands:
>* Different `push` commands:
>>* `git push origin master` => From the master branch, pushing the master branch to the remote master branch where the remote is called 'origin'
>>* `git push origin add-links` => From the feature branch 'add-links', the syntax for creating a remote add-links branch with all of the local branch's content.(remote is still called 'origin')"
>>* `git push upstream master` => From the master branch, the syntax for pushing the master branch to the remote master branch where the remote is called 'upstream'
>>* `git push upstream add-image` => From the feature branch 'add-image', the syntax for creating a remot add-image branch with all of the local branch's content. (remote is still called 'upstream')"
>* Different `fetching` commands:
>>* `git fetch --all` => to update all branches from all remotes
>>* `git fetch upstream master` => to update the local master branch with the master branch on the remote 'upstream'
>* Different `pulling` commands
>>* _`git pull`_ the same as running `git fetch` followed by `git merge`.
>>* `git pull origin add-img` => From the add-img branch, to fetch and merge all the changes from the add-img branch on the remote 'origin'
>* Different `branching` commands:
>>* `git checkout -b add-nav-bar` => one line syntax for creating and switching to a branch called 'add-nav-bar'
>* Different `deleting` commands:
>>* `git branch -d add-link` => From master, the syntax for deleting a local branch called 'add-link'.
>>* `git push origin :add-avatar` => the syntax for deleting a branch called 'add-avatar' on the remote 'origin' using the push and colon syntax.
>* It is best practice to add a feature on the master branch. __false__
>* Merge conflicts are bad and always mean that you did something wrong. __false__

+ I completed *__Git Merge Conflicts__* lab and that is the end of this section *__Advanced BASH & Git__*
>* When I am on master branch and run `git merge BRANCH_NAME` I sometimes get a message in terminal if this merge is necessary and I need to write a commit message.
>>* It's not a Git error message, it's the editor as git uses your default editor. To solve this:
>>>* press "i"
>>>* write your merge message
>>>* press "esc"
>>>* write ":wq"
>>>* then press enter
>>* I will have a printout message in terminal 'Merge made by the 'recursive' strategy.'
>* To fetch remote branches I can run the following command:
>>* `git checkout -t origin/BRANCH-NAME` this creates a new branch on my computer that matches the BRANCH_NAME branch on GitHub.

---

###### Thursday 16th August
+ After finishing the *__Web Development Fundamentals__* prework I am going to work on the rest of *__Bootcamp prep__* on Learn.co and the web developer bootcamp on Udemy. I am not going to take notes of everything except things that I always forget about or new things.

+ I worked on *__Intro to Ruby Iterators__* lesson and next is *__Tic Tac Toe__* section.

+ I completed *__Nested Arrays__* lesson where I practised a bit multidimensional arrays.

+ I worked on *__Boolean Enumerables__* where I've learned more about true/false return values and some of the methods to use.
>* `#all?` => Passes each element of the collection to the given block. The method returns *true* if the block *never* returns *false or nil*. If the block is not given, Ruby adds an implicit block of { |obj| obj } which will cause all? to return true when none of the collection members are false or nil.
>>* Imagine wanting to know if all the numbers in an array are odd.
```Ruby
all_odd = true
[1,2,3].each do |number|
  if number.even? # Will evaluate to false for 1, true for 2, false for 3
    all_odd = false
  end
end
all_odd #=> false
```
>>* Instead of `each` we can use `all?` method like this:
```Ruby
all_odd = [1,2,3].all? do |number|
  number.odd? # Will evaluate to true for 1, false for 2, true for 3
end #=> false
all_odd #=> false
```
>* `#none?` => Passes each element of the collection to the given block. The method returns *true* if the block *never* returns *true for all elements*. If the block is not given, none? will return true only if none of the collection members is true.
>>* Imagine it is the opposite of `all?`
>>* It means we are interested in none of the elements in a collection producing a true expression within the block passed to `#none?`
```Ruby
[1,3].none?{|i| i.even?} #=> true
```
>>* If we compare it with `each`
```Ruby
none_even = true
[1,3].each do |i|
  if i.even?
    none_even = false
  end
end #=> [1,3] because `#each` always returns the original collection
none_even #=> true
```
>* `#any?` => This enumerator will return true if at least one iteration of the block evaluates to true, but false if none of them do.
>>* Sometimes you want to be a bit more forgiving than `#all?` or `#none?` and just ensure that *at least one element* in a collection will create a *true* expression within the block passed.
```Ruby
[1,2,100].any?{|i| i > 99} #=> true
```
>* `#include?()` => It is helpful if you'd like to merely compare actual contents of a known value.
>>*  It will return *true* if the given object *exists* in the element. If it *doesn't find a match*, it will return *false*.
```Ruby
the_numbers = [4,8,15,16,23,42]
the_numbers.include?(42)   #=> true
the_numbers.include?(6)   #=> false
```
+ I am working on *__Search Enumerables__* lesson and I've learned so much from it same as the previous lesson.
>* *Overview* for why we need the methods I am learning now.
>>* When we iterate or enumerate over a collection with `#each`, the return value is always the original collection.
>>* Often we want to search for elements in a collection based on a condition. Imagine wanting to find all even numbers in a collection of numbers using `#each`.
```Ruby
matches = []
[1,2,3,4,5].each do |i|
  matches << i if i.even? # add i to the matches array if it is even
end #=> [1,2,3,4,5]
matches #=> [2,4]
```
>>>* We have to hang on to the matches within the local array matches. Programmers use the phrase __maintain state__ to refer to this task.
>>>>* Cars can be in a state like "Reverse, Drive, Neutral".
>>>>* Our matches array has states of "Empty, [2], [2,4]".
>>>* Our block is complicated with conditional logic that can be implicit with a better enumerator.
>>>* Our code lacks intention and clear semantics.
>* `#select` => the return value will be a new array containing all the elements of the collection that cause the block passed to `select` to return true.
>>* That means for each iteration, if the block evaluates to true, the element yielded to that iteration will be kept in the return value array.
```Ruby
[1,2,3,4,5].select do |number|
  number.even?
end #=> [2,4]
```
>>* check the clarity and expressiveness of this syntax in the short block from below.
```Ruby
[1,2,3,4,5].select{|i| i.odd?} #=> [1,3,5]
[1,2,3].select{|i| i.is_a?(String)} #=> []
```
>>* Notice that if no element makes the block evaluate to true, an empty array is returned.

>* `#detect`/`#find` => are two names for the same method. Those enumerators will only return the first element that makes the block true.
```Ruby
[1,2,3].detect{|i| i.odd?} #=> 1
[1,2,3].find{|i| i.odd?} #=> 1
[1,2,3,4].detect{|i| i.is_a?(String)} #=> nil
```
>>* As you can see, even though both 1 and 3 would cause the block to evaluate to true, because 1 is first in the array, it alone is returned.
>>* Notice also that `#detect` will always return a *single object* where `#select` will always return an *array*.

>* `#reject` =>  It will return an array with the elements for which the block is *false*.
```Ruby
[1,2].reject{|i| i.even?} #=> [1]
```

`#select`, `#detect` & `#reject` are part of a family of *search and filter type enumerators* whose purpose is to help you refine a collection to only matching elements.

They are way easier to manage than using lower-level methods like `#each` and create *meaningful return values* based on expressions in a block.

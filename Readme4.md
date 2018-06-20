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

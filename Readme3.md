#### Continue Learning Notes - 3

###### Friday 1st June
+ Today I am working on *Methods* in Ruby and I am learning about TDD and Rspec and how testing makes your code flexible and helps to write code that is robust.

Here are few lines of the codes for Rspec:
```Ruby
require_relative '../current_age_for_birth_year.rb'

describe "current_age_for_birth_year method" do
it "returns the age of a person based on the year of birth" do
    age_of_person = current_age_for_birth_year(1984)

    expect(age_of_person).to eq(19)
  end
end
```
And here is to pass the tests:

```Ruby
def
  current_age_for_birth_year(birth_year);
  2003 - birth_year
end
```

###### Sunday 3rd June
+ I worked on the rest of Ruby *Methods* section and I leaned about default arguments and required arguments. I also learned how to use array elements with string interpolation instead of having the data stored in variables especially when it is a list of data.

Here are few lines of my codes:

```Ruby
def display_board(board)
  puts " #{board[0]} | #{board[1]} | #{board[2]} "
  puts "-----------"
  puts " #{board[3]} | #{board[4]} | #{board[5]} "
  puts "-----------"
  puts " #{board[6]} | #{board[7]} | #{board[8]} "
end
```
I also worked on 2 tests in Rspec.

```Ruby
board = ["O", "O", "O", "O", "O", "O", "O", "O", "O"]

    output = capture_puts{ display_board(board) }
    rows = output.split("\n")

    expect(rows[0]).to eq(" O | O | O ")
    expect(rows[1]).to eq("-----------")
    expect(rows[2]).to eq(" O | O | O ")
    expect(rows[3]).to eq("-----------")
    expect(rows[4]).to eq(" O | O | O ")
```

###### Monday 4th June
+ I started to work on *Color Game Project* in the web developer bootcamp on Udemy and it is been great so far! I am going to add this project on Github.

```HTML
<body>
  <h1>The Great <span id="colorDisplay">RGB</span> Color Game</h1>

  <div>
    <span id="message"></span>
  </div>
  <div id="container">
    <div class="square"></div>
    <div class="square"></div>
    <div class="square"></div>
    <div class="square"></div>
    <div class="square"></div>
    <div class="square"></div>
  </div>
  <script type="text/javascript" src="colorGame.js"></script>
</body>
```
```javascript
for(let i = 0; i < squares.length; i++) {
 //add initial colors to squares
 squares[i].style.backgroundColor = colors[i];

 //add event listeners to squares
 squares[i].addEventListener("click", function() {
   //grab color of clicked square
   var clickedColor = this.style.backgroundColor;
   //compare color to pickedColor
   if(clickedColor === pickedColor) {
     messageDisplay.textContent = "Correct!";
     changeColors(clickedColor);
   } else {
     this.style.backgroundColor = "#232323";
     messageDisplay.textContent = "Try again!";
   }
 });
}
```

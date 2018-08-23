#### Continue Learning Notes - 9

###### Monday 20th August
+ I worked on *__Tic Tac Toe Game Status__* lab where I practised boolean & search enumerables such as `detect` & `all?` plus I used logical operators; `&&`, `||` and not operator `!`.

Here is my solution:

```Ruby
# this is all the possible winning combinations for tic tac toe
WIN_COMBINATIONS = [
  [0,1,2],
  [3,4,5],
  [6,7,8],
  [0,3,6],
  [1,4,7],
  [2,5,8],
  [0,4,8],
  [2,4,6]
  ]

# It returns the winning combination if it is true otherwise returns false.
def won?(board)
  WIN_COMBINATIONS.detect do |win_combination|
    if board[win_combination[0]] == board[win_combination[1]] && board[win_combination[1]] == board[win_combination[2]] && position_taken?(board, win_combination[0])
      win_combination
    end
  end
end

board.all? {|move| move == "X" || move == "O"}
end

def draw?(board)
  full?(board) && !won?(board)
end

def over?(board)
  draw?(board) || won?(board)
end

def winner(board)
  if won?(board)
    board[won?(board).first]
  end
end
```
>* `#first` => returns the first element, or the first n elements, of the array. If the array is empty, the first form returns nil, and the second form returns an empty array.

I checked Learn.co solution and it almost the same as mine.

###### Thursday 23rd August
+ I am working on *__TicTacToe.rb__* lab which is the last lab in *__Tic Tac Toe__* section.

+ I finished lots of methods but still have 1 more to do `#play` which is the main one for the CLI application.

```Ruby
def input_to_index(user_input)
  user_input.to_i - 1
end

def move(board, position, token)
  board[position] = token
end

def position_taken?(board, position)
  board[position].include?("X") || board[position].include?("O")
end

def valid_move?(board, position)
  position.between?(0,8) && !position_taken?(board, position)
end

def turn_count(board)
  count = 0
  board.each {|cell| count += 1 if cell == "X" || cell == "O"}
  count
end

def current_player(board)
  count = turn_count(board)
  count.even? ? "X" : "O"
end

def turn(board)
  puts "Please enter 1-9:"
  user_input = gets.chomp
  index = input_to_index(user_input)
  if valid_move?(board, index)
    move(board, index, current_player(board))
    display_board(board)
  else
    turn(board)
  end
end

def won?(board)
  WIN_COMBINATIONS.detect do |win_combination|
    if board[win_combination[0]] == board[win_combination[1]] && board[win_combination[1]] == board[win_combination[2]] && position_taken?(board, win_combination[0])
      win_combination
    end
  end
end

def full?(board)
  board.all? {|cell| cell == "X" || cell == "O"}
end

def draw?(board)
  full?(board) && !won?(board)
end

def over?(board)
  full?(board) || won?(board)
end

def winner(board)
  if win = won?(board)
    board[win.first]
  end
end
```
+ I've learned about `between?(min, max)` which is a *comparable* and we use it to check if a value is between a range.
```Ruby
3.between?(1, 5)               #=> true
6.between?(1, 5)               #=> false
'cat'.between?('ant', 'dog')   #=> true
'gnu'.between?('ant', 'dog')   #=> false
```

Comparable:
---
>* The Comparable *mixin* is used by classes whose objects may be ordered.
>* The class must define the `<=>` operator, which compares the receiver against another object, returning -1, 0, or +1 depending on whether the receiver is less than, equal to, or greater than the other object.
>* If the other object is not comparable then the <=> operator should return *nil*.
>* Comparable uses `<=>` to implement the conventional comparison operators (`<`, `<=`, `==`, `>=`, and `>`) and the method `between?`

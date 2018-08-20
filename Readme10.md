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

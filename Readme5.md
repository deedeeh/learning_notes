#### Continue Learning Notes - 4

######  Monday 2nd June
+ I finished the *__Cartoon Collections__* lab and I used `collect`, `map`, `find` and `include?` and `each_with_index` methods.

```Ruby

def roll_call_dwarves(dwarves)
  dwarves.each_with_index do |dwarves, i|
    puts "#{i+1} #{dwarves}"
  end
end

def summon_captain_planet(array)
  array.collect {|item| item.capitalize + "!"}
end

def long_planeteer_calls(array)
  array.map do |item|
    return item.length > 4 ? true : false
  end
end

def find_the_cheese(array)
  cheese_types = ["cheddar", "gouda", "camembert"]
  array.find do |cheese|
    cheese_types.include?(cheese)
  end

```

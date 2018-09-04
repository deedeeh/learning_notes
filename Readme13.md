#### Continue Learning Notes - 13

###### Continue: Tuesday 4th September

+ I've started reading a blog post [The Ultimate Guide to Blocks, Procs & Lambdas](https://www.rubyguides.com/2016/02/ruby-procs-and-lambdas/) by *Jesus Castello* and here what I've learned:

>* __Lambdas VS Procs__
>* Procs & lambdas are a very similar concept, one of the differences is how you *create* them.
>* Another difference between `procs` and `lambdas` is how they *react* to a `return` statement.
>* __Lambda__ => is commonly referred to as an anonymous function. It is an instance of the `Proc` class (you can check that by `lambda.class` on your irb)
>>* The syntax for defining a lambda looks like this
```ruby
say_something = -> { puts "This is a lambda" }
```
>>* You can also use the alternative syntax: `lambda` instead of `->`.
>>* Defining a lambda won’t run the code inside it, just like defining a method won’t run the method, you need to use the `call` method for that.
```Ruby
say_something = -> { puts "This is a lambda" }
say_something.call # "This is a lambda"
```
>>* There are other ways to `call` a lambda such as `my_lambda.()`, `my_lambda[]` and `my_lambda.===`
>>>* it’s good to know they exist, however, it's better to stick with `call` for clarity.
>>*  Lambdas can also take arguments.
```Ruby
times_two = ->(x) { x * 2 }
times_two.call(10) #20
```
>>>* If you pass the wrong number of arguments to a `lambda`, it will raise an exception, just like a regular method.
>* __Procs__ => is short for procedure, which is a set of instructions packaged as a unit to perform a specific task. It is an object.
>>* They are usually made to be called multiple times and from multiple times in a program.
```Ruby
t = Proc.new { |x,y| puts "I don't care about arguments!" }
t.call       # "I don't care about arguments!"
```
>* A `lambda` will return normally, like a regular method. But a `proc` will try to `return` from the current context.

```Ruby
# Should work
my_lambda = -> { return 1 }
puts "Lambda result: #{my_lambda.call}"
# Should raise exception LocalJumpError
my_proc = Proc.new { return 1 }
puts "Proc result: #{my_proc.call}"
```
>>* The reason is that you can’t `return` from the *top-level context*.
>>* BUT if the `proc` was inside a method then calling `return` would be equivalent to returning from that method.

This is demonstrated in the following example:
```Ruby
def call_proc
  puts "Before proc"
  my_proc = Proc.new { return 2 }
  my_proc.call
  puts "After proc"
end
p call_proc
# Prints "Before proc" & return 2 but doesn't print "After proc"
```
##### Summary of how `procs` & `lambdas` are different:
>* Lambdas are defined with `-> {}` or `lambda {}` and procs with `Proc.new {}`.
>* Procs return from the *current method*, while lambdas return from the *lambda itself*.
>* Procs *don’t* care about the correct number of arguments, while lambdas will *raise* an exception.

We can see that `lambdas` are a lot closer to a regular method than `procs` are.

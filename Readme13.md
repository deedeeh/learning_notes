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

Ruby procs & lambdas also have another special attribute. When you create a Ruby proc, it *captures the current execution scope* with it. This concept is called *closure*.
>* __Closure__ => it means that a `proc` will *carry* with it values like local variables and methods from the *context* where it was defined.
>>* They don’t carry the actual values, but a *reference* to them, so if the variables change after the proc is created, the proc will always have the latest version.

```Ruby
def call_proc(my_proc)
  count = 500
  my_proc.call
end
count   = 1
my_proc = Proc.new { puts count }
p call_proc(my_proc) # What does this print?
```
>>* because of the ‘closure’ effect this will print `1` and NOT `500`
>>* This happens because the proc is using the value of `count` from the place where the proc was *defined*, and that’s *outside of the method* definition.

##### Where do Ruby procs & lambdas store this scope information?
>* When you create a `Binding` object via the `binding` method, you are creating an *‘anchor’* to this point in the code.
>>* Every variable, method & class defined at this point will be *available later* via this object, even if you are in a completely different scope.
>>* In other words, executing something under the context of a `binding` object is the same as if that code was in the same place where that `binding` was defined (remember the ‘anchor’ metaphor).

Example to demonstrate `binding`
```Ruby
def return_binding
  foo = 100
  binding
end
# Foo is available thanks to the binding,
# even though we are outside of the method
# where it was defined.
puts return_binding.class     #Binding
puts return_binding.eval('foo')     #100
# If you try to print foo directly you will get an error.
# The reason is that foo was never defined outside of the method.
puts foo      #NameError
```
>>* `eval(string [, binding [, filename [,lineno]]])` => it returns an obj.
>>>* Evaluates the Ruby expression(s) in *string*. If *binding* is given, which must be a `Binding` object, the evaluation is performed in its context.
>>>* If the optional *filename* and *lineno* parameters are present, they will be used when reporting syntax errors.

You don’t need to use `binding` objects directly, but it’s still good to know this is a thing!

+ Enough with *Ruby* today! It is time for some *JS* and I will be practising that on Codeacademy *__Learn JavaScript__* course.
>* I've already started it ages ago but then the curriculum has been updated so it is a good time to sharpen my skills.

+ After working on some *Ruby* & *JavaScript*, I've decided that is enough with programming languages I will practice some HTML, CSS & responsive design on FreeCodeCamp *__Responsive Web Design Certification__* that I've started it very long time ago and after the curriculum is updated I will try to finish it!
>* I will take __quick notes__ on things I haven't seen/learned about before because I would rather practice on the platform than documenting plenty of info.

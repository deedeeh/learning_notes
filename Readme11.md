#### Continue Learning Notes - 9

###### Continue: Tuesday 28th August

>* __The Abstraction of Instance Methods__
>* In Ruby, it is possible to simply set an instance variable with the following method:
```Ruby
kanye.instance_variable_set(:@name, "Yeezy")
```
>* It is also possible to simply retrieve an instance variable from an object with the following method:
```Ruby
kanye.instance_variable_get(:@name)
  => "Yeezy"
```
Since this is the case, __why do we even use instance setter and getter methods?__

>* In fact, there are a number of reasons:
>>* *Syntactic Vinegar* vs. *Syntactic Sugar*
>>>* The first reason is a __stylistic__ one but it is important.
>>>* As object-oriented Rubyists, we care about our program's readability and design.
>>>* The above method is ugly. It places a verb at the end of the method name. The weird grammar of this method should remind us not to use it.
>>>* This technique of purposely naming methods in a hard to use manner is called __syntactic vinegar__.
>>* *Exposing Literal Variables* vs. *Abstracting Attributes*
>>>* The `instance_variable_set` method depends on a literal, concrete variable, `@name`.
>>>* It exposes it directly to the person executing our code. This is bad practice because it forces our program to rely directly on the `@name` variable.
>>* __Why is this so terrible?__
>>>* What if we want our program to store both a first and last name.
>>>* Let's do a quick refactor of our Person class.

```Ruby
class Person

  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  #...

end
```
>* Our program has some added functionalty. We could imagine collecting all of our instances of `Person` and sorting them by last name, for example.
>>* Now, any other part of our program that was calling `instance_variable_get(:@name)` is broken!
>>* Additionally, any part of our program that is calling `instance_variable_set(:@name)` isn't taking advantage of our new first name and last name functionality.
>>* Allowing our code to rely on an instance variable directly created a program that is not flexible.
>>* If our program contains multiple occurrences of `instance_variable_get(:@name)` and `instance_variable_set(:@name)`, we would have to hunt down *each* and *every* one and change them to accommodate our shift to using both a first and a last name.
>>* Instead of writing code that depends on instance (or any type of) variables, we *write methods* that contain instance variables.
>>* This is a form of abstraction, whereas the instance variable `@name` is a *literal value*. The literal value reference, the variable `@name`, may change as our application grows and we want our application to seamlessly accommodate that change.

Let's create abstraction: the `#name=` and `#name` setter and getter instance methods:
```Ruby
class Person

  def initialize(first_name, last_name)
    @first_name = first_name
    @last_name = last_name
  end

  def name=(full_name)
    first_name, last_name = full_name.split
    @first_name = first_name
    @last_name = last_name
  end

  def name
    "#{@first_name} #{@last_name}".strip
  end

end
```
>* We can change the content of these methods according to our needs, without needing to hunt down every appearance of them in our program and change them as well, like we would need to do with our `instance_method_set` and `instance_method_get` usages.

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
>* Our program has some added functionality. We could imagine collecting all of our instances of `Person` and sorting them by last name, for example.
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

---

###### Wednesday 29th August
+ I worked on *__Object Attributes Lab__* where I practice to create classes, methods inside those classes with instance variables to write & read the added attributes.

```Ruby
class Person
  def name=(person_name)
    @name = person_name
  end

  def name
    @name
  end

  def job=(person_job)
    @job = person_job
  end

  def job
    @job
  end
end

# Extra work
ashley = Person.new

ashley.name = "Ashley"
ashley.job = "Web Developer"

puts "Hello, my name is #{ashley.name} and I am a #{ashley.job}."
```
+ I am working on *__Object Lifecycle__*
section where I will be learning about `#initialize` and work on a lab to practice its use.
>* I've learned about creating new instances of a class and sets that object equal to a variable and if we want to give our class attributes we can create a method to write & another one to read that attribute.
>* But for example most dogs are born with a breed, not assigned a breed afterwards.
>>* How can we model the behavior of dogs being born with a breed in our `Dog` class?
>>* `#initialize` method let us assign an individual dog a breed *automatically upon creation*, or *instantiation*.
>>* If we want *each* instance of our class to be created with certain attributes, we must define an `#initialize` method.
>>* An `#initialize` method is a method that is *called automatically* whenever `#new` is used.
>* Let's define our `#initialize` method to contain the functionality of the `#breed=` method, so that a dog instance will get a breed assigned to it right away when it is created, without us having to explicitly use the `#breed=` method.

```Ruby
class Dog
  def initialize(breed)
    @breed = breed
  end

  def breed=(breed)
    @breed = breed
  end

  def breed
    @breed
  end
end
```
Now we can call `#new`

```Ruby
lassie = Dog.new("Collie")

lassie.breed #=> "Collie"
```
>* When `#new` is called with an argument, it will pass that argument (or arguments) to the `#initialize` method and invoke that method. The code in `#initialize` will then run, using any arguments from `#new`.
>* The initialize method is what's called a *callback method*, because it is automatically invoked every time the `#new` method is used to create a new instance of the class.
>* Think of the initialize method as a *constructor method*. A constructor method is invoked upon the creation of an instance of a class and used to help define the instance of that class.
>* Every time you type `Dog.new("some breed")`, a new dog instance is created that has a breed of "some breed".

+ I completed *__Object Initialize Lab__* and here is my code for one of the classes:

```Ruby
class Dog
  def initialize(name, breed="Mutt")
    @name = name
    @breed = breed
  end
end
```
>>* In this class I created an `#initalize` method that accepts 2 arguments, the 2nd one is a default argument which is optional to add a breed and if not it is going to be "Mutt".
>>* Then I stored each of these arguments in its own instance variable.
>>* If I want to extend my code I can create the setter & getter methods so once I have new instances I can read these objects or edit attributes values.

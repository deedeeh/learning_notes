#### Continue Learning Notes - 14

###### Continue: Saturday 8th September

+ The 3rd resource is [Ruby- Object Oriented](https://www.tutorialspoint.com/ruby/ruby_object_oriented.htm) and I will be taking notes for information that I haven't seen before or not already in my notes.
>* The data and methods within a class are called *members of the class*.
>* If there is more than one word in the class name, by convention CamelCase.
>* __Instance Variables__ => are kind of *class attributes* and they become *properties of objects* once objects are created using the class.
>>* Every object's attributes are assigned individually and share no value with other objects.
>>* They are accessed using the `@` operator within the class but to access them outside of the class we use __public__ methods, which are called __accessor methods__ (getter methods)

```Ruby
class Box
   def initialize(w,h)
      # assign instance variables
      @width, @height = w, h
   end
end
```
>* __Accessor (getter )& setter methods__
>>* To make the instance variables available from outside the class => "getter"
>>* To set the value of those variables from outside of the class => "setter"

```Ruby
# define a class
class Box
   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end

   # accessor methods
   def getWidth
      @width
   end
   def getHeight
      @height
   end

   # setter methods
   def setWidth=(value)
      @width = value
   end
   def setHeight=(value)
      @height = value
   end
end

# create an object
box = Box.new(10, 20)

# use setter methods
box.setWidth = 30
box.setHeight = 50

# use accessor methods
x = box.getWidth()  #we can have no brackets as well
y = box.getHeight()

puts "Width of the box is : #{x}"
puts "Height of the box is : #{y}"
```

```Ruby
Width of the box is : 30
Height of the box is : 50
```

>* __Instance Methods__ => are also defined in the same way as we define any other method using `def` keyword and they can be used using a *class instance only*

The following code is from another resource which I find it easier to understand. Check it [here](http://www.railstips.org/blog/archives/2009/05/11/class-and-instance-methods-in-ruby/)

```Ruby
# Way 1
class Foo
  def baz
    puts 'instance method'
  end
end

Foo.new.baz # "instance method"

# Way 2
class Foo
  attr_accessor :baz
end

foo = Foo.new
foo.baz = 'instance method'
puts foo.baz

# Way 3
class Foo; end

foo = Foo.new
def foo.bar
  puts 'instance method'
end

Foo.new.baz # "instance method"
```

>>* You have to create a new instance to use them. (Foo.new).
>>* There are more ways to define instance methods than this, especially if you look into meta programming.

>* __Class Variables__ =>  is a variable, which is *shared* between all instances of a class.
>>* Class variables are prefixed with two @ characters `@@`.
>>* A class variable must be initialized within the class definition
>* __Class Methods__ => is defined using `def self.methodname()`, which ends with end delimiter and would be called using the class name as `classname.methodname`

Here is an example on class variables & methods.

```Ruby
class Box
   # Initialize our class variables
   @@count = 0
   def initialize(w,h)
      # assign instance avriables
      @width, @height = w, h
      # it will add one every time we have an instance of class Box.
      @@count += 1  
   end

   def self.printCount()
      puts "Box count is : #@@count"
   end
end

# create two object
box1 = Box.new(10, 20)
box2 = Box.new(30, 100)

# call class method to print box count
Box.printCount()

# If we create a box3 object and call the class method again the answer will be 3
```
```Ruby
Box count is : 2
```

>* The __to_s__ method => Any class you define should have a __to_s__ instance method to return a string representation of the object.

```Ruby
class Box
   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end
   # define to_s method
   def to_s
      "(w:#@width,h:#@height)"  # string formatting of the object.
   end
end

# create an object
box = Box.new(10, 20)

# to_s method will be called in reference of string automatically.
puts "String representation of box is : #{box}"
```
```Ruby
String representation of box is : (w:10,h:20)
```
>* __Access Control__ =>  Ruby gives you *three levels* of protection at instance methods level, which may be __public__, __private__, or __protected__.
>>* Ruby does not apply any access control over instance and class variables.
>>* __Public Methods__ => They can be called by anyone. Methods are public by default except for `initialize`, which is *always* private.
>>* __Private Methods__ => They cannot be accessed, or even viewed from outside the class. *Only* the class methods can access private members.
>>* __Protected Methods__ => They can be invoked *only* by objects of the defining *class* and its *subclasses*. Access is kept within the family.

Here is an example to demonstrate that:

```Ruby
# define a class
class Box
   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end

   # instance method by default it is public
   def getArea
      getWidth() * getHeight
   end

   # define private accessor methods
   def getWidth
      @width
   end
   def getHeight
      @height
   end
   # make them private
   private :getWidth, :getHeight

   # instance method to print area
   def printArea
      @area = getWidth() * getHeight
      puts "Big box area is : #@area"
   end
   # make it protected
   protected :printArea
end

# create an object
box = Box.new(10, 20)

# call instance methods
a = box.getArea()
puts "Area of the box is : #{a}"

# try to call protected or methods
box.printArea()
```
```Ruby
Area of the box is : 200
test.rb:42: protected method 'printArea' called for #
<Box:0xb7f11280 @height = 20, @width = 10> (NoMethodError)
```

>>* I've tried to call the private methods as well and I get the same `NoMethodError`.

>* __Class Inheritance__ => Inheritance allows us to define a class in terms of another class, which makes it easier to create and maintain an application.
>>* Inheritance also provides an opportunity to
>>>* *reuse* the code functionality and
>>>* *fast* implementation time
>>>* but unfortunately Ruby does not support multiple levels of inheritances but Ruby supports __mixins__.
>>* __mixin__  => is like a specialized implementation of multiple inheritance in which *only the interface portion is inherited*.
>>* When creating a class, instead of writing completely new data members and member functions, the programmer can designate that the new class should *inherit* the members of an *existing class*.
>>>* This existing class is called the __base class or superclass__, and the new class is referred to as the __derived class or sub-class__
>>>* The syntax for extending a class is simple. Just add a `<` character and the name of the *superclass* to your class statement.

```Ruby
# define a class
class Box
   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end
   # instance method
   def getArea
      @width * @height
   end
end

# define a subclass
class BigBox < Box

   # add a new instance method
   def printArea
      @area = @width * @height
      puts "Big box area is : #@area"
   end
end

# create an object
box = BigBox.new(10, 20)

# print the area
box.printArea()

#=> Big box area is : 200
```

>* __Methods Overriding__ => you can add new functionality in a derived class, but sometimes you would like to change the behaviour of *already defined method* in a parent class.
>>* You can do so simply by *keeping* the method name same and overriding the functionality of the method.

```Ruby
# define a class
class Box
   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end
   # instance method
   def getArea
      @width * @height
   end
end

# define a subclass
class BigBox < Box

   # change existing getArea method as follows
   def getArea
      @area = @width * @height
      puts "Big box area is : #@area"
   end
end

# create an object
box = BigBox.new(10, 20)

# print the area using overriden method.
box.getArea()
```

---

###### Monday 10th September

+ Today I will continue [Ruby - Object Oriented](https://www.tutorialspoint.com/ruby/ruby_object_oriented.htm) and there are few concepts that I need to learn about.
>* __Operator Overloading__  (From another resource) => Operator overloading allows us to use standard operators on our custom classes.

Here is an example:

```Ruby
class Point2D
    def initialize(x, y)
        @x = x
        @y = y
    end
end

p1 = Point2D.new(2, 3)
p2 = Point2D.new(4, 5)
```

Let's say I want to be able to do the following operations:

```Ruby
p1 + p2
p1 - p2
p1 * p2
p1 / p2
```

To achieve this, we can perform operator overloading in Ruby.

```Ruby
class Point2D
    attr_accessor :x, :y
    def initialize(x, y)
        @x = x
        @y = y
    end

    def +(second)
        Point2D.new(@x + second.x, @y + second.y)
    end

    def -(second)
        Point2D.new(@x - second.x, @y - second.y)
    end

    def *(second)
        Point2D.new(@x * second.x, @y * second.y)
    end

    def /(second)
        Point2D.new(@x / second.x, @y / second.y)
    end

    def to_s
        return "(#{@x}, #{@y})"
    end
end
```

```Ruby
p1 = Point2D.new(2, 3)
p2 = Point2D.new(4, 5)
puts p1 + p2      #=>(6, 8)
puts p1 - p2      #=>(-2, -2)
puts p1 * p2      #=>(8, 15)
puts p1 / p2      #=>(0, 0)
```

There is another example that I would like to share from [Ruby for Newbies: Operators & their Methods](https://code.tutsplus.com/tutorials/ruby-for-newbies-operators-and-their-methods--net-18163) by *Andrew Burgess*

```Ruby
class Fridge
    def initialize (beverages=[], foods=[])
        @beverages = beverages
        @foods     = foods
    end

    def + (item)
      if item.is_a? Beverage
        @beverages.push item
      else
        @foods.push item
      end
    end

    def - (item)
      ret = @beverages.find do |beverage|
        beverage.name.downcase == item.downcase
      end
      return @beverages.delete ret unless ret.nil?

      ret = @foods.find do |food|
          food.name.downcase == item.downcase
      end
      @foods.delete ret
    end
end
```
>>* You might wonder why we’re using the keyword `return` here, since it’s not required in Ruby. If we didn’t use it here, the function wouldn’t return yet, since there’s more code to the function.
>>* Using `return` here allows us to return a value from a place the function wouldn’t normally return.

```Ruby
class Beverage
    attr_accessor :name

    def initialize name
        @name = name
        @time = Time.now
    end
end
class Food
    attr_accessor :name

    def initialize name
        @name = name
        @time = Time.now
    end
end
```
```Ruby
f = Fridge.new  #a new instance of class Fridge
#<Fridge:0x00000100a10378 @beverages=[], @foods=[]>
f + Beverage.new("water")
#[#<Beverage:0x000001009fe8d0 @name="water", @time=2011-01-15 13:20:48 -0500>]
f + Food.new("bread")
#[#<Food:0x000001009d3c98 @name="bread", @time=2011-01-15 13:20:59 -0500>]
f + Food.new("eggs")
[
  #<Food:0x000001009d3c98 @name="bread", @time=2011-01-15 13:20:59 -0500>,
  #<Food:0x000001009746a8 @name="eggs", @time=2011-01-15 13:21:04 -0500>
]
f + Beverage.new("orange juice")
[
  #<Beverage:0x000001009fe8d0 @name="water", @time=2011-01-15 13:20:48 -0500>,
  #<Beverage:0x00000100907cd8 @name="orange juice", @time=2011-01-15 13:21:16 -0500>
]
f #to check what we have in Fridge
#<Fridge:0x00000100a10378
  @beverages=[
      #<Beverage:0x000001009fe8d0 @name="water", @time=2011-01-15 13:20:48 -0500>,
      #<Beverage:0x00000100907cd8 @name="orange juice", @time=2011-01-15 13:21:16 -0500> ],
  @foods=[
      #<Food:0x000001009d3c98 @name="bread", @time=2011-01-15 13:20:59 -0500>,
      #<Food:0x000001009746a8 @name="eggs", @time=2011-01-15 13:21:04 -0500> ]
f - "bread"
#<Food:0x000001009d3c98 @name="bread", @time=2011-01-15 13:20:59 -0500>
f   #check if "bread" is deleted
#<Fridge:0x00000100a10378
  @beverages=[
      #<Beverage:0x000001009fe8d0 @name="water", @time=2011-01-15 13:20:48 -0500>,
      #<Beverage:0x00000100907cd8 @name="orange juice", @time=2011-01-15 13:21:16 -0500>],
  @foods=[#<Food:0x000001009746a8 @name="eggs", @time=2011-01-15 13:21:04 -0500>]
```
I believe operator overloading is too powerful and there are many of those operators and not just the arithmetic ones `+`, `-`, `*` & `/`
Here is a list of the operators:
>>* Get and Set Operators: `[]` `[]=`
>>* Shovel Operator: `<<`
>>* Comparison Operators: `==` `<` `>` `<=` `>=`
>>* Case equality Operator: `===`
>>* Bit-wise Operator: `|` `&` `^`

>* __Freezing Objects__ => We use it when we want to prevent an object from being changed. The `freeze` method effectively turning an object into a constant.
>>* A frozen object may not be modified: you can't change its instance variables.
>>* Any object can be frozen by invoking `Object.freeze`
>>* You can check if a given object is already frozen or not using `Object.frozen?` method, which returns true in case the object is frozen otherwise a false value is return.

```Ruby
# define a class
class Box
   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end

   # accessor methods
   def getWidth
      @width
   end
   def getHeight
      @height
   end

   # setter methods
   def setWidth=(value)
      @width = value
   end
   def setHeight=(value)
      @height = value
   end
end

# create an object
box = Box.new(10, 20)

# let us freeze this object
box.freeze
if( box.frozen? )
   puts "Box object is frozen object"
else
   puts "Box object is normal object"
end

# now try using setter methods
box.setWidth = 30
box.setHeight = 50

# use accessor methods
x = box.getWidth()
y = box.getHeight()

puts "Width of the box is : #{x}"
puts "Height of the box is : #{y}"
```
```Ruby
Box object is frozen object
test.rb:20:in `'setWidth=': can't modify frozen object (TypeError)`
```
>* __Class Constants__ => are variables. By convention, we keep constant names in *upper case*. They are assigned to direct numeric or string values.
>>* Once a constant is defined, you *cannot* change its value
>>* you can access a constant directly *inside* a class much like a variable
>>* to access a constant *outside* of the class then you would have to use `classname::constant`
>>* Class constants are inherited and can be __overridden__ like instance methods.

```Ruby
# define a class
class Box
   BOX_COMPANY = "TATA Inc"
   BOXWEIGHT = 10
   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end
   # instance method
   def getArea
      @width * @height
   end
end

# create an object
box = Box.new(10, 20)

# call instance methods
a = box.getArea()
puts "Area of the box is : #{a}"
puts Box::BOX_COMPANY
puts "Box weight is: #{Box::BOXWEIGHT}"
```

```ruby
Area of the box is : 200
TATA Inc
Box weight is: 10
```

>* __Create Object Using `allocate`__ => There may be a situation when you want to create an object without calling its constructor `initialize`, you can call `allocate`, which will create an uninitialized object for you.

```Ruby
# define a class
class Box
   attr_accessor :width, :height

   # constructor method
   def initialize(w,h)
      @width, @height = w, h
   end

   # instance method
   def getArea
      @width * @height
   end
end

# create an object using new
box1 = Box.new(10, 20)

# create another object using allocate
box2 = Box.allocate

# call instance method using box1
a = box1.getArea()
puts "Area of the box is : #{a}"

# call instance method using box2
a = box2.getArea()
puts "Area of the box is : #{a}"
```

```Ruby
Area of the box is : 200
test.rb:14: warning: instance variable @width not initialized
test.rb:14: warning: instance variable @height not initialized
test.rb:14:in `'getArea': undefined method '*' for nil:NilClass (NoMethodError) from test.rb:29`
```

>* __Class Information__ => If class definitions are executable code, this implies that they execute in the context of some object: `self` must reference something.

```Ruby
class Box
   # print class information
   puts "Type of self = #{self.type}"
   puts "Name of self = #{self.name}"
end
```
```Ruby
Type of self = Class
Name of self = Box
```
>>* This means that a class definition is executed with that class as the current object.
>>* This means that methods in the metaclass and its superclasses will be available during the execution of the method definition.

#### Continue Learning Notes - 12

###### Sunday 2nd September
+ I am working on the rest of *__Todo List Project__* and here are the new highlights:

>* `event.which` => For key or mouse events, this property indicates the specific key or button that was pressed. In the following code 13 is the *keyCode* for *Enter*
>* `val()` => *Get* the current value of the first element in the set of matched elements or *set* the value of every matched element.
>>* In the following code we __get__ the value of the input and store it in variable `todoText`.
>>* Then we __set__ the value of input to an empty string so we can have a blank input after pressing enter.
>* `append()` => Insert content, specified by the parameter, to the end of each element in the set of matched elements.
>>* It adds the specified content as the *last child* of each element in the jQuery collection.
>>* If we want to insert content as *first child* we can use `prepend()`.

```javascript
$("input[type='text']").on("keypress", function(event){
  if(event.which === 13){
    //grabbing new todo text from input
    var todoText = $(this).val();
    $(this).val("");
    //create a new li and add to ul
    $("ul").append(`<li><span>X</span> ${todoText}</li>`);
  }
});
```

>* __Template literals__ are string literals allowing embedded expressions. They are enclosed by the back-tick (` `) and they can contain placeholders. These are indicated by the dollar sign and curly braces `${expression}`. The expressions in the placeholders and the text between them get passed to a function.
>* The one key difference between event listener such as `click()` & `on("click")`
>>* `click()` only adds listeners for existing elements.
>>* `on("click")` will add listeners for all potential future elements.
>* `on(event, selector, data)` => Attach an event handler function for one or more events to the selected elements. Check the following code:

```javascript
$("ul").on("click", "li", function(){
  $(this).toggleClass("completed");
});
```
>>* In order for `on()` to work we need to select the existing element in the DOM which is this case is the `ul` & not the `li` because we will add more `lis` in future.
>>* The selector that we want to work with such as `li` will be passed as a second argument to the `on()` method.
>>* So the `ul` will listen to any click events on any of its `lis` whether it is an existing one or an added one and then will implement the code block.

#### Styling The App
Here are some of the properties I've used in this project:
>* `box-shadow` => attaches one or more shadows to an element. Some of the values are:
>>* `none`
>>* `h-offset` (Required) => The horizontal offset of the shadow.
>>>* A positive value puts the shadow on the right side of the box.
>>>* A negative value puts the shadow on the left side of the box.
>>* `v-offset` (Required) => The vertical offset of the shadow.
>>>* A positive value puts the shadow below the box.
>>>* A negative value puts the shadow above the box.
>>* `blur` (optional) => The higher the number, the more blurred the shadow will be.
>>* `spread` (optional) => A positive value increases the size of the shadow, a negative value decreases the size of the shadow.
>>* `color`(optional) => The color of the shadow. The default value is the text color.
>>* `inset` => Changes the shadow from an outer shadow (outset) to an inner shadow.
>* An example of box-shadow:
`box-shadow: 10px 10px 8px 10px #888888;`
>* An example of multiple shadows:
`box-shadow: 5px 5px blue, 10px 10px red, 15px 15px green;`

>* `background` is a shorthand for:
>>* `background-color`
>>* `background-image` => sets one or more background images for an element.
>>>* Use `url('URL')` and to specify more than one image, separate the URLs with a comma.
>>>* `none` => No background image will be displayed. This is default.
>>* `background-repeat` => most common values are:
>>>* `repeat` => The background image is repeated both vertically and horizontally.  The last image will be clipped if it does not fit. This is default.
>>>* `repeat-x` => The background image is repeated only horizontally.
>>>* `repeat-y` => The background image is repeated only vertically.
>>>* `no-repeat` => The background-image is not repeated. The image will only be shown once.
>>* `background-position` => sets the starting position of a background image.
>>>* The values are to have either `left`, `right` or `center` with `top`, `bottom` or `center` so like this `left top`
>>>* If you only specify *one keyword*, the other value will be `center`
>* `text-transform` => controls the capitalisation of text. Here are the most common values used:
>>* `uppercase`
>>* `lowercase`
>>* `capitalize`
>>* `initial` => Sets this property to its default value.
>>* `inherit` => Inherits this property from its parent element.
>* `list-style` => It is a shorthand for the properties:
>>* `list-style-type` => specifies the appearance of a list item element. And the common values are:
>>>* `disc`(default value), `circle`, `square`, `decimal`, `upper-latin`,`upper-roman` and `none`
>>>* Check the rest of the values online.
>>* `list-style-image` => replaces the list-item marker with an image.
>>>* `url` => The path to the image to be used as a list-item marker like `url('sqpurple.gif')`
>>>* `none` => No image will be displayed. Instead, the `list-style-type` property will define what type of list marker will be rendered. This is default.
>>* `list-style-position` => specifies the position of the list-item markers (bullet points). Values are:
>>* `outside` => means that the bullet points will be outside the list item.
>>>* The start of each line of a list item will be aligned vertically. This is default.
>>* `inside` => means that the bullet points will be inside the list item.
>>>* As it is part of the list item, it will be part of the text and push the text at the start.
>>* Also there is `initial` & `inherit`.
>* `:nth-child(n)` => pseudo-class matches elements based on their position in a group of siblings, regardless of type, of its parent. Some of the values:
>>* `odd` => lets say we have a `ul` so if we select the `li:nth-child(odd)` it will represent list 1, 3, 5, etc...
>>>* We can also have the same result with `li:nth-child(2n+1)`
>>* `even` => so here represents list 2,4,6,etc...
>>>* We can have the same with `li:nth-child(2n)`
>>* If we give just a number without `n` it means it will represent the element in that number such as `:nth-child(7)` it means the seventh element.
>>* Using a formula `(an + b)` => `a` represents a *cycle size*, `n` is a *counter* (starts at 0), and `b` is an *offset value*.
>>>* `:nth-child(3n+4)` represents element __4__ [=(3×0)+4], 7 [=(3×1)+4], 10 [=(3×2)+4], 13 [=(3×3)+4], etc.
>* `height` & `line-height` => I can set the height of an element that contains text (for example a text input) but the text won't be centered vertically and that's when we should use `line-height` with the same value as `height`.
>* `box-sizing` => can make building CSS layouts easier and a lot more intuitive.
>>* Since the width and height you set for an element both go out the window of the box model as soon as you start adding padding and borders to the element and that is why we use `box-sizing` so we can have the same width we set even after adding padding & border.
>>* Universal box-sizing `*, *:before, *:after {
  box-sizing: border-box;}`
>>* __Vendor Prefixes__ => if you need to support older versions of Safari (< 5.1), Chrome (< 10), and Firefox (< 29), you should include the prefixes `-webkit` and `-moz`, like this:
```css
html {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
```
>* `:focus` => is a pseudo-class represents an element (such as a form input) that has received focus. It is generally triggered when the user *clicks* or taps on an element or selects it with the keyboard's *"tab"* key.
>* `outline` => a line that is drawn around elements, *OUTSIDE* the borders, to make the element "stand out". This is a shorthand property for:
>>*  `outline-width` => It has the following values:
>>>* `thin` => typically 1px
>>>* `medium` => typically 3px
>>>* `thick` => typically 5px
>>>* Or I can add a specific size (in px, pt, cm, em, etc)
>>* `outline-style` (required) => There are different values but the most common ones are:
>>>* `dotted`, `dashed`, `solid` and `double`
>>>* Check for the rest of the values online.
>>* `ouline-color`
>* __CSS gradients__ let you display smooth transitions between two or more specified colors. There are 2 types of gradients:
>>* *Linear Gradients* (direction, color1, color2, ...)
>>>* direction => the default is top to bottom, and I can change that by bottom to top, left to right, right to left or diagonal.
>>>* If I want more control over the direction of the gradient I can add angle instead of the previous directions. For ex. `background-image: linear-gradient(-90deg, red, yellow)`
>>* Radial Gradients (defined by their center)
>>* We can add transparency by adding `rgba()` color.
>>>* To create a radial gradient you must also define at least two color stops.
>>>* For more check online resources.
>>* With gradients we have the vendor prefixes issue and that is why we use different cross-browser like `-webkit`
>>* We also need a backup color for older browsers so we add `background-color`.
>* A new CSS framework __Font Awesome__ that I can download or have it as a cdn link. [Check it out!](https://fontawesome.com/)
>>* To add it in my project, I will insert the path or link between a `<link>` tag under the styling file.

---

###### Monday 3rd September
+ I have few coding to do for this project and then I am done!
>* After linking the __Font Awesome__ framework to our HTML file we can pick on the above website the icon we want, click on it and then under the big svg illustration there is an HTML tag to copy includes `<i></i>` stands for icon.
>>* Between that tag a `class` with the values of the icon you selected.
>>* Copy & paste in HTML then voilà you have your icon on your project.
>* `transition` => allows you to change property values smoothly (from one value to another), over a given duration.
>>* This is the shorthand for the following properties & they should be added in the same order like this `{transition: <property> <duration> <timing-function> <delay>;}`
>>>* `transition-property` => Specifies the name or names of the CSS properties to which transitions should be applied. Here are some of the values:
>>>>* `none`
>>>>* `all` => Default value. All properties will get a transition effect
>>>>* __property__ => Defines a comma separated list of CSS property names the transition effect is for.
>>>* `transition-duration` => specifies how many seconds (s) or milliseconds (ms) a transition effect takes to complete.
>>>>*  Default value is 0s, meaning there will be no effect
>>>* `transition-timing-function` => specifies the speed curve of the transition effect. It allows a transition effect to change speed over its duration. The most common values are:
>>>>* `ease` => Default value. Specifies a transition effect with a slow start, then fast, then end slowly.
>>>>* `linear` => Specifies a transition effect with the *same speed* from start to end.
>>>>* `ease-in` => Specifies a transition effect with a *slow start*.
>>>>* `ease-out` => Specifies a transition effect with a *slow end*.
>>>>* `ease-in-out` => Specifies a transition effect with a slow start and end.
>>>>* Check the rest of the values online.
>>>* `transition-delay` => Defines how long to wait between the time a property is changed and the transition actually begins. Value is defined in seconds (s) or milliseconds (ms).
>>* This is one of the properties that has the __vendor prefixes__ problem and that is why we use
>>>* `-webkit-` (Chrome, Safari, newer versions of Opera, almost all iOS browsers (including Firefox for iOS); basically, any WebKit based browser)
>>>* `-moz-` for Firefox
>>>* `-o-` (Old, pre-WebKit, versions of Opera)
>>>* `-ms-` (Internet Explorer and Microsoft Edge)

>>* The following code snippet basically hides the `span` that contains the trash icon then when the user hovers on the `li` the `span` appears.  
>>* The `span` disappears again when the user removes the cursor from that `li`.
>>* The main properties that does that are `width` & `opacity` plus of course `display` & `height`.

```css
span {
  background: #e74c3c;
  height: 40px;
  margin-right: 20px;
  text-align: center;
  color: #fff;
  width: 0;
  display: inline-block;
  transition: 0.2s linear;
  opacity: 0;
}

li:hover span{
  width: 40px;
  opacity: 1.0;
}
```

##### New jQuery Method:
>* `fadeToggle()` => Display or hide the matched elements by animating their opacity. It takes arguments such as:
>>* *duration* => A string or number determining how long the animation will run.
The default is 400. Values could be:
>>>* milliseconds
>>>* `slow`
>>>* `fast`
>>* *easing* => A string indicating which easing function to use for the transition. Default is "swing".
>>>* `linear` => moves in a constant speed
>>>* More easing functions are available in external plugins.
>>* *complete* => A function to call once the animation is complete, called once per matched element.
>>* All of the above parameters are __optional__.

+ I completed the *__Todo List Project__*. You can check my code on Github.

+ I am watching a video on Youtube with the title *__Yield & Enumerables__* by Learn.co channel. And here are some of the new things I've learned:

#### New Terminology In Programming
>* __Polymorphism & Interfaces__ or *Polymorphic Interfaces*
>>* Polymorphism provides one of the most useful programming techniques of the object-oriented paradigm.
>>* It means "many forms" (poly = many, morphos = form) because it changes its behaviour based on how you use it.
>>* Most of Ruby methods are polymorphic Interfaces such as:
>>>* `#count` method without giving an argument it will return an integer.
>>>* `#count(obj)` if we pass an argument it counts the number of elements which equal obj using ==.
>>>* `#count{|item| block}` it counts the number of elements for which the block returns a true value.

To demonstrate the previous interfaces check out this code:
```Ruby
ary = [1, 2, 4, 2]
ary.count                  #=> 4
ary.count(2)               #=> 2
ary.count { |x| x%2 == 0 } #=> 3
```

>* __Named block__ => `&block` (ampersand parameter). Usually blocks are anonymous in Ruby but we can give them a name by adding an `&` before the object's name then we do `object.call` in order to call the block to be executed. Here is what `&object` does:
>>* if the object is a block, it converts it to a `Proc`.
>>* if the object is a `Proc`, it converts it to a `block`.
>>* if the object is something else, it calls `to_proc` on it, and then converts it to a block.
>>>* `to_proc` it is a part of the protocol for *converting objects* to *Proc objects*. Instances of class Proc simply return themselves.

>* __teardown__ => It is the return of a method. It is the last thing it does.

+ After I'm done with the video, I've started reading about a blog post [Learning Ruby: From Zero to Hero](https://medium.freecodecamp.org/learning-ruby-from-zero-to-hero-90ad4eecc82d) by *TK* on medium and here are few things I wanted to take notes of:
>* __Classes & Objects__
>>* “Class” is a way to define objects. In the real world there are many objects of the same type. Like vehicles, dogs, bikes. Each vehicle has similar components (wheels, doors, engine).
>>* “Objects” have two main characteristics: data and behaviour. Vehicles have data like number of wheels and number of doors. They also have behaviour like accelerating and stopping.
>>* In object oriented programming we call
>>>* Data = `attributes`
>>>* Behaviour = `methods`.
>>* We can "get" or "set" an object attribute without using methods
>>>* `attr_reader` => implements the *getter* method.
>>>* `attr_writer` => implements the *setter* method.
>>>* `attr_accessor` => implements *both* methods.

```Ruby
class Vehicle
  attr_accessor :number_of_wheels, :seating_capacity, :maximum_velocity

  def initialize(number_of_wheels, seating_capacity, maximum_velocity)
    @number_of_wheels = number_of_wheels
    @seating_capacity = seating_capacity
    @maximum_velocity = maximum_velocity
  end
end

# number_of_wheels equals 4
tesla_model_s = Vehicle.new(4, 'electric', 5, 250)
tesla_model_s.number_of_wheels # => 4

# number_of_wheels equals 3
tesla_model_s.number_of_wheels = 3
tesla_model_s.number_of_wheels # => 3
```
>* __Encapsulation: Hiding information__
>>* Encapsulation is a way to restrict direct access to objects’ data and methods. At the same time it facilitates operation on that data (objects’ methods).
>>* All internal representation of an object is *hidden from the outside*, __only__ the object can interact with its internal data.
>>* __Remember__ in Ruby we use methods to directly access data. Without those methods of `name` & `age` we can't access those informations.

```Ruby
class Person
  def initialize(name, age)
    @name = name
    @age  = age
  end

  def name
    @name
  end

  def age
    @age
  end
end
```

```Ruby
tk = Person.new("Leandro Tk", 24)
```
>>* With encapsulation we can ensure that the object (tk in this case) is only allowed to access name and age.
>>* The internal representation of the object is hidden from the outside.

>* __Inheritance: behaviour & characteristics__
>>* Certain objects have something in common. Behaviour and characteristics.
>>* In object oriented programming, classes can inherit common characteristics (data) and behaviour (methods) from another class.
>>* In Ruby, we use the `<` operator to show a class inherits from another.

From the previous example `Vehicle` class we can have a new class of `ElectricCar` that can inherit from the `Vehicle` class.

```Ruby
class ElectricCar < Vehicle
end
```
>>* We don’t need to implement the initialize method and any other method, because this class already has it (inherited from the Vehicle class).

```Ruby
tesla_model_s = ElectricCar.new(4, 5, 250)
tesla_model_s.number_of_wheels # 4
tesla_model_s.seating_capacity # 5
tesla_model_s.maximum_velocity # 250
```
>>* I've checked the code on irb to prove it to myself and it worked!

>* __Module: A Toolbox__
>>* We can think of a module as a toolbox that contains a set of constants and methods. (This is the best way TK explained it)
>>* An example of a Ruby module is `Math`
>>>* constant PI => `Math::PI # > 3.141592653589793`
>>>* the `.sqrt` method => `Math.sqrt(9) # 3.0`
>>* we can implement our own `module` and use it in classes.

```Ruby
class RunnerAthlete
  def initialize(name)
    @name = name
  end
end
```
>>* And implement a module `Skill` to have the `average_speed` method.

```Ruby
module Skill
  def average_speed
    puts "My average speed is 20mph"
  end
end
```
>>* How do we add a module to a class so it has this behaviour `average_speed` method?

```Ruby
class RunnerAthlete
  include Skill

  def initialize(name)
    @name = name
  end
end
```
>>* See the `include Skill`?
>>* And now we can use this method in our instance of RunnerAthlete class.
```Ruby
mohamed = RunnerAthlete.new("Mohamed Farah")
mohamed.average_speed # "My average speed is 20mph"
```

>* We need to *understand* that:
>>* A module can have no instances.
>>* A module can have no subclasses.
>>* A module is defined by module…end.
>>* A module's name is capital same as a class or camelCased.

---

###### Tuesday 4th September
+ I have worked on Codeacademy *__Learn Ruby__* course long time ago but I haven't finished it. I still had OOP sections to finish so I thought it is a good time for more Ruby practice.

+ Here are some new things I've learned & used during those sections:
>* __Class variable__ => They are prefixed with `@@` before the name .
>* They can be used to *store data* that belongs to a *class*, but __not__ to its instances.
>* `public` methods => methods are public by default unless you use the private 0r protected keyword/method to make them not public.
>>* Public methods describe the outside (outside of the class definition) behaviours of an object.
>>* They are called with the object as the explicit receiver(thing you’re calling the method on: receiver.method)
>* `private` methods => are methods defined under the private keyword/method. Private methods can only be used within the class definition; they’re for internal usage.
>>* private methods can not be called with an explicit receiver, the receiver is always *implicitly self*.
>>* The only way to have external access to a private method is to call it within a public method.
>>* Think of private methods as internal helper methods.
>* __Constants__ = > is like a variable, except that its value is supposed to *remain constant* for the duration of the program.
>>* The Ruby interpreter does not actually enforce the constancy of constants, but it does issue a *warning* if a program changes the value of a constant.
>>* Ruby constants are written in ALL_CAPS and are separated with *underscores* if there's more than one word.
>* __Namespacing__ => is a way of bundling logically related objects together. Modules serve as a convenient tool for this such as `Math::PI`
>>* This allows classes or modules with conflicting names to co-exist while avoiding collisions.
>>* Think of this as storing different files with the same names under separate directories in your filesystem.
>>* The double colon you see is called the *scope resolution operator*, which is a fancy way of saying it tells Ruby where you're looking for a specific bit of code so in this case Ruby knows to look inside the `Math` module to get the `PI`.

##### Notes  
>* Some modules, like `Math`, are already present in the interpreter.
>* Others need to be *explicitly* brought in, however, and we can do this using `require`.
>* For example if we want to use the Ruby `Date` module to show today's date we need to do this:
```Ruby
require 'date'
puts Date.today
```

>* We can do more than just `require` a module but also we can `include` it!
>>* Any class that `include`s a certain module can use those module's methods.
>>* It should be after defining the class and we add `include Math` .

```Ruby
class Angle
  include Math
  attr_accessor :radians

  def initialize(radians)
    @radians = radians
  end

  def cosine
    cos(@radians)
  end
end

acute = Angle.new(1)
acute.cosine
```
>>* In the previous code we mixed together the behaviours of a class and a module!
>>* __mixin__ => When a module is used to mix additional behaviour and information into a class.
>>>* Mixins allow us to customize a class without having to rewrite code!

__The difference between `include` & `extend`__
>* `include` => mixes a module's methods in at *the instance level* (allowing instances of a particular class to use the methods)
>* `extend` => mixes a module's methods at *the class level*. This means that class itself can use the methods.

An example to demonstrate it:
```Ruby
module Foo
  def foo
    puts 'heyyyyoooo!'
  end
end

class Bar
  include Foo
end

Bar.new.foo # heyyyyoooo!
Bar.foo # NoMethodError: undefined method ‘foo’ for Bar:Class

class Baz
  extend Foo
end

Baz.foo # heyyyyoooo!
Baz.new.foo # NoMethodError: undefined method ‘foo’ for #<Baz:0x1e708>
```

#### Note:
>* We can use underscores in numbers `1_000_000`. Ruby allows this, and it makes it easier to read big numbers!

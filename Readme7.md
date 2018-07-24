#### Continue Learning Notes - 6

######  Thursday 19th July

+ I continued working on *__HTML5__* and today I've learned about:
>* Embedding audio so the tag is `<audio></audio>` and it takes attribute `src` for location.
>>* Different browser render supports different file types and that is why we provide the browser with `<source>` which is just an opening tag.
>>* Its attributes `src` & `type` - for instance `src="audio.mp3"` & `type="audio/mp3"`
>* Embedding video so the tag is `<video></video>` and its attribute `src`
>>* The same idea as `<audio` and the multiple file types so working with `<source` to add multiple files, each file with its own `<source>`.
>>* Its attributes `src` & `type` so example `src="movie.mp4"` & `type="video/mp4"`.
>* There is a converter for videos, audios, etc..., *miro video converter*. It contains different file types.  

######  Monday 23rd July
+ Today I continued the rest of *__Front-End HTML5__* section which contained a code along lab and a lesson full of resources to check.

+ I've learned about semantic containers, google map and practised videos and its different resources such as mp3 & ogv:
>* `<iframe></iframe>` with attributes `src`, `height`, `width` and `style`.
>* `<video></video>` and `source` with its attributes `src` and `type` and in the lab it was `type="video/mp3"` and `type="video/ogg"`
>* `<header></header>` represents a container for introductory content or a set of navigational links.
>* `<nav></nav>` tag defines a set of navigation links, only for major block of navigation links.
>* `<section></section>` is a thematic grouping of content, typically with a heading.
>>* Examples of sections would be chapters, the tabbed pages in a tabbed dialog box, or the numbered sections of a thesis.
>>* A Web site's home page could be split into sections for an introduction, news items, contact information.
>* `<footer></footer>` element represents a footer for its nearest ancestor sectioning content or sectioning root element.
>>* A footer typically contains information about its section such as who wrote it, links to related documents, copyright data, and the like.
>>* Footers don’t necessarily have to appear at the end of a section, though they usually do.
>>* When the footer element contains entire sections, they represent appendices, indexes, long colophons, verbose license agreements, and other such content.
>* `<figure></figure>` specifies self-contained content, like illustrations, diagrams, photos, code listings, etc.
>>* While the content of the `<figure>` element is related to the main flow, its position is independent of the main flow.
>>* If removed it should not affect the flow of the document.
>* `<figcaption></figcaption>` tag defines a caption for a `<figure>` element. It can be placed as the first or last child of the `<figure>` element.

######  Tuesday 24th July
+ I worked on *__Keys of Hash__* lab in *__More on Hashes__* section.

This is in spec repo:

```Ruby
let(:animals) { {"sugar glider"=>"Australia","aye-aye"=> "Madagascar","red-footed tortoise"=>"Panama","kangaroo"=> "Australia","tomato frog"=>"Madagascar","koala"=>"Australia"} }
```

Here is my solution:

```Ruby
class Hash
  def keys_of(*arguments)
    # code goes here
    result = []
    self.each do |k, v|
      arguments.map {|value| result << k if value == v}
    end
    result
  end
end
```
Learn.co solution:

```Ruby
class Hash
  def keys_of(*args)
    map {|key, value| args.include?(value) ? key : nil }.compact
  end
end
```
In Learn.co code I didn't know that I can use *map* or any other method inside the instance of a class without joining it to an argument. So the *map* works on `Hash.new` which is our example an hash of animals.

+ I've learned so many things today:
>* *Monkey patching* is the practice of re-opening and modifying pre-existing classes.
>>* It is generally avoided. You don't want to mess with the implementation of the objects and methods native to Ruby. It could get messy, fast.
>* `class` is the blueprint from which individual objects are created. In object-oriented terms, we say that your bicycle is an instance of the class of objects known as bicycles.
>>* To create a class you always start with the keyword *class* followed by the name of the class.
>>* The name of the class should always be in CamelCase.
>>* You terminate a class by using the keyword *end*.
>* `self` is a special variable that points to the object that "owns" the currently executing code. Ruby uses self everywhere:
>>* For instance variables: `@myvar`
>>* For method and constant lookup.
>>* When defining methods, classes and modules.
>>* So in this lab `self` belongs to `Hash.new` class which is a Hash of animals.
>* splat operator `*` has almost endless uses. But the main idea is that whenever you don’t want to specify the number of arguments you have, you would use a splat operator.
>* `compact` I have seen it couple of times before but every time it feels like I see it for the first time. It returns a copy of self with all nil elements removed. Usually it is used with `map` or `collect`.
>* Variables in Ruby Class are *4 types*:
>>* __Local Variables -__  are the variables that are defined in a method. Local variables are not available outside the method. They begin with a lowercase letter or _ .
>>* __Instance Variables -__ are available across methods for any particular instance or object. That means that instance variables change from object to object. They are preceded by the at sign @ followed by the variable name.
>>* __Class Variables -__ are available across different objects. A class variable belongs to the class and is a characteristic of a class. They are preceded by the sign @@ and are followed by the variable name.
>>* __Global Variables -__ Class variables are not available across classes. If you want to have a single variable, which is available across classes, you need to define a global variable. The global variables are always preceded by the dollar sign $.

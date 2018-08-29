#### Continue Learning Notes - 7

###### Tuesday 31st July
+ I am working on *__Front_End - CSS Introduction__* section as part of the *__Intro to HTML/CSS__*.

+ I worked on *__CSS Fundamentals__* where I've learned so many things:  
>* Formats: inline, internal and external, and the external is considered the best option for styling websites.
>* CSS syntax `p {color: white}`
>* The difference between Type selectors, ID selectors, Class selectors and Compound selectors; which is a set of selectors with comma separation that have the same styles.
>* Inheritance rules and the more specific a selector the more authority it has. ID over Class which over rules Type which over rule universal `*`
>* If multiple Classes are applied to the same element the Class listed furthest to the right over rules its neighbours to the left.
>* When conflicts with equal authority arise, CSS will listen to the last style it was told to apply.
>* The difference between *descendent selector*, *child selector* `#list > li`, *sibling selector* `h3 + p`; it will select just the 1st p as a sibling to the h3, *preceded selector* `h3 ~ p` it will select all p elements after h3 and *universal selector* `* {...}`
>* *Attribute selector* selects elements who have an attribute with matching value condition
>>* `img[alt="cat"]` equals to
>>* `a[href^="http"]` starts with
>>* `a[href$="com"]` ends with
>>* `img[alt*="love"]` anywhere within
>>* `p[class~="dog"]` space separated (when there is more than one class for an element.)
>>* `p[class|="dogs"]` dash separated
>* *Pseudo Class selector* selects elements based on a particular event state or relationship among other elements
>>* `a:link {...}` untouched link
>>* `a:visited {...}` already visited
>>* `a:hover {...}` on mouse hover
>>* `a:active {...}`on mouse click (when you click and hold)
>>* `p:first-child {...}`
>>* `p:last-child {...}`
>* I've learned about colors in CSS and how we can add them by
>>* *name*
>>* *hexadecimal system* - Hex system values use combination of the characters 0-9 as well as A-F
>>* *RGB/RGBA* using a scale of values between 0-255 for Red-Green-Blue and A (Alpha) allows an additional accepted value from 0-1 (0%-100% opacity)
>* Using web fonts where we can download the font we want for our project in a folder inside our site repo then we use `@font-face` selector to insert the font in our CSS file with properties `font-family` and `src` (location of the file) then we select the element we want and declare this font family to it.

__Check a list of the different Pseudo Classes and Pseudo elements__

__Check font and text declarations__

+ I worked on the *__CSS code along__* lab and next I have one more lesson and 2 other labs to finish this section.

---

###### Wednesday 1st August
+ I worked on 2 labs in *__CSS Introduction__* and still have 1 more lab to finish this section.
>* One of the labs was to create a rainbow with divs and colors so it was a good practice to learn about hexadecimal color system.
>* The second lab I had the styles written for me and all I had to do is to select the correct element with the correct selector syntax such as by ID, class, descendants, siblings and attribute selector.

```CSS
/* Select the image that has an attribute value matching "Kitty 5" (using attribute selector) */

img[alt="Kitty 5"] {
  position: absolute;
  z-index: 3;
  top: 217px;
  left: 223px;
}
```
+ I finished the last lab *__Bonus - CSS Graffiti override__* which is mainly about specificity in CSS and how there are many ways to override styles.
>* I tried to use different selectors such as descendants, child selector, sibling selector and Pseudo class.

```HTML
<div id="wall">
  <div class="tag-1"></div>
  <div id="tag-2"></div>
  <div id="tag-3" class="slick wicked"></div>
  <div class="parent">
    <div id="tag-4"></div>
  </div>
  <div class="parent">
    <div id="tag-5" class="slick"></div>
  </div>
  <div class="parent">
    <div></div>
    <div>
      <div id="tag-6"></div>
    </div>
  </div>
  <div class="parent">
    <div>
      <div id="tag-7" class="slick"></div>
    </div>
    <div></div>
  </div>
</div>
```

```CSS
#wall .tag-1 {
  display: none;
}

#wall .tag-1 + #tag-2 {
  display: none;
}

div#wall div#tag-3.slick {
  display: none;
}

#wall .parent #tag-4 {
  display: none;
}

div#wall .parent div#tag-5.slick {
  display: none;
}

div#wall div.parent div:last-child div#tag-6:nth-child(1) {
  display: none;
}

body div#wall div.parent div > div#tag-7.slick {
  display: none;
}
```
This is the end of this section and next I am going to start *__ Front-End - CSS Page Layout__* which is the last section in *__Intro to HTML/CSS__*

__I am almost there! :-)__

---

###### Saturday 4th August
+ I am working on *__Front-End - CSS Page Layout__* section and the first lesson is *__CSS Layout__* where I've learned about:
>* Box Model => margin (spacing inside an element), padding (spacing outside an element) and border.
>>* There are 2 different box models: The W3C box model used by Chrome, Firefox, opera and safari, and Internet explorer use its own box model.
>>* In W3C when you specify the width of an element it will just take into account the content area and not the padding and border while in Internet explorer it counts the content area, padding and border to calculate the width of an element.
>>* To solve this CSS3 introduced the `box-sizing` property and if we want the IE model the value should be `border-box` and if we want the W3C model then it should be `content-box`.
>>* This property has around 92% support across browsers.
>* Layout types => fixed (px), elastic (em), fluid (%) and using min/max sizing.
>>* Fixed layout (px):
>>>* Pros => widths are the same for all screens large and small.
>>>* Cons => A fixed-width layout may create excessive whitespace for users with larger screen resolutions.
Smaller screen resolutions may require horizontal scroll bar, depending the fixed layout's width.
>>* Elastic layout (em):
>>>* Pros => In responsive design up-scaling/down-scaling the text will keep the containers in proportion with their text content.
>>>* Cons => It takes a lot of savvy and testing to get the layout right for all users. Parent elements may begin to bump into each other as the type expands in size.
>>>* If I want to calculate from px to em then I will take the px number and divide it by *16px* (1em) then I will have the correct em size.
>>* Fluid layout (%):
>>>* Pros => Makes full use of the screen and can eliminate horizontal scroll bars in smaller screen resolutions.
>>>* Cons => The designer has less control over what the user sees with regards to container sizes and where type and media wraps.
>>* min-max sizing:
>>>* We can add `min-width` or `max-width` so the layout can be fluid until a `min-width` then we change it to fixed layout. We can also do that with height.
>* We can specify a `height` property for an element (div) and if the div height is less than the content we can use the `overflow` property to fix this.
>>* `overflow` property can have values such as *visible*, *hidden*, and *scroll* and *auto* which does the same job.
>>* *Fluid height* for ex. is to create an element that can extends from the top to the bottom and in this case we will have to create `height` property of 100% same as set the `width` to 100% but there is a difference between both properties:
>>>* `width` is by default set to 100%
>>>* `height` is by default only as tall as the content.
>>>* That is why we will need to add to `body` and `html` elements a `height: 100%` and a `min-height: 100%` so the height will be expanded to the whole page from top to bottom.
>* Elements display => inline, block and inline-block
>>* `display: inline` appears side by side does not accept width or top and bottom margins. They are as wide as the content. An example of inline element is `span` & `img`
>>* `display: block` displays one above the other, take up the whole line. Able to specify width, and top and bottom margins. Block elements such as `div`
>>* `display: inline-block` displays side by side, allows top and bottom margins and width to be specified.
>>* `display: table-cell` displays content in a table.
>* Floating: We use it to create column structure and it is two values are `left` or `right`. It won't affect the elements before it but it will affect the way the element that comes after the `float` property.
>>* That is why we use `clear` property:
>>>* `clear: left` => It will clear the height of anything that is floating left and not allowing the element to float left.
>>>* `clear: right` => It will clear the height of anything that is floating right and not allowing the element to float right.
>>>* `clear: both` => It will clear the height on both sides, right and left so the element will be displayed after the floating elements.
>>* Collapsed parents: If a parent element has floating children it might collapse and in this case we will need to add a *class* of `clearfix` for the parent in order to make the children inside the parent element again.
```CSS
.clearfix:after {
  /* content property is a ref. for how tall a parent should be and we will set visibility to hidden so we don't see that ref. */
  content: ".";
  display: block;
  clear: both;
  visibility: hidden;
  height: 0;
  line-height: 0;
}
```
>* Centring content in the middle of the page in any screen sizes we can add `margin: 0 auto` to the parent element.
>* *Positioning*: static, relative, fixed, absolute and sticky.
>>* `position: static` it is by default and it is always positioned according to the normal flow of the page. Static elements are not affected by the top, bottom, left, and right properties.
>>* `position: relative` is positioned relative to its normal position. We can add properties such as `top`, `right`, `left` or `bottom` if we want to change the position.
>>* `position: fixed` is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element.
>>* `position: absolute` is positioned relative to the nearest positioned ancestor(parent). If an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling.
>>* `position: sticky` is positioned based on the user's scroll position. It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place (like position:fixed).
>>>* `sticky` is not supported by earlier versions of IE so check what it does support.
>>>* Safari requires a -webkit- prefix `position: -webkit-sticky;`
>>>* Must specify at least one of `top`, `right`, `bottom` or `left` for sticky positioning to work.
>* Overlapping elements: after applying some positioning to elements we can work with `z-index` property.
>>* It specifies the stack order of an element (which element should be placed in front of, or behind, the others).
>>* An element can have a positive or negative stack order.
>>* By default any element starts with z-index of 0 and the higher the number the closer to the viewer the element will be.

---

###### Sunday 5th August
+ I worked on *__Code Along IV__* lab which is mainly to practise what I've learned in the CSS layout properties.

*__Note about Git:__* changes using Git. To do so, in Terminal type git add . and press return. Then type `git commit -m "add columns and fixed header and social bar"` and press return. Then push up this feature branch `git push -u origin columns` and press return. Next merge the changes into your master branch. Type `git checkout master` and press return, then `git merge columns` and press return. Then `git push origin master` and press return.

+ I worked on *__Green Grocer__* lab which wasn't easy and I spent some time to work on it!

There are few differences between my solution and Learn.co:

```Ruby
def consolidate_cart(cart)
  # code here
  new_hash = {}
  cart.each do |groceries|
    groceries.each do |item, item_data|
      if new_hash[item] == nil
        new_hash[item] = {}
        new_hash[item] = item_data
        new_hash[item][:count] = 1
      else
        new_hash[item][:count] += 1
      end
    end
  end
  new_hash
end
```
Learn.co solution:

```Ruby
def consolidate_cart(cart)
  cart.each_with_object({}) do |item, result|
    item.each do |type, attributes|
      if result[type]
        attributes[:count] += 1
      else
        attributes[:count] = 1
        result[type] = attributes
      end
    end
  end
end
```
>* They used `each_with_object({})` which saved lots of code comparing to my code.
>* They use a lot the boolean values without comparing the condition to equal true or false.
>>* In here `result[type]` is true which means there is that type already in result hash and that is why we are adding 1 and updating the value.
>>* If I want to compare it to false I will do `!result[type]`.

I want to start using `each_with_object({})` method to have clean and short codes.

```Ruby
def apply_coupons(cart, coupons)
  # code here
  result = {}
  cart.each do |item, item_data|
    result[item] = item_data
    coupons.each do |coupon|
      if item == coupon[:item] && item_data[:count] >= coupon[:num]
        item_data[:count] -= coupon[:num]
        if result["#{item} W/COUPON"] != nil
          result["#{item} W/COUPON"][:count] += 1
        else
          result["#{item} W/COUPON"] = {
            :price => coupon[:cost],
            :clearance => item_data[:clearance],
            :count => 1
          }
        end
      end
    end
  end
  result
end
```
Learn.co:

```Ruby
def apply_coupons(cart, coupons)
  coupons.each do |coupon|
    name = coupon[:item]
    if cart[name] && cart[name][:count] >= coupon[:num]
      if cart["#{name} W/COUPON"]
        cart["#{name} W/COUPON"][:count] += 1
      else
        cart["#{name} W/COUPON"] = {:count => 1, :price => coupon[:cost]}
        cart["#{name} W/COUPON"][:clearance] = cart[name][:clearance]
      end
      cart[name][:count] -= coupon[:num]
    end
  end
  cart
end
```
>* Same thing here they used the boolean true with `cart["#{name} W/COUPON"]` without comparing it with `true` keyword.
>* Here they update the cart instead of storing the result in a new hash.
>* In here they didn't use `each` with cart they just used it with coupon (the 2nd argument for this method)
>>* They didn't need to access nested cart arguments but they needed to do that with coupons to access each coupon.
>>* They only had to use the cart and access it with keys.
>* Those difference saved around 3-4 lines of code which is more neatly.

```Ruby
def apply_clearance(cart)
  # code here
  cart.each do |item, item_data|
    cart_item = cart[item]
    if cart_item[:clearance] == true
      cart_item[:price] = cart_item[:price] - (cart_item[:price] * 0.2)
    end
  end
  cart
end
```
Learn.co:

```Ruby
def apply_clearance(cart)
  cart.each do |name, properties|
    if properties[:clearance]
      updated_price = properties[:price] * 0.80
      properties[:price] = updated_price.round(2)
    end
  end
  cart
end
```
>* Here I am updating the cart as well instead of storing it in a new hash.
>* Again using the boolean value without comparing `properties[:clearance]`
>>*  Mathematically I did the discount percent (20%) multiplied by the original price then I subtract it from the original price.
>>* Learn.co they the took the rest of the value after the discount which is 80% percent (the new price of the item) and multiplied it by the original price then they added `round(2)` to the final price.

```Ruby
def checkout(cart, coupons)
  # code here
  total = 0
  consolidated_cart = consolidate_cart(cart)
  applied_coupons = apply_coupons(consolidated_cart, coupons)
  applied_clearance = apply_clearance(applied_coupons)
  applied_clearance.each do |k, v|
    total += v[:price] * v[:count]
  end
  if total > 100
    total *= 0.9
  end
  total
end
```
Learn.co solution:

```Ruby
def checkout(cart, coupons)
  consolidated_cart = consolidate_cart(cart)
  couponed_cart = apply_coupons(consolidated_cart, coupons)
  final_cart = apply_clearance(couponed_cart)
  total = 0
  final_cart.each do |name, properties|
    total += properties[:price] * properties[:count]
  end
  total = total * 0.9 if total > 100
  total
end
```
>* I believe this method is very similar to mine except using the conditional statement in the middle like this `total * 0.9 if total > 100`

*There are __so many__ ways to execute your code and have the same result.*

---

###### Tuesday 7th August
+ I worked on *__Emoticon Translator__* lab and it was so fun to learn about a new human-readable data serialisation language *YAML*

>* *YAML* is a recursive acronym for "YAML Ain't Markup Language". YAML is used because it is easier for humans to read and write than typing out entire arrays, hashes, etc.
>* This module provides a Ruby interface for data serialisation in YAML format.
>* You can choose from one of two YAML engines that ship with Ruby 1.9. By default *Psych* is used but the old unmaintained *Syck* may chosen.
>* To load the file in the Ruby file:
```Ruby
require "yaml"
var = YAML.load_file('file.yml')
```
>* If we have a `.yml` file that contains an array, this is how it will look like:
```YAML
---
# fruits.yml
- Apple
- Orange
- Strawberry
- Mango
---
```
The result will be:
 ```YAML
require "yaml"
fruits = YAML.load_file('fruits.yml')

fruits
# => ["Apple","Orange","Strawberry","Mango"]
 ```
>* What if we have a file of hash?
```YAML
---
# government.yml
president: Barack Obama
vice president: Joe Biden
secretary of state: John Kerry
secretary of the treasury: Jacob Lew
---
```
The result is:
```YAML
require "yaml"
gov = YAML.load_file('government.yml')

gov
# =>
# {
#   "president" => "Barack Obama",
#   "vice president" => "Joe Biden",
#   "secretary of state" => "John Kerry",
#   "secretary of the treasury" => "Jacob Lew"
# }
```
+ The lab is about translating the Japanese emojis to English ones and the meaning of it as emotion. We have a `.yml` file which contains a hash of emotions as keys and each emotion has 2 emojis, one eng and the other jpn.

```Ruby
def load_library(file_path)
  # code goes here
  emoticons = YAML.load_file(file_path)
  emoticons_library = {
    "get_emoticon" => {},
    "get_meaning" => {}
  }

  emoticons.each do |emotion, emoticons|
    eng = emoticons[0]
    jpn = emoticons[1]
    emoticons_library["get_emoticon"][eng] = jpn
    emoticons_library["get_meaning"][jpn] = emotion
  end
  emoticons_library
end
```

Learn.co result:

```Ruby
def load_library(file_path)
  library = {"get_meaning" => {}, "get_emoticon" => {} }
  YAML.load_file(file_path).each do |meaning, array|
    english, japanese = array
    library["get_emoticon"][english] = japanese
    library["get_meaning"][japanese] = meaning
  end
  library
end
```
>* In Learn.co they didn't store the file loading in a variable and they just used it straight away with `#each`
>* I stored the eng & jpn emoticon each in a var but Learn.co had 2 vars and initialised the array of emoticons to it. NOT sure how is that possible and this is the 1st time to see it. The rest is a similar concept.

```Ruby
def get_japanese_emoticon(file_path, eng_emoticon)
  # code goes here
  jpn_emoticon = load_library(file_path)["get_emoticon"][eng_emoticon]
  jpn_emoticon ? jpn_emoticon : "Sorry, that emoticon was not found"
end

def get_english_meaning(file_path, jpn_emoticon)
  # code goes here
  get_meaning = load_library(file_path)["get_meaning"][jpn_emoticon]
  get_meaning ? get_meaning : "Sorry, that emoticon was not found"
end
```
Learn.co:

```Ruby
def get_japanese_emoticon(file_path, emoticon)
  library = load_library(file_path)
  result = library["get_emoticon"][emoticon]
  if result
    result
  else
    "Sorry, that emoticon was not found"
  end
end

def get_english_meaning(file_path, emoticon)
  library = load_library(file_path)
  result = library["get_meaning"][emoticon]
  if result
    result
  else
    "Sorry, that emoticon was not found"
  end
end
```
>* This time Learn.co stored the file loading a var but I used the loading straight away.
>* I used a ternary operator instead of if/else.

---

###### Wednesday 8th August
+ I worked on *__Zesty__* lab in *__CSS Page Layout__* section and I coded the site almost from scratch with HTML5 and CSS3.
>* I learned a bit about transitions and I've done lots of pseudo classes work such as `:hover` and most of the selectors were by tag name, descendants and ID.
>* I used *HTML5* tags such as `<header>`, `<section>` and `<footer>`.

Check my code at *__fe-zesty-prework__* Github repo.

+ Finallyyyyy! I finished *__Intro to Ruby__* section. The last lab called *__Alphabet in Esperanto__* and it was part of in *__Advanced Hashes__*.
>* The lab was about sorting an array of sentences according to Esperanto alphabets which is one of the most popular international auxiliary languages.
>* It was recommended to use `sort_by` and it was the 1st time to check it and work with this method.
>* I've done some research to check how this method works behind the scenes like so many methods for ex. `<=>` spaceship operator which is used to compare two elements at the same time and the method use it behind the scenes is `sort`.

Here is my solution:

```Ruby
def alphabetize(arr)
  # code here
  esperanto_alphabet = "abcĉdefgĝhĥijĵklmnoprsŝtuŭvz"
  arr.sort_by do |phrase|
    phrase.split("").collect do |character|
      esperanto_alphabet.index(character)
    end
  end
end
```

Learn.co:

```Ruby
ESPERANTO_ALPHABET = " abcĉdefgĝhĥijĵklmnoprsŝtuŭvz"
def alphabetize(arr)
  arr.sort_by { |a| a.split("").map{ |char| ESPERANTO_ALPHABET.index(char) } }
end
```

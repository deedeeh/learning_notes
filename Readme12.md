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

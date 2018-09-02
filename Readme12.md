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

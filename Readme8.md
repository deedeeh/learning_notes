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

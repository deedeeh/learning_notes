### MY LEARNING NOTES

#### Example

+ Learn more Vanilla JS and document the outcome and share it on Github.
+ Build more projects to build my portfolio and learn through the process.

```JavaScript
function removeTransition(e) {
  if (e.propertyName !== 'transform') return;
  e.target.classList.remove('playing');
}
```

Currently I am doing a Web Developer Bootcamp on Udemy by Colt Steele who is a developer and bootcamp instructor.

The course covers Frontend which I have some of its skills and Backend which I know nothing about! It is a good opportunity to learn new technologies that will help me in my career and understand what happens under the hood.

###### Tuesday 6th of March
I did an *Image Blog* using HTML and CSS as part of the Bootcamp Intermediate CSS section and next I will be creating a Blog.

Here are few lines of my stylesheet:

```CSS
.title {
  margin-left: 1.66%;
  font-family: 'Raleway', sans-serif;
  font-weight: 800;
  font-size: 24px;
  text-transform: uppercase;
  border-bottom: 1px solid #000;
  width: 30%;
  padding-bottom: 20px;
}
```

I created a *Blog* using HTML5 and CSS and I really enjoyed building it and it didn't take time.

```HTML
<article>
  <p class="date">November 23 2015</p>
  <h1 class="heading">This is my first article</h1>
  <p class="border-left">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat ut enim ad minim veniam sed do eiusmod tempor.</p>
  <p>Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt.</p>
  <p>Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem.</p>
</article>
```

```CSS
.date {
  color: #3498db;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: .2em;
}

.heading {
  color: #2c3e50;
  font-size: 2em;
  font-weight: 900;
  text-transform: capitalize;
  letter-spacing: 1px;
}

.border-left {
  border-left: 6px solid #bdc3c7;
  padding-left: 6px;
}
```

---
title: Homework 2
layout: default
---

## Homework 2: JavaScript, JQuery

This assignment assigned us with the task of creating a webpage that takes user input and changes the page in some way using the input.
- The assignment page is [here](http://www.wou.edu/~morses/classes/cs46x/assignments/HW2.html).
- The completed assignment can be found [here](http://www.wou.edu/~bbauer15/cs460/homework%202/).
- Repo is [here](https://bitbucket.org/blakebauer/cs460/).

Resources:
+ [W3Schools](https://www.w3schools.com/)
+ HTML CSS and JS interactive cheat sheets [here](http://html-css-js.com/)

Table of contents:
+ [JavaScript](#javascript)
+ [CSS](#jquery)
+ [The Assignment](#the-assignment)

### JavaScript:

JavaScript is a pretty simple language used by webpages and browsers to render dynamic webpages.

JavaScript is dynamically typed. Variables are declared with var. It also doesn't have type errors, operations are unsafe.
```javascript
var x = 5
var y = 3
x = "Moo"
x + y   // = "Moo3"
x - y   // = NaN
[] - {} // = NaN
{} - [] // = -0
{} + [] // = 0
```

JavaScript numbers are all one type. The following are all type Number
```javascript
var x = 1
var y = 1.2
var z = 34e7
```

JavaScript has booleans as well. With all the common conditionals
```javascript
var x = true
var y = false
if(((x || y && true) || 7 == 9) && 1 >= 2){
  x = "I am a string"
}
```

Arrays or lists are defined as usual although they can hold multiple types.
```javascript
var stuff = ["a", 'b', 1, 2, [3, 4]]
```

JavaScript has what are called "objects" which is a list defined by {} with key-value pairs
```javascript
var dog = {
  name: 'Chloe',
  age: 15
}

dog.name == 'Chloe'
dog.age == 15
```

Functions can be assigned to variables and 'moved' around.
```javascript
var x = function(a){
  return a*a;
}

x(2) == 4;
```

JS has standard for loops as well as for/in loops that iterate over keys of an object.
```javascript
for (i = 0; i < 5; i++) {
    x += i*i;
}

var text = '';
for (key in dog) {
  text += dog[key] + " ";
} 
text == 'Chloe 15 '
```
It also has standard while and do while loops.

Built-in Regex W3Schools has a good page [here](https://www.w3schools.com/js/js_regexp.asp).

Running JS in html is done with the script tag.
```html
<script>
      //embedded JS
      element.style.color = "#ff00ff";
</script>

<script src="Some js file.js"></script>
```

Accessing and modifing html elements in js is done in two ways. First, through the document variable.
```javascript
var element = document.getElementById("id_of_element");
element.innerHTML = "New text";
element.style.color = "red";
```

The second is using:

### JQuery

JQuery is a addon for JS that more or less adds the use of CSS selectors to find elements in a minimal syntax fashion.

The basic syntax is $('selector')
```javascript
$('div.container');                     // Returns a list of all divs with class container
$('div.container').style.color = 'red'; // Sets all div.container's color to red
```

JQuery has a nice interface for working with html events.
```javascript
$("button").click(function(){
  $(this).hide();               //this keyword grabs the html element that called the function
});

$("#title").hover(function(){
  //Entered
},
function(){
  //Exited
});
```

JQuery also has the ability to animate CSS properties. !!CSS properties must be camelCased e.g. padding-left = paddingLeft.
```javascript
$('#some_button').click(function(){
  $('#some_div').animate({
    left: '200px',
    width: '100px',
    //Any other css property
  });
});
```

### The Assignment:
For this assignment I made a scheduler where one inputs their events for the week and it generates a nice schedule for them. It has several customization proerties such as color, start time, end time, and time interval. There is a few things I left out like selecting the days and wrapping events from one day to the next.

![Cite_Image](full_cite_shot.png)

This is the basic layout. The general schedule options are at the top as well as the generate button.

One of the color pickers followed by the generate button:
```html
<label class="control-label col-sm-2 col-sm-offset-1" for="border_color">Border Color:</label>
<input type="color" class="form-control" name="border_color" value="#000000">

<button type="button" class="btn" id="genBtn" onclick="generateSchedule();">Generate Schedule</button>
```

Each event on the calender is inputted in one of the small blue forms. The page starts with 1 event and more can be added by clicking the plus. After clicking the plus the following will be added and the plus will move over.

![New Event](new_event.png)

Unlike the starting event, the extra ones have an X button which deletes them.

The X button:
```html
<button type="button" class="btn btn_ev_delete col-sm-1" onclick=\'$("#event_n").remove();\'>X</button>
```
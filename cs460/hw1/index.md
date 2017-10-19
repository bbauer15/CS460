---
title: Homework 1
layout: default
---

## Homework 1: Git, HTML, CSS, BootStrap

This first homework tasked us with developing a small series of webpages that meet a certain criteria using HTML, CSS, and BootStrap. At the same time we were to use git through the command line to commit to a repo regularly. 
- The assignment page is [here](http://www.wou.edu/~morses/classes/cs46x/assignments/HW1.html).
- The completed assignment can be found [here](http://www.wou.edu/~bbauer15/cs460/homework%201/home.html).
- Repo is [here](https://bitbucket.org/blakebauer/cs460/).

Resources:
+ [W3Schools](https://www.w3schools.com/)
+ HTML CSS and JS interactive cheat sheets [here](http://html-css-js.com/)

Table of contents:
+ [Git](#git)
+ [HTML](#html)
+ [CSS](#css)
+ [Bootstrap](#bootstrap)
+ [The Assignment](#the-assignment)

### Git:

The first steps were to create a local git repo and connect it to a github or bitbucket and/or clone one. I went with github for the time being.

To clone a git repo such as github:
```bash
git clone https://github.com/{username}/{project}.git
```

To initialize a local repo and connect it:
```bash
git init
git remote add https://github.com/{username}/{project}.git
git pull
```

To configure the git user:
```bash
git config --global user.name "Blake Bauer"
git config --global user.email bbauer15@wou.edu
```

Git has several commands:
- __**add** *file*__ stages *file* so it can be commited
- __**commit** *-m "commit message"*__ does a local commit 
- __**push** *remote branch*__ pushs to the remote repo
- __**merge** *branch*__ merges the active branch into *branch*
- __**fetch** *remote branch*__ fetchs from the remote
- __**pull** *remote branch*__ fetchs and merges from the remote

Example:
```bash
git add file.html
git commit -m "Added file.html"
git push origin master

//Other machine
git pull
```

### HTML:

HTML is quite a simple language. It is basically just a hierarchical set of elements.

The basic syntax:
```html
<tag atribute=value>
    Some text
</tag>
```

There are several tags that have certain properties and do certain things.

A few examples:
```html
<a href="web/address">I am a link</a>
<p>I am a paragraph</p>
<ol>
    <li>Lists</li>
    <li>are</li>
    <li>cool!</li>
</ol>
<div>
    Divs are used as a basic separator
</div>
```
---
<a href="#">I am a link</a>
<p style="color:red;">I am a red paragraph</p>
<ol>
    <li>Lists</li>
    <li>are</li>
    <li>cool!</li>
</ol>
<div>
    Divs are used as a basic separator
</div>
---

There are a few special attributes:
- **class** is used a lot
- **id** is used as a unique identifier
- **href** for links
- **style** for inline CSS styling

Every document needs an html, head, and body element. Head is used for some initializing for stuff like CSS and Javascript. Body is where the content of the webpage is.

An example with a title and CSS stylesheet:
```html
<html>
<head>
    <meta charset="utf-8">
    <title>Title of the tab</title>

    <link rel="stylesheet" href="style.css">
</head>

<body>
I am the body.
</body>
</html>
```

### CSS:

HTML on its own can't do much; but, in conjecture with CSS styling it can look really cool.

Like HTML, CSS is rather simple.

Basic syntax:
```css
selector {
    attribute: value;
}
```

Selectors are a form of regular expression. They specify what elements the styling should be applied to.

Examples:
+ \* (selects everything)
+ tag
+ .class
+ #id
+ parent > child
+ parent descendant
+ sibling ~ sibling
+ tag + immediate sibling
+ tag[attribute="value"]
+ tag:psuedo-class

They can be combined in all sorts of ways.

```css
#navbar < ul < li.active < p a {
    color: red;
}
```

Selects all links that are a descendant of paragraphs which are children of a list item that has a class *active* which is a child of an un-ordered list which is a child of an element with the id *navbar*.

The styling is rather simple. Just assigns the value to the attribute for all elements that the selector picks out.

```css
div {
    background-color: #ffffff;
    color: blue;
    border: 10px;
}
```

The more specific a selector, the higher the precedence.

### Bootstrap:

Bootstrap is a libary used for created very nice looking webpages easily and quickly.

Bootstrap has a grid system that can be used to split the webpage into segments to easily position elements side by side or off to the left and so on. The grid system has properties to change depending on the screen size so one webpage can look good on several screen sizes. 

To use the grid system a *row* tag is used to classify a row and each row has 12 columns. The columns are specified using a *dev* tag and a class *col-xx-yy* where xx is the smallest size where the columns don't break apart. That is, if your device is smaller the size then the columns will arrange vertically instead of horizontal. yy is the amount of columns to take up. If the total number of columns in a row exceeds 12 then the last column will break off to a new row.

A 3 columns layout with two large columns and a small column in the center.
```html
<row>
    <div class="col-md-5">
        1
    </div>
    <div class="col-md-2">
        space
    </div>
    <div class="col-md-5">
        2
    </div>
</row>
```

The arguments for the columns are optional:
```html
<row>
    <div class="col">
        1
    </div>
    <div class="col">
        2
    </div>
    <div class="col">
        3
    </div>
</row>
```
3 Equal width columns.

Bootstrap has tables:
```html
<table class="table">
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
            <th>Header 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>2</td>
            <td>3</td>
        </tr>
        ...
    </tbody>
</table>
```

Bootstrap has several other classes like Buttons, List Groups, Progress Bars, Forms, Inputs, NavBars, etc. 

NavBars come in many different shapes and looks. A simple example:
```html
<nav class="navbar navbar-default">
    <div class="container-fluid">
        <div class="navbar-header">
            <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#navbar1"> 
                <span class="icon-bar"></span>   
                <span class="icon-bar"></span>     
                <span class="icon-bar"></span>         
            </button>
            <a class="navbar-brand" href="#">LOGO</a>
        </div>
        <div class="collapse navbar-collapse" id="navbar1">
            <ul class="nav navbar-nav">
                <li><a href="#">Link 1</a></li>
                <li><a href="#">Link 2</a></li>
            </ul>
        </div>
    </div>
</nav>
```
When this navbar gets to small it hides the items into a collapsable menu that opens with a button!

### The Assignment:
The completed assignment can be found [here](http://www.wou.edu/~bbauer15/cs460/homework%201/home.html).

For the assignment I took an old assignment I had from Math 280 Introduction To Proofs where we had to write a paper on the different forms of mathematical proofs. I took that assignment and made it into a website. I have 5 pages in total: Home, Direct Proofs, Proof by Cases, Proof by Contradiction, and Proof by Induction.

The website has a nice looking navbar the code is not much different from the example above.
```html
<nav class="navbar navbar-default">
    <div class="container-fluid">
        <div class="navbar-header">
            <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#navbar1"> 
                <span class="icon-bar"></span>   
                <span class="icon-bar"></span>     
                <span class="icon-bar"></span>         
            </button>
            <a id="logo" class="navbar-brand" href="#">B<sup>2</sup></a>
        </div>
        <div class="collapse navbar-collapse" id="navbar1">
            <ul class="nav navbar-nav">
                <li><a href="direct.html">Direct Proofs</a></li>
                <li><a href="cases.html">Proof by Cases</a></li>
                <li><a href="contradiction.html">Proof by Contradiction</a></li>
                <li><a href="induction.html">Proof by Induction</a></li>
            </ul>
        </div>
    </div>
</nav>
```

The styling took a little while to find a few things.
```css
.navbar {
    background: #b5e0ff;
    border-radius: 0;
    border: 0px;
}

#logo {
    color:#0f0f0f;
    font-size: 22pt;
}

#navbar1 li > a {
    font-size: 13pt;
    color: #1f1f1f;
}
```
Changes the font colors and background colors as well as font size.

The hover color needed to be changed to white to see it better with the darker text. The active color I changed to a darker blue instead of grey.
```css
#navbar1 li > a:hover, #logo:hover {
    color: white;
}

#navbar1 li.active > a {
    background-color: #95c0df;
}
```
The ids were necessary because bootstraps styling was much more specific then what was reasonable so it took precedence.

On the home page I had a list of axioms and the sort, that were numbered oddly so I used a dl list.
```html
<dl>
    <dt>Axiom 1:</dt>
    <dt>Axiom 2:</dt>
    <dt>Theorem 1:</dt>
</dl>
```

The Proofs by Cases document I made use of the grid system to put the two cases side by side.
```html
<row>
    <div class="col-md-6">
        <h4>Case 1:</h4>
        ...
    </div>
    <div class="col-md-6">
        <h4>Case 2:</h4>
        ...
    </div>
</row>
```

They have some styling to seperate them a bit and give them rounded corners.
```css
.col-md-6 {
    border: 3px solid #f5f5f5;
    border-radius: 1em;
    background: #e9e9e9;
    padding: 1em; 
}
```

The Induction page has a lot of stuff including a table with some inline styling.
```html
<center style="font-size: 12pt;">
    <table class="table table-bordered" style="text-align: right; width: 50%;">
        <thead>
            <tr>
                <th>n</th>
                <th>
                    <equ>(3<sup>2n</sup>-2<sup>n</sup>)</equ>
                </th>
                <th>
                    <equ>(3<sup>2n</sup>-2<sup>n</sup>)</equ> / 7
                </th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>7</td>
                <td>1</td>
            </tr>
            <tr>
                <td>2</td>
                <td>77</td>
                <td>11</td>
            </tr>
            ...
        </tbody>
    </table>
</center>
```

I also used my own tag which ended up not having a lot of formatting.
```html
<equ>
    1 + 1 = 2
</equ>
```

```css
equ {
    font-family: monospace;
}
```
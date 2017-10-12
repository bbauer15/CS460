---
title: Homework 1
layout: default
---

## Homework 1: Git, HTML, CSS, BootStrap

This first homework tasked us with developing a small series of webpages that meet a certain criteria using HTML, CSS, and BootStrap. At the same time we were to use git through the command line to commit to a repo regularly. The assignment page is [here](http://www.wou.edu/~morses/classes/cs46x/assignments/HW1.html).

### Git:

The first steps were to create a local git repo and connect it to a github or bitbucket and/or clone one. I went with github for the time being.

To clone a git repo such as github:
```bash
git clone https://github.com/{username}/{project}.git
```

To initilize a local repo and connect it:
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

Like HTMl, CSS is rather simple.

Basic syntax:
```css
selector {
    attribute: value;
}
```

Selectors are a form of regular expression. They specify what elements the styling should be applied to.

Examples:
+ * (selects everything)
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

Selects all links that are a descedant of paragraphs which are children of list items which is a child of a unordered list which is a child of an element with the id navbar.

The styling is rather simple. Just assigns the value to the attribute for all elements that the selector picks out.

```css
div {
    background-color: #ffffff;
    color: blue;
    border: 10px;
}
```

The more specific a selector is the higher the precedence.
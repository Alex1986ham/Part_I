# Part_I

## How to open files, read out information of files, close files:

## use the functin "open". 

		Built-in Functions		
abs()	dict()	help()	min()	setattr()
all()	dir()	hex()	next()	slice()
any()	divmod()	id()	object()	sorted()
ascii()	enumerate()	input()	oct()	staticmethod()
bin()	eval()	int()	open()	str()
bool()	exec()	isinstance()	ord()	sum()
bytearray()	filter()	issubclass()	pow()	super()
bytes()	float()	iter()	print()	tuple()
callable()	format()	len()	property()	type()
chr()	frozenset()	list()	range()	vars()
classmethod()	getattr()	locals()	repr()	zip()
compile()	globals()	map()	reversed()	__import__()
complex()	hasattr()	max()	round()	 
delattr()	hash()	memoryview()	set()	 


# To do, before submiting a repo

- Add docstrings to each 'class' and each 'def'
- Check the whole document through 'POP8 online' for identation and so on


# HTML and CSS Skills

IDs for example in <p id="something"> could be used just once in a webpage.

In this example:

<p class="highlight module right"></p>
.right {
color: green;
}

The class will be changed in color. Because its enought that the class just contains the word right.


CSS References
Mozilla Developer Network - CSS Reference
css-tricks.com - CSS Almanac


# DevTools

- For Chrome look this up: https://developers.google.com/web/tools/chrome-devtools/
- For Edge look this up: https://docs.microsoft.com/de-de/microsoft-edge/devtools-guide
- For Safari look this up: https://developer.apple.com/safari/tools/

# Setting Colors in CSS 

## RGB
Red 0 - 255 (255 means full light; 0 means no light
Green 0 - 255
Blue 0 - 255
background-color: rgb(255, 0, 255);

## Hexadecimal

Red 00-FF
Green 00-FF
Blue 00-FF
background-color: #FF00FF;

# Styling of curser

https://css-tricks.com/almanac/properties/c/cursor/

# Designing a border

https://developer.mozilla.org/en-US/docs/Web/CSS/border

# Box shadow generator

https://www.cssmatic.com/box-shadow

# Refering from html to a css stylesheet

<head>
  <meta charset="UTF-8">
  <title>Web Dev Blog Post</title>
	<link rel="stylesheet" href="styles.css">


# Positioning in CSS

## Inline-Block
- box-sizing: border-box; for sizing the border box
- display: inline-block; for sizing a span inline block (it positions elements in one line, but not if two divs are positions under each other
- position: relative; The relative flow is a variant of the normal flow and behaves basically the same. But, the relative flow adds some new abilities.
In case of this:
'
.shift {
  position: relative;
  top: 10px;
  left: 10px;
}
'
position: relative; change the position of the box to top 10px and left 10px

## Position fixed

position: fixed; this element will be always in the viewpoint of the user, use this especially for navigation tools

Right! You only need position: fixed and bottom: 0px to make a sticky footer!

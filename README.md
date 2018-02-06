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

In the case of position: absolute, the element is positioned relative to its parent before the rest of the normal flow occurs. Its siblings in the normal flow ignore it and are laid out as if it were not there. Frankly, position: absolute is best thought of as a last resort. If all the other flows fail, then maybe absolute is your best option. Off the top of my head, I can't actually think of an instance where I wanted to use position: absolute. 
Transform is a better solution to absolute: here is a link to it: https://developer.mozilla.org/en-US/docs/Web/CSS/transform

## Inline Formatting

Horizontal alignment starts with another property, direction, which has two options: ltr and rtl. Besides that, use text-align left, right, and center.

vertical-align: text-top, vertical-align: text-bottom and vertical-align: middle are options for aligning text to the eponymous locations in the parent.

vertical-align: top and vertical-align: bottom will align with the line instead.

### CSS properties:
- display
- position
- text-align
- vertical-align

## Floats inside of a container

.left {
      float: left;
     
With overflow: auto, the "new context" element respects the boundaries of the two children. No overlap! Try toggling overlap: auto to see what happens if it isn't applied.

clear: left indicates that the top of the element must be below any left floated elements that appear before this one in the document. clear: right acts the same, but with right floated elements. clear: none means that there are no restrictions; this is the default value.

  .bordered {
      border: 2px solid #2e3d49;
    }
    .left {
      float: left;
      background-color: #FD9F0E;
    }
    .right {
      float: right;
      background-color: #FD9F0E;
    }
    .clear-left {
      clear: left;
    }
    .clear-right {
      clear: right;
    }
    .clear-both {
      clear: both;
    }
    .wide {
      width: 40%;
    }
  </style>
  

## obsvgtxtlayout
###Chapter 1. Understanding
###Chapter 2. SVG Text Basics
####Letters on a Page
text position - viewBox
- A number without units is interpreted as that number of user units in the current coordinate system.
- Lengths with units are scaled according to the viewBox or transformations in effect. CSS px units are always interchangeable with SVG user units.
- Percentages are relative to the width or height specified in the viewBox of the nearest <svg> or <symbol> element (or the actual width and height, if no viewBox was given).  

```
Any text content within an SVG that isn’t inside a <text> element will not be displayed. 
```
ex:
```
<svg xmlns="http://www.w3.org/2000/svg"
     xml:lang="en"
     width="4in" height="0.8in" viewBox="0 0 400 80" >
    <title>Basic SVG Text</title>
    <rect width="100%" height="100%" fill="lightYellow" />
    <text x="10px" y="80%">SVG Text</text>
</svg>
```
for text transformation the following are same:
```
<text transform="translate(10,64)">SVG Text</text>    //64 =80*80%
<text x="10px" transform="translate(0,64)">SVG Text</text>
<text y="80%" transform="translate(10,0)">SVG Text</text>
<text x="50px" y="-20%" transform="translate(-40,80)">SVG Text</text>
```
####Big Words, Little Words
There is another reason to always set a font size for text within an SVG image.   
The text is being drawn in a custom coordinate system and will scale with the image.  
The ratio of the font size to the image size is kept constant, but the actual final font size on screen can vary.  
####Styling Text
```
font-size-adjust, font-stretch  //no browsers support these two currently
```

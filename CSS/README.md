# Basic CSS
**Select by tag, id or class:**
```css
input{}
#id{}
.class{}
```

**Select by attribute :**
```css
tag[attr=value]{}
```

**Override CSS :**
The last declared class take precedence id attribute will always take precedence on classes independently of the orderinline styles always take precedence on classes and id

**Override All Other Styles by using Important :**
```css
.class {
    property: value !important; 
}
```

**CSS Variables:**
```css
:root{ 					/* other_class inherit from class, root is the html element  */
	--variable_name: value;		/* globale variable */
}

.class {
	--variable_name: value;
}

.other_class {
	property: var(--variable_name, fallback_value);
}

```

# Applied vidual design

**Text formating**
```css
.class{
	font-family: monospace;
	font-size: 14px;
	text-align: left;				/* right, center or justify */
	text-decoration: underline;			/* <u></u> */
	font-weight: bold;				/* <strong></strong> */
	font-style: italic;				/* <em></em> */
	text-decoration: line-through;			/* <s></s> */
	text-transform: uppercase;			/* lowercase, uppercase, capitalize, initial, inherit, none(default) */
	line-height: 25px; 				/* hange the height of each line in a block of text */
}
```

**A pseudo-class is a keyword that can be added to selectors, in order to select a specific state of the element**
```css
a:hover {
  color: red;
}
```

**Position Elements**
```css
p {
  position: relative;			/* Relative to its current position in the normal flow of the page */
  bottom: 10px;				/* top, left, right: offests */
  z-index: number;			/* specify the order of how elements are stacked on top of one another */
}

p {
  position: absolute;			/* Lock an element in place relative to its parent container */
  bottom: 10px;				/* top, left, right: offests */
}

.navbar {
  position: fixed;			/* Lock an Element to the Browser Window */
  bottom: 10px;				/* top, left, right: offests */
}

.navbar {
  float: left;				/* rigt: push the element to the left or right of it containing parent element */
}

div {
	margin: auto;			/* center a block element horizontally */
}

```
**Transform Elements**
```css
div:hover {
  transform: scale(1.5);		/* scale the element to 1.5 times it original size */
  transform: skewX(-32deg);		/* skews the selected element along its horizontal axis by a given degree */
  transform: skewY(-32deg);		/* skews the selected element along its vertical axis by a given degree */
  transform: rotate(-45deg);
}
```

**@keyframes and animation Properties**
```	css
@keyframes colorful {              		/* create the animation */
  0% {
    background-color: blue;
  }
  100% {
    background-color: yellow;
  }
}

#anim {                                  	/* use the animation */
  animation-name: colorful;        
  animation-duration: 3s;
  animation-fill-mode: forwards;       		/* specifies the style applied to an element when the animation has finished */
  animation-iteration-count: number;		/* infinite, control how many times to loop through the animation */
}
```

# Responsive web-design principles
**Media Queries:**
Media Queries are a new technique introduced in CSS3 that change the presentation of content based on different viewport sizes. The viewport is a user's visible area of a web page, and is different depending on the device used to access the site.
```css
@media (min-height: 350px) { 
	/* CSS Rules */ 
}

img {	/* make an image repsonsive */
	display: block;
	max-width: 100%;
	height: auto;
}
```

# CSS Flexbox
Flexbox container properties
```css
.flex_container {
	display: flex; 
    flex-direction: row;         	/* row-reverse, column, column-reverse */
    justify-content: flex-start; 	/* flex-end, space-between, space-around, space-evenly to allign items on the main axis */
    align-items: stretch;        	/* flex_start, flex-end, center, baseline to allign items on the cross axis */
    flex-wrap: nowrap;           	/* wrap, wrap-reverse to split a flex item into multiple rows (or columns) */
}
```
Flexbox container properties
```css
.flex_item {
	flex-shrink: 1;          		/* To Shrink Items, the higher the number, the more it will shrink compared to the other items in the container */
	flex-grow: 1;            		/* to Expand Items */ 
	flex-basis: 10em;        		/* to Set the Initial Size of an Item */
	flex: 1 1 10em;          		/* shortcut to flex-grow, flex-shrink, and flex-basis */
	order: value;            		/* to Rearrange Items */
	align-self: flex-start;  		/* flex-end, center to adjust each item's alignment individually */
}
```

# CSS Grid
Gird container properties
```css
.grid_container {
	display: grid;
	grid-template-columns: 50px 50px;   	/* create two columns that are each 50px wide on the grid (fr, auto, %) */
	grid-template-rows: 50px 50px;      	/* create two rows that are each 50px tall on the grid (fr, auto, %) */
	grid-column-gap: 10px;              	/* create a Column Gap */
	grid-row-gap: 5px;                  	/* create a row gap */
	grid-gap: 10px 5px;               	/* the first one to set the gap between the rows and the second value for the columns */
	justify-items: stretch;             	/* center, start, end align all the items horizontally */
	align-items: stretch;               	/* center, start, end align all the items vertically */
	grid-template-areas:                	/* Divide the Grid Into an Area Template */
  		"header header header"
  		"advert content content"
  		"advert footer footer";
	grid-template-rows: repeat(100, 50px);     		/* Create the 100 row grid, each row at 50px tall */
	grid-template-columns: 100px minmax(50px, 200px);	/* Limit Item Size Using the minmax Function */
	grid-template-columns:                           	/* Create Flexible Layouts */
		repeat(auto-fill, minmax(60px, 1fr));
	grid-template-columns:                           	/* Create Flexible Layouts */
	repeat(auto-fit, minmax(60px, 1fr)); 

}
```
Gird item properties
```css
.grid_items {
	grid-column: 1 / 3;                 			/* To control the number of columns an item will consume start/stop */
	grid-row: 1 / 3;                    			/* To control the number of rows an item will consume start/stop */
	justify-self: stretch;              			/* center, start, end to align the content's position within the cell horizontally */
	align-self: stretch;                			/* center, start, end to align the content's position within the cell vertically */
	grid-area: header; 					/* place an item in a custom area by referencing the name */
	grid-area: col_start/row_start/col_end/row_end;     	/* place an item in a custom area without a template */
}
```

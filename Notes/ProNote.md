<a name="top"></a>
# Processing Notes

### [Processing Basics](#basics)
### [Function](#function)


<a name="basics"></a>

## Processing Basics

Processing uses functions to create visuals.

### Terminology

###### Stroke

Outline of a shape

###### Fill

Anything inside of stroke.

### Rules

* When there are multiple codes, first code will be dislpayed on the bottom, later codes will be displayed on top of the previous ones.

* To color a shape, call color function before the defining the shape.

<a name="function"></a>

## Function

###### Rectangle

Syntax: 

	rect(a, b, c, d);

a: float x-coordiante of upper-left corner

b: float y-coordiante of upper-left corner 

c: float width

d: float height

Return type: void

![Rectangle](./images/rect1.png) rect(30, 20, 55, 55);


Syntax: 

	rect(a, b, c, d, r);

r: float radii for all corners

![Rectangle2](./images/rect2.png) rect(30, 20, 55, 55, 7);

Syntax:

	rect(a, b, c, d, tl, tr, br, bl);

tl: float radius for top-left

tr: float radius for top-right

br: float radius for bottom-right

bl: float radius for bottom-left

![Rectangle3](./images/rect3.png) rect(30, 20, 55, 55, 3, 6, 12, 18);

###### Ellipse

Syntax:

	ellipse(a, b, c, d);

a: float x-coordinate (center)

b: float y-coordinate (center)

c: float width (diameter)

d: float height (diameter)

Return type: void

![Ellipse](./images/ellipse1.png) ellipse(56, 46, 55, 55);

<a name="top"></a>
# Processing Notes

[Processing Basics](#basics)

[Function](#function)

[Color](#color)


<a name="basics"></a>

## Processing Basics 
[Top](#top)

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
[Top](#top)

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

<a name="color"></a>

## Color
[Top](#top)

###### Outline color

Syntax:

	stroke(rgb);
	stroke(gray);

rgb: int rgb in hexadecial

gray: float a value between black adn white (0 = black, 255 = white)

Return type: void

![Color1](./images/color1.png) stroke(153); rect(30, 20, 55, 55);

Syntax:

	stroke(rgb, alpha);
	stroke(gray, alpha);

alpha: float opacity of the outline

Syntax:

	stroke(v1, v2, v3);
	stroke(v1, v2, v3, alpha);

v1: float red or hue value

v2: float green or saturation value

v3: float blue or brightness value

![Color2](./images/color2.png) stroke(204, 102, 0); rect(30, 20, 55, 55);


###### color inside of a shape

Syntax:

	fill(rgb);
	fill(gray);

rgb: int rgb in hexadecial

gray: float a value between black adn white (0 = black, 255 = white)

Return type: void

![Color3](./images/color3.png) fill(153); rect(30, 20, 55, 55);

Syntax:

	fill(rgb, alpha);
	fill(gray, alpha);

alpha: float opacity of the outline

Syntax:

	fill(v1, v2, v3);
	fill(v1, v2, v3, alpha);

v1: float red or hue value

v2: float green or saturation value

v3: float blue or brightness value

![Color4](./images/color4.png) fill(204, 102, 0); rect(30, 20, 55, 55);


###### Background color

Syntax:

	background(rgb);
	background(gray);

rgb: int rgb in hexadecial

gray: float a value between black adn white (0 = black, 255 = white)

Return type: void

![Color5](./images/color5.png) background(51);

Syntax:

	background(rgb, alpha);
	background(gray, alpha);

alpha: float opacity of the outline

Syntax:

	background(v1, v2, v3);
	background(v1, v2, v3, alpha);

v1: float red or hue value

v2: float green or saturation value

v3: float blue or brightness value

![Color6](./images/color6.png) background(255, 204, 0);

Syntax:

	background(image);

image: PImage for the background (must be the same size as the sketch window)

![Color7](./images/color7.png) PImage img; img = loadImage("laDefence.jpg"); background(img);
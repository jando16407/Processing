<a name="top"></a>
# Processing Notes
 
<[Processing Basics](#basics)>  
***	[Stroke](#stroke), [Fill](#fill), [setup()](#setup), [frameRate()](#framerate), "[draw()](#draw), [mousePressed](#mousepressed_v), [mouseX](#mousex), [mouseY](#mousey)      

<[Shape](#shape)>  
***	[Rectangle](#rectangle), [Ellipse](#ellipse), [Line](#line), [Point(dot)](#point), [Triangle](#triangle)  

<[Function](#function)>  
***	[selectinput()](#selectinput), [loadStrings()](#loadstrings), [split()](#split), [max()](#max), [isNaN()](#isnan), [nf()](#nf), [mousePressed()](#mousepressed_f), [sqrt()](#sqrt), [random()](#random)   

<[Draw Function](#draw_function)>  
***	[text()](#text), [textAlign()](#textalign)  

<[Color](#color)>  
***	[Outline color](#outlinecolor), [Color inside of a shape](#colorinside), [Background color](#backgroundcolor)  

<[Array](#array)>   
***  

<[Map](#map)>  
***  

<[Table](#table)>  
***	[getFloat()](#getfloat), [getString()](#getstring), [loadTable()](#loadtable), [getRowCount()](#getrowcount), [getColumnCount()](#getcolumncount), [getColumnTitle()](#getcolumntitle)  

<[JSON](#json)>  
*** [JSONObject](#jsonobject), [loadJSONObject()](#loadjsonobject), [parseJSONArray()](#parsejsonaray), [loadJSONArray()](#loadjsonarray), [getJSONObject()](#getjsonobject), [setJSONObject()](#setjsonobject)  

<[PVector](#pvector)>  
*** [Set()](#pvecset), [random2D()](#pvecrandom2d), [random3D()](#pvecrandom3d), [fromAngle()](#pvecfromangle), [copy()](#pveccopy), [mag()](#pvecmag), [magsq()](#pvecmagsq)  

<a name="basics"></a>

## Processing Basics 
[Top](#top)

Processing uses functions to create visuals.  
### Terminology  
<a name="stroke"></a>
#### Stroke    

Outline of a shape
stroke can set the color or set the with of the line.

Syntax:

	strokeWeight(weight);

weight: float the weight of the stroke  
Return type: void

<a name="fill"></a>
#### Fill  

Anything inside of stroke.

<a name="rules"></a>
### Rules  

* When there are multiple codes, first code will be dislpayed on the bottom, later codes will be displayed on top of the previous ones.  
* To color a shape, call color function before the defining the shape.

### Setup and Draw
<a name="setup"></a>
#### Setup  

It happens only once at the beginnig of the sketch.  
Syntax:

	void setup(){
	}

* Set the size of canvas

<a name="framerate"></a>
#### frameRate()  

Specifies the number of frames to be displayed every second.  
Syntax:    

	frameRate(fps);

fps: float number of desred frames per second  

<a name="draw"></a>
#### Draw  

It loops.  
Syntax:

	void draw(){
	}

* Don't forget to include background(); in the draw function to refresh the background. Otherwise it'll keep drawing new shapes on top.

<a name="mousepressed_v"></a>

#### mousePressed  

It's a variable. mousPressed variable stores whether or not a mouse button is currently being pressed.  
The value is true when any mouse button is pressed, and false if no button is pressed.  

Example:

	// Click within the image to change 
	// the value of the rectangle
	void draw() {
	  if (mousePressed == true) {
	    fill(0);
	  } else {
	    fill(255);
	  }
	  rect(25, 25, 50, 50);
	}

<a name="mousex"></a>
#### mouseX  

The system variable mouseX always contains the current horizontal coordinate of the mouse.  

<a name="mousey"></a>
#### mouseY  

The system variable mouseY always contains the current vertical coordinate of the mouse.  


<a name="shape"></a>

## Shape
[Top](#top)
<a name="rectangle"></a>
#### Rectangle  

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
<a name="ellipse"></a>
#### Ellipse  

Syntax:

	ellipse(a, b, c, d);

a: float x-coordinate (center)  
b: float y-coordinate (center)  
c: float width (diameter)  
d: float height (diameter)  
Return type: void  
![Ellipse](./images/ellipse1.png) ellipse(56, 46, 55, 55);

<a name="line"></a>
#### line  

Syntax:

	line(x1, y1, x2, y2);
	line(x1, y1, z1, x2, y2, z2);

x1: float 1st x-coordinate  
y1: float 1st y-coordinate  
x2: float 2nd x-coordinate  
y2: float 2nd y-coordinate  
z1: float 1st z-coordinate  
z2: float 2nd z-coordinate  
![Line1](./images/line1.png) line(30, 20, 85, 75)

![Line2](./images/line2.png) line(30, 20, 85, 20); stroke(126); line(85, 20, 85, 75);
stroke(255); line(85, 75, 30, 75);

![Line3](./images/line3.png) // Drawing lines in 3D requires P3D // as a parameter to size() size(100, 100, P3D); line(30, 20, 0, 85, 20, 15); stroke(126); line(85, 20, 15, 85, 75, 0); stroke(255); line(85, 75, 0, 30, 75, -50);

<a name="point"></a>
#### Point (dot)

Syntax:

	point(x, y);
	point(x, y, z);

x: float x-coordinate of the point
y: float y-coordinate of the point
z: float z-coordinate of the point
Return type: void

<a name="triangle"></a>  
#### Triangle  

Syntax:  

	triangle(x1, y1, x2, y2, x3, y3);  

x1: float x-coordinte of the first point  
y1: float y-coordinte of the first point  
x2: float x-coordinte of the second point  
y2: float y-coordinte of the second point  
x3: float x-coordinte of the third point  
y3: float y-coordinte of the third point  
Return type: void  
![Triangle](./images/triangle.png) triangle(30,75, 58, 20, 86, 75);  


<a name="function"></a>

## Function 
[Top](#top)
<a name="selectinput"></a>
#### SelectInput  

It lets user to open a new window and browse the file to select a file to use.

Example:

	void setup(){
		selectInput("Select a file to process:", "fileSelected");
	}

	void fileSelected(File selection){
		if(selection == null){
			println("Window was closed or the user hit cancel.");
		} else{
			println("User selected " + selection.getAbsolutePath());
		}
	}

Syntax:

	selectInput(prompt, callback);
	selectInput(prompt, callback, file);
	selectInput(prompt, callback, file, callbackObject);
	selectInput(prompt, callback, file, callbackObject, parent, sketch);
	selectInput(prompt, callback, file, callbackObject, parent);

prompt: string a message to dislpay  
callback: string name of the method for the selection  
Return type: void


<a name="loadstrings"></a>
#### loadStrings  

It reads the contents of a file and creates a string array of individual lines in the file.

Examples:
		
	String[] lines = loadStrings("list.txt");
	println("there are " + lines.length + " lines");
	for (int i = 0 ; i < lines.length; i++) {
	  println(lines[i]);
	}

Syntax:

	loadStrings(filename);
	loadStrings(reader);

filename: string name of the file or URL  
Return type: String()  
<a name="split"></a>
#### split

This function breaks a string into pieces by the given character or string as a delimiter.

Exaples:

		
	String men = "Chernenko,Andropov,Brezhnev";
	String[] list = split(men, ',');
	// list[0] is now "Chernenko", list[1] is "Andropov"...

Syntax:

	split(value, delim);

value: string the string to be split  
delim: char the character or string to separate the string  
Return type: string[]
<a name="max"></a>
#### max()

Syntax:

	max(a, b);
	max(a, b, c);
	max(list);

a: float or int first number to compare  
b: float or int sencond number to compare 
c: float or int thirs number to compare  
list: float[] or int[] array of numbers to compare  

<a name="isnan"></a>  
#### isNan()  

isNan checks if a variable is Not a Number or not.  
It will return *true* if the variable is NaN. False otherwise.  

<a name="nf"></a>
#### nf()  

It is a utility function for formatting numbers into strings.  
Values should always be positive.  

Syntax:  

	nf(num)
	nf(nums)
	nf(nums, digits)
	nf(num, digits)
	nf(nums, left, right)
	nf(num, left, right)

nums: float[] or int[] the numbers to format  
digits: int number of digits of pad with zero  
num: float or int the number to format  
left: int number of digit to the left of the decimal point  
right: int number of digit to the right of the decimal point  
Return type: String[]  

Example:  

	int a=200, b=40, c=90;
	String sa = nf(a, 10);
	println(sa);  // Prints "0000000200"
	String sb = nf(b, 5);
	println(sb);  // Prints "00040"
	String sc = nf(c, 3);
	println(sc);  // Prints "090"

	float d = 200.94, e = 40.2, f = 9.012;
	String sd = nf(d, 10, 4);
	println(sd);  // Prints "0000000200.9400"
	String se = nf(e, 5, 3);
	println(se);  // Prints "00040.200"
	String sf = nf(f, 3, 5);
	println(sf);  // Prints "009.01200"
  
<a name="mousepressed_f"></a>
#### mousePressed()  

This function is called once after every time a mouse button is pressed.  
Syntax:  

	mousePressed();
	mousePressed(event);

Return type: void

<a name="sqrt"></a>
#### sqrt()  

It calculates the square room of a number.  

Syntax:  

	sqrt(n);

n: float non-negative number  
Return type: float  

<a name="random"></a>
#### random()  

It generates random numbers. Each time the random() function is called, it return an enexpected vallue within the specified range.  
If one parameter is passed, it will return a float between zero and the value of the high parameter.  
ex) random(5) will return values between 0 and 5(not including 5)  

Syntax:  

	random(high)  
	random(low, high)  

low: float lower limit  
high: float upper limit  
Return type: float  



<a name="draw_function"></a>

## Draw Function
[Top](#top)
<a name="text"></a>
#### text()

Syntax:

	text(c, x, y);
	text(str, x, y);

c: char the alphanumeric character to be displayed  
x: float x-coordinate  
y: float y-coordinate  
str: string

<a name="textalign"></a>  
#### textAlign()  

Syntax:  

	textAlign(alignX)  
	textALlign(alignX, alignY)  

alignX: int horizontal alignment, either LEFT, CENTER, or RIGHT  
alignY: int vertical alignment, either TOP, BOTTOM, CENTER, or BASELINE  


<a name="color"></a>

## Color
[Top](#top)
<a name="outlinecolor"></a>
#### Outline color

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

<a name="colorinside"></a>
#### Color inside of a shape

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

<a name="backgroundcolor"></a>
#### Background color

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


<a name="array"></a>

## Array
[Top](#top)

To find the length of the array

	arr.length

<a name="map"></a>

## Map
[Top](#top)

Re-maps a number from one range to another  
It will convert the input number accoring to the given range as an output.

Syntax:

	map(value, start1, stop1, start2, stop2)

value: float the incoming value to be converted  
start1: float lower bound of the value's current range  
stop1: float upper bound of the value's current range  
start2: float lower bound of the value's target range  
stop2: float upper bound of the value's target range  
Return type: float

<a name="table"></a>

## Table
[Top](#top)
<a name="getfloat"></a>
#### getFloat()

It return a float value from the table's specified row and column.

Syntax:

	.getFloat(row, column)
	.getFloat(row, columnName)

row: int ID number of the row to reference
column: int ID number of the column to reference
columnName: String title of the column to reference
Return type: float

Example:

	Table table;

	void setup() {

	  table = new Table();
	  
	  table.addColumn("number", Table.INT);
	  table.addColumn("mass", Table.FLOAT);
	  table.addColumn("name", Table.STRING);
	  
	  table.addRow();  // Creates an empty row
	  
	  table.setInt(0, "number", 8);
	  table.setFloat(0, "mass", 15.9994);
	  table.setString(0, "name", "Oxygen");
	  
	  println(table.getInt(0, "number"));   // Prints 8
	  println(table.getFloat(0, "mass"));   // Prints 15.9994
	  println(table.getString(0, "name"));  // Prints "Oxygen"
	}
<a name="getsting"></a>
#### getString()

It returns a string from a table at specified row and column.  

Syntax:

	.getString(row, column);
	.getString(row, columnName);

row: int ID numeber of the row to reference  
column: int ID number of the column to refrence  
columnName: String title of the column to reference  
Return type: String

Example:

Table table;

	void setup() {

	  table = new Table();
	  
	  table.addColumn("number", Table.INT);
	  table.addColumn("mass", Table.FLOAT);
	  table.addColumn("name", Table.STRING);
	  
	  table.addRow();  // Creates an empty row
	  
	  table.setInt(0, "number", 8);
	  table.setFloat(0, "mass", 15.9994);
	  table.setString(0, "name", "Oxygen");
	  
	  println(table.getInt(0, "number"));   // Prints 8
	  println(table.getFloat(0, "mass"));   // Prints 15.9994
	  println(table.getString(0, "name"));  // Prints "Oxygen"
	}

<a name="loadtable"></a>
#### loadTable()   

Read a contents of a file or URL and make a table of the data in a file "data"   

Syntax:  

	loadTable(filename)  
	loadTable(filename, options)  

filename: String name of a file in the data folder or a URL  
options: String may contain "header", "tsv", "csv", or "bin separated by commas  
Return type: Table  

<a name="getrowcount"></a>
#### getRowCount()   

It returns the toal number of rows in a table  

Syntax:  

	.getRowCount()

Return type: int  

<a name="getcolumncount"></a>
#### getColumnCount()  

It returns the total number of columns in a table.  

Syntax:  

	.getColumnCount()

Return type: int  

<a name="getcolumntitle"></a>
#### getColumnTitle()  

It returns the name for a column in a *TableRow* based on its ID  

Syntax:  

	.getColumnTitle(column)

column: int ID number of the target column  
Return type: String  

<a name="json"></a>

## JSON
[Top](#top)
<a name="jsonobject"></a>  
#### JSONObject  

A JSONObject stores JSON data with multiple name/value pairs.  
Values can be numeric, Strings, booleans, other JSONObjects oor JSONArrays, or null.  
JSONObject and JSONArray objects are quite similar and share most of the same methods; the primaru difference is that the latter stores an array of JSON objects, while the former represents a single JSON object.  

	json = new JSONObject();  

<a name="loadjsonobject"></a>  
#### loadJSONObject()  

It loads a JSON from the data folder or URL and return a JSONObject.  

Syntax:  

	loadJSONObject(filename)  
	loadJSONObject(file)  

filename: String name of a file in the data folder or a URL  

<a name="parsejsonaray"></a>  
#### parseJSONArray()  

It will take a string, prases its contents, and return a JSONArray. If the string does not contain JSONArray data ot cannot be parsed, a null value is returned.  
If the data already exists as a JSON file in the data folder, it is simpler to use loadJSONArray().  

Syntaax:  

	parseJSONArray(input)  

input: String string to parse as a JSONArray  


<a name="loadjsonarray"></a>  
#### loadJSONArray()  

It loads an array of JSON objects from the data folder and return a JSONArray.  

Syntax:  

	loadJSONArray(filename)  
	loadJSONArray(file)  

filename: String name of a file in he data folder or a URL  


<a name="getjsonobject"></a>  
#### getJSONObject()  

It retrieves the JSONObject with the associated index value.  

Syntax:  

	.getJSONObject(index)  
	.getJSONObject(index, defaultValue)  

index: int the index value of the object to get  

<a name="setjsonobject"></a>  
#### setJSONObject()  

It sets the value of the JSONObject with the index value.  

Syntax:  

	.setJSONObject(index, value)  

index: int the index value to target  
value: JSONObject the value to assign  

<a name="pvector"></a>

## PVector
[Top](#top)

A class to descrive a two or three dimentsional vector, specifically a Euclidean (also known as geometric) vector.  

Fields include:  

x: the x component of the vector  
y: the y component of the vector  
z: the z component of the vector  

Methods include:  

<a name="pvecset"></a>  
#### set()  

It sets the x, y, and z component of the vector.  

Syntax:  

	.set(x, y, z)  
	.set(x, y)  
	.set(v)  
	.set(source)  

x: float the x  
y: float the y  
z: float the z  
v: PVector any variable of type PVector  
source: float[] arrau to copy from  
Return type: PVector  



<a name="pvecrandom2d"></a>  
#### random2D()  

It return a new 2D unit vector with a random direction. It will use Papplet's random number generator.  

Syntax:  

	.random2D()  
	.random2D(parent)  
	.random2D(target)  
	.random2D(target, parent)  

parent: PApplet current PApplet instance  
target: PVector the target vetctor (if null, a new vector will be created)  
Return type: PVector  

<a name="pvecrandom3d"></a>
#### random3D()  

Same as 2D but it's 3D.  

<a name="pvecfromangle"></a>  
#### fromAngle()  

It clculates and return a new 2D unit vecto from the specified angle value(in radians)  

Syntax:  

	.fromAngle(angle)  
	.fromAngle(angle, target)  

angle: float the angle in radians  
target: PVector the target vector (if null, a new vector will be created)  
Return type: PVector  

<a name="pveccopy"></a>
#### copy()  

It copies the component of the vector.  

Syntax:  

	.copy()  

Ex:  

	v2 = v1.copy();  

Return type: PVector  

<a name="pvecmag"></a>  
#### mag()  

It returns the magnitutde(length) of the vector. Equation is simply sqrt(x*x+y*y+z*z).  

Syntax:  

	.mag()  

Return type: float  

<a name="pvecmagsq"></a>
#### magSq()  
calculated the magnitutde of the vector and it's squared. It's often used to improve performance since, unlike mag(), it does not require a sqrtt() operation.  

Return tye: float  

<a name="pvecsub"></a>  
#### sub()  

It subtracts x, y and z components from a vector, subtracts one vector from another, or subtracts two independendt vectors.   

Syntax:  

	.sub(v)  
	.sub(x, y)  
	.sub(x, y, z)  
	.sub(v1, v2)  
	.sub(v1, v2, target)  

Example:  

	v2.sub(v1);  
	v.sub(40, 20, 0);  
	PVector v3 = PVector.sub(v1, v2);  

v: PVector any variable of type PVector  
x: float the x component  
y: float the y component   
z: float the z component  
v1: PVector the x, y and z components  
v2: PVector theh x, y and z components  
target: PVector PVector in which to store the result  
Return type: PVector  

<a name="pvecdist"></a>  
#### dist()  

It calculates the Euclidean distance between two points(cconsidering a point as a vecto object)  

Syntax:  

	.dist(v)  
	.dist(v1, v2)  

v: PVector the x, y, z coordinates of a PVector  
v1: PVector any variable of type PVector  
v2: PVector nay variable of type PVector  
Return type: float  


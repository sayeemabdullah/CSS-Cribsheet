# CSS Cribsheet 

> CSS which stands for Cascading Style Sheets which is a Styling Language. This is an initiative to make small notes on CSS which may help me or anyone else in the future.

___

Before starting I would like to recommend some tools and extensions which will make our coding experience easier and better. We can use [Visual Studio Code](https://code.visualstudio.com/) as our code editor. Inside **Visual Studio Code** we can install [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) to make our code prettier and easy to read/debug and [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) which will run our project in our localhost. 

Starting with the basic, there are **three ways of using CSS**:

* **Embedded Stylesheets:** using CSS inside HTML file 
* **External Stylesheets:** using different file for CSS
* **Inline Styles:** using CSS in particular elements


##### N.B. External Stylesheets is recommended but others can be also used when needed 

___

## Context Table

|Topics|
|---|
|[How to connect CSS with HTML?](https://github.com/sayeemabdullah/CSS-Cribsheet#how-to-connect-css-with-html)|
|[Normalizing CSS](https://github.com/sayeemabdullah/CSS-Cribsheet#normalizing-css)|
|[Basic Selectors](https://github.com/sayeemabdullah/CSS-Cribsheet#basic-selectors)|
|[Relational Selectors](https://github.com/sayeemabdullah/CSS-Cribsheet#relational-selectors)|
|[Pseudo-class Selectors](https://github.com/sayeemabdullah/CSS-Cribsheet#pseudo-class-selectors)|
|[Pseudo-element Selectors](https://github.com/sayeemabdullah/CSS-Cribsheet#pseudo-element-selectors)|
|[Universal Selector](https://github.com/sayeemabdullah/CSS-Cribsheet#universal-selector)|
|[Selectors Specificty](https://github.com/sayeemabdullah/CSS-Cribsheet#selectors-specificty)|
|[Colors](https://github.com/sayeemabdullah/CSS-Cribsheet#colors)|
|[Gradient](https://github.com/sayeemabdullah/CSS-Cribsheet#gradient)|
|[Borders](https://github.com/sayeemabdullah/CSS-Cribsheet#borders)|
|[Shadow](https://github.com/sayeemabdullah/CSS-Cribsheet#shadow)|
|[Box Model](https://github.com/sayeemabdullah/CSS-Cribsheet#box-model)|
|[Overflow](https://github.com/sayeemabdullah/CSS-Cribsheet#overflow)|
|[Measurement Units](https://github.com/sayeemabdullah/CSS-Cribsheet#measurement-units)|
|[Postioning](https://github.com/sayeemabdullah/CSS-Cribsheet#postioning)|
|[Floating Elements](https://github.com/sayeemabdullah/CSS-Cribsheet#floating-elements)|
|[FlexBox](https://github.com/sayeemabdullah/CSS-Cribsheet#flexbox)|
|[Grid](https://github.com/sayeemabdullah/CSS-Cribsheet#grid)|
|[Hiding Elements](https://github.com/sayeemabdullah/CSS-Cribsheet#hiding-elements)|
|[Media Queries](https://github.com/sayeemabdullah/CSS-Cribsheet#media-queries)|



## How to connect CSS with HTML?

In the HTML file, we will add the following line -
 hidden;
``` html
<link rel="stylesheet" href="styles.css" />
```
In **href** we will put the path address where the CSS file is kept. 

___

## Normalizing CSS

As there are different browsers and they render some HTML elements differently. So [normalize.css](https://necolas.github.io/normalize.css/8.0.1/normalize.css) is a stylesheet that provides a basic default style.  

___

## Basic Selectors

We can select elements for styling in the following ways:

* **Type:** Choosing an element by type
* **ID:** Choosing an element by ID and can be used in a single element
* **Class:** Choosing an element by Class and can be used in multiple elements  
* **Attribute:**  Choosing an element by Attribute but is not recommended 

___

## Relational Selectors

As we know the basic selectors, we can also use some relational selectors too

*  **Descendant Selector:** Choosing an element by **ID** and **Type** like below
	
  ``` css
  #products p {
    color: purple;
  }
  ```
  
And if we want to change only the first decent or direct child use the following code

 ``` css
  #products > p {
    color: purple;
  }
  ```
  
* **Sibling Selector:** Selecting the element that comes right after the selected element. We can use the following code 

 ``` css
  #products + p {
    color: purple;
  }
  ```
  
And if we want to choose all the elements after the chosen one

 ``` css
  #products ~ p {
    color: purple;
  }
  ```
  
So in the above two codes, in the first one after **products** the first **p** will be purple and in the second one after **product**, all **p** will be purple.
  
___

##  Pseudo-class Selectors

Pseudo-class is not something we define it’s something which the browser defines.

 ``` css
  article :first-child {
    color: purple;
  }
  ```
  
``` html
<article>
	<h1>fist</h1>
        <p>second</p>
</article>
```

So the first element in **article** will be purple. There are many more like `first-of-type` which will make all the first occurrence of a type purple and also `last-child` and `last-of-type` for making the last child and the last of each type purple respectively.  

Let say we want all the even number of a list purple. We will use the following code:

 ``` css
  ul li:nth-child(even) {
  	color: purple;
}
  ```
We can also use **even** and also **formula** like 3n (every 3rd item in the list).

Let say we want to change the color of the visited link to red we can use the following code:

 ``` css
  a:visited {
  	color: red;
}
  ```

We can also use `a:link` to change the color of unvisited link and if we want to change color when the user hover we can use `a:hover` and also add `a:focus` so that if the user using tab key it will focus.

___

##  Pseudo-element Selectors

Pseudo-element is also not something we define it’s something which the browser defines just like **Pseudo-class Selectors** but instead of using **":"** we will use **"::"**.

 ``` css
 p::first-letter {
  font-size: 140%;
}
  ```
  
So if we write the above code the first word of each paragraph will have a font-size of 140%. We can also use `p::first-line` to make changes in the first line, `p::selection` to make changes when someone selects the words in the paragraph. If we want to add something before or after a paragraph we can use `p::before` and `p::after` respectively. 

___

## Universal Selector

If we want to make all the element types into a specific style we use `*` as follows:

 ``` css
* {
  color: purple;
}
  ```

___
##  Selectors Specificty

While coding different selectors sometimes triggers the same elements more than once like below:

 ``` css
h1 {
  color: blue;
}

.highlight {
  color: yellow;
}
  ```
  
``` html
<h1 class="highlight">I am blue or yellow?</h1>
```
In these types of cases, the above list is followed **the first one having the highest priority and the last one the least**.

* ID Selector
* Class and Attribute Selector
* Element Selector

But if there are 2 IDs with the same name like below:

``` css
#products {
  color: purple;
}

#products {
  color: pink;
}
```
In the above case, it will **choose the very last one**. So the color will be pink.

But lets say from the first snnipet of code we want to use **h1** which makes the color **blue**. So we have to add a keyword **!important** after **color: blue;** as following:

 ``` css
h1 {
  color: blue !important;
}

.highlight {
  color: yellow;
}
  ```
Or we can be more specific like below: 

 ``` css
h1.highlight {
  color: blue;
}
  ```
Using **!important** keyword is **not recommended**.
___

## Colors

There are **four ways** to select a color in CSS. They are by - 

* Name
* RGB / RGBA
* HSL / HSLA
* Hexadecimal 

___

## Gradient 

A gradient shows the transition between two or more colors. If we want to write a code that will make a box where the first color is blue and will transit into yellow from top to bottom it will be like below:

``` css
.box {
  width: 200px;
  height: 200px;
  background: linear-gradient(blue, yellow);
}
```
``` html
<div class="box"></div>
```
We can also change the transit to a different direction by adding `to right`, `to bottom right`, or according to our need. We can also use a specific degree like `45deg` and also select a **percentage** of a specific color in the gradient. We can also use `radial-gradient()`.

https://cssgradient.io : This website is **recommended** to get the right gradient for your project as it generates the **CSS code** too. 

___

## Borders 

Border takes **three values thickness, style, and color**. There are different types of styles `dashed`, `solid`, and so on. Something to remember while using `border-width` it takes 4 values in the following order  **Top-Right-Bottom-Left**. We can also use `border-color`, `border-radius` and so on.

___

## Shadow 

We can use `box-shadow` to make a shadow of box where we pass 4 values **Horizontal Distance-Vertical Distace-Softness-Color**. We can also use `text-shadow` for a text. 

___

## Box Model

The box model consist of 4 things :

* Margin 
* Border 
* Padding 
* Content 

To get a clearer view here is a diagram:

![boxmodel](https://user-images.githubusercontent.com/31423599/109789169-41463680-7c3a-11eb-8f9a-df29e6a6ff0f.png)



___

## Overflow

Sometimes in a fixed-sized element, overflow happens. In those cases, we use `overflow: hidden;` to hide the overflowed content or we can also use `overflow: scroll;` or `overflow: auto;`. To contol by the X (Horizontal) and Y (Vertical) axis by using two values like `overflow: hidden auto;`.

___

## Measurement Units

There are two types of Measuring Categories:

* Absolute
* Relative 

In **Absolute** there is **px (Pixel)** and in **Relative** there are **% (Percentage)** which is relative to the size of the container, **vw (Viewport Width)** and **vh (Viewport Height)** which is relative to the viewport, and lastly **rem (10x The root element's font-size)** and **em (10x The current element's font-size)** which is relative to the font size.   
 
___

## Postioning 

We can position an element by setting values in 5 different ways. They are -

* **Static:** Default type
* **Relative:** Relative to its normal position
* **Fixed:** Relative to the viewpoint
* **Absolute:** Relative to the parent (the container must be positioned “Relative”)
* **Sticky:** Relative to the user's scroll position

Another thing to remember is `z-index`. If `z-index` is negative that means the element is further than us and if positive that means closer. We can use `top`, `bottom`, `left` and `right` to fix the position but if and only if the `position` is not static.
 

___

## Floating Elements 

The float property specifies that whether the element floats left or right by using `float: left;` or `float: right;` respectively. If we want to clear the left, right or both sides of the floating element we can use `clear: left`, `clear:right`, and `clear: both` respectively.

As the parent element doesn’t see the floating element so the view will collapse or will look weird. To solve this you have to **clear** after or you can use the following code and call the **class**:

``` css
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```
___

## FlexBox

FlexBox is used for laying out elements in one direction. Let say we want to show some boxes in a container in a row we can use the below code:

``` css

.container {
  border: 3px solid lightgrey;
  display: flex;
  flex-direction: row;
}

.box {
  width: 5rem;
  height: 5rem;
  background: gold;
  margin: 1rem;
}

```

So in the above code, we can see that `display: flex` makes the display flex and we can change the direction however we want eg. `flex-direction: row;` for displaying as a row or `flex-direction: column;` for displaying as column and you can reverse the row or column by `flex-direction: row-reverse;` and `flex-direction: column-reverse;` respectively. 

#### Align

Now to understand **Align**  better we need to know about **Axes**. There are **two types** of Axes-

* **Main:** Primary
* **Cross:** Secondary

When the direction is **Row**, **Main** is **Horizontal** and  **Cross** is **Vertical**. 
On the other hand when the direction is **Column**, **Main** is **Vertical** and  **Cross** is **Horizontal**.

Now to `Align items` we need to know **3 properties**. They are-

* `justify-content` : Along the main axis
* `align-items` : Along the cross axis
* `align-content`

When using `justify-content` we can use `justify-content : flex-start` , `justify-content : space-between` , `justify-content : space-evenly` and many more to style the primary. Then while using `align-items` which is to style the secondary we can use `align-items : flex-start` , `align-items : flex-end` and many more.

`flex-wrap` is another important property of flex. Let’s say when there are multiple boxes in a row so to keep them in a single line they shrink the size of the boxes but if we don’t want that we have to use `flex-wrap` and change the default (`nowrap`) to `wrap`.

After this we will see that the boxes are not in the center of the axes to change this `align-content` comes which can align multiple lines or whole content. 

To style a **flex item** we can use `align-self`.

#### Sizing

There are some properties to remember which is used for sizing **flex item**. They are -

* `flex-basis` : The initial size of a flex item
* `flex-grow` : The growth factor
* `flex-shrink` : The shrink factor
* `flex` : Combination of above three properties 

`flex-basis` takes size as value. When the `flex-direction: row;` its overwrites **width** and when `flex-direction: column;` it overwrites **height**.

`flex-grow` and `flex-shrink` take growth factor and shrink factor as value respectively and do work accordingly.

Lets say we have 3 boxes, **box-one** , **box-two** and **box-three**. If box-one has a factor of 2 and the other two boxes of 1. So basically box-one will be 2/4th. 

Finally `flex` takes **3 values** in the following order : 
**`flex-grow`-`flex-shrink`-`flex-basis`**.

___

## Grid 

Grid is a grid-based layout by rows and columns. Starting with the basic, we can define grid by the following ways -

``` css
  /* 3X2  */
  display: grid;
  grid-template-rows: 100px 100px 100px;
  grid-template-columns: 100px 100px;
```

``` css
  /* 3X2  */
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(2, 100px);
```

``` css
  /* 3X2  */
  display: grid;
  grid-template: repeat(3, 100px) / repeat(2, 100px);
```

#### Align

For aligning items we can use the following properties:

* `justify-items` : along the horizontal axis
* `align-items` : along the vertical axis
* `justify-content` : along the horizontal axis
* `align-content` : along the vertical axis


`justify-items` and `align-items` is used to align items in the grid and `justify-content` and `align-content` to align the entire grid. 

If we want to change the size of the grid column or row by **fr (fraction : of the the existing free space)** or size we can do it like below:

``` css
display: grid;
grid-template: repeat(3, 100px) / 100px 30fr 70fr;
```

#### Gap

There are three properties for gap. They are -

* `row-gap` : Gaps between rows
* `column-gap` : Gaps between columns 
* `gap` : Short hand for `row-gap` and `column-gap`


#### Placing

There are three properties for placing items. They are -

* `grid-row`  
* `grid-column` 
* `grid-area` : Shorthand for `grid-row` and `grid-column` 

Let’s say we want to use the third row - second column we can use the below code:

``` css
grid-column: 1;
grid-row: 3;
```

So from the above code, we can understand it takes the row/column number as a value, and now if we want to start at the first column and end on the third column. We can use the following code:

 ```css
grid-column: 1 / 3;
```
We can also use `span` like below:

 ```css
grid-column: 1 / span 2;
```

Both of the codes will do the same work. It depends on the user what s/he wants to use. 

`grid-area` takes 4 values: **start of row - start of column - end of row - end of column** like below:

``` css
grid-area: 1 / 1 / 1 / 3;
```

There is another way to place items that are in named areas. We use `grid-template-area` and `grid-area`.

First `grid-template-area` is naming the rows and columns of your grid like below:

```css
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
```
So between the first double quotation marks the first name is of the first column of the first row and the second word is of the second column of the first row. This is how it is named. Now let’s say we don’t want to name the second column of the first row we can just use a `.` like below:

```css
  grid-template-areas:
    "header ."
    "sidebar main"
    "footer footer";
```

Now we can call by name like below:

```css
grid-area: header;
```

___

## Hiding Elements 

There are two ways of hiding an element. The first one is commonly used which is:

``` css
 display: none;
```
In the above case, the whole element goes away and another way is where the element stays but cannot be seen. To do so we use the below code:

```css
visibility: hidden;
``` 

___


## Media Queries 

With media queries, we can give different styles for different devices like a style for **mobile** and another style for **desktop** depending on their features. During designing a responsive design we can first design for the desktop and then adjust for mobile or vice-versa.
Lets say there is a **container** where `display: flex` and `flex-direction: column` but we want to make the `flex-direction: row` when the screen is **600px or more**. We can use the following code:
 
``` css

@media screen and (min-width: 600px){
  .container{
    flex-direction: row;
  }
}

```

And now if we want to change the background color of a box when the screen is **700x or less**, we can use the  following code:

``` css

@media screen and (max-width: 700px){
  .box{
    background-color: deepskyblue;
  }
}

```
 
We can also use both in case like you want to change the background color when the screen is **between 600px to 700px**, we can use:

``` css

@media screen and (min-width: 600px) and (max-width: 700px){
  .box{
    background-color: deepskyblue;
  }
}

```

There is another type of `@media` which is `@media print` which only applies to printer. When using `@media print` we will use **measuring unit** of `font-size` as **pt** and `padding` as `cm`.

___



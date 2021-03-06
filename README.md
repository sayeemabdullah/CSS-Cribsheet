# CSS Cribsheet 

> CSS which stands for Cascading Style Sheets is a Styling Language. This is an initiative to make small notes on CSS which may help me or anyone else in the future.

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
|[Positioning](https://github.com/sayeemabdullah/CSS-Cribsheet#positioning)|
|[Floating Elements](https://github.com/sayeemabdullah/CSS-Cribsheet#floating-elements)|
|[FlexBox](https://github.com/sayeemabdullah/CSS-Cribsheet#flexbox)|
|[Grid](https://github.com/sayeemabdullah/CSS-Cribsheet#grid)|
|[Hiding Elements](https://github.com/sayeemabdullah/CSS-Cribsheet#hiding-elements)|
|[Media Queries](https://github.com/sayeemabdullah/CSS-Cribsheet#media-queries)|
|[Typography](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#typography)|
|[Images](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#images)|
|[Embed With Google Maps](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#embed-with-google-maps)|
|[Forms](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#forms)|
|[CSS Frameworks](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#css-frameworks)|
|[Inputs](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#inputs)|
|[Lists](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#lists)|
|[Transformations & Transitions](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#transformations--transitions)|
|[Animations](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#animations)|
|[Variables](https://github.com/sayeemabdullah/CSS-Cribsheet/blob/main/README.md#variables)|
<!---|[]()|
|[]()|--->


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

Pseudo-class is not something we define it’s something that the browser defines.

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

We can also use `a:link` to change the color of the unvisited link and if we want to change color when the user hover we can use `a:hover` and also add `a:focus` so that if the user using tab key it will focus.

___

##  Pseudo-element Selectors

Pseudo-element is also not something we define it’s something which the browser defines just like **Pseudo-class Selectors** but instead of using **":"** we will use **"::"**.

 ``` css
 p::first-letter {
  font-size: 140%;
}
  ```
  
So if we write the above code the first word of each paragraph will have a font size of 140%. We can also use `p::first-line` to make changes in the first line, `p::selection` to make changes when someone selects the words in the paragraph. If we want to add something before or after a paragraph we can use `p::before` and `p::after` respectively. 

___

## Universal Selector

If we want to make all the element types into a specific style we use `*` as follows:

 ``` css
* {
  color: purple;
}
  ```

___
##  Selectors Specificity

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
We can also change the transit to a different direction by adding `to right`, `to the bottom right`, or according to our need. We can also use a specific degree like `45deg` and also select a **percentage** of a specific color in the gradient. We can also use `radial-gradient()`.

https://cssgradient.io: This website is **recommended** to get the right gradient for your project as it generates the **CSS code** too. 

___

## Borders 

The border takes **three values thickness, style, and color**. There are different types of styles `dashed`, `solid`, and so on. Something to remember while using `border-width` it takes 4 values in the following order  **Top-Right-Bottom-Left**. We can also use `border-color`, `border-radius` and so on.

___

## Shadow 

We can use `box-shadow` to make a shadow of the box where we pass the following values **Horizontal Offset-Vertical Offset-Blur-Spread-Color-inset|initial|inherit**. We can also use `text-shadow` for a text. 

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

Sometimes in a fixed-sized element, overflow happens. In those cases, we use `overflow: hidden;` to hide the overflowed content or we can also use `overflow: scroll;` or `overflow: auto;`. To control by the X (Horizontal) and Y (Vertical) axis by using two values like `overflow: hidden auto;`.

___

## Measurement Units

There are two types of Measuring Categories:

* Absolute
* Relative 

In **Absolute** there is **px (Pixel)** and in **Relative** there are **% (Percentage)** which is relative to the size of the container, **vw (Viewport Width)** and **vh (Viewport Height)** which is relative to the viewport, and lastly **rem (n x The root element's font-size)** and **em (n x The current element's font-size)** which is relative to the font size.   
 
___

## Positioning 

We can position an element by setting values in 5 different ways. They are -

* **Static:** Default type
* **Relative:** Relative to its normal position
* **Fixed:** Relative to the viewpoint
* **Absolute:** Relative to the parent (the container must be positioned “Relative”)
* **Sticky:** Relative to the user's scroll position

Another thing to remember is `z-index`. If `z-index` is negative that means the element is further than us and if positive that means closer. We can use `top`, `bottom`, `left`, and `right` to fix the position but if and only if the `position` is not static.
 

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

After this, we will see that the boxes are not in the center of the axes to change this `align-content` comes which can align multiple lines or whole content. 

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

Grid is a grid-based layout with rows and columns. Starting with the basic, we can define the grid in the following ways -

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


`justify-items` and `align-items` are used to align items in the grid and `justify-content` and `align-content` to align the entire grid. 

If we want to change the size of the grid column or row by **fr (fraction : of the the existing free space)** or size we can do it like below:

``` css
display: grid;
grid-template: repeat(3, 100px) / 100px 30fr 70fr;
```

#### Gap

There are three properties for the gap. They are -

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

With media queries, we can give different styles for different devices like **mobile** and **desktop** depending on their features. During designing a responsive design we can first design for the desktop and then adjust for mobile or vice-versa.
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
 
We can also use both in a case like we want to change the background color when the screen is **between 600px to 700px**, we can use:

``` css

@media screen and (min-width: 600px) and (max-width: 700px){
  .box{
    background-color: deepskyblue;
  }
}

```

Another type of `@media` is `@media print`, which only applies to printers. When using `@media print` we will use **measuring unit** of `font-size` as **pt** and `padding` as **cm**.

We can use two or more **style sheets / CSS files** which can be used as shown below:

``` html

<link rel="stylesheet" href="css/style.css" />
<link rel="stylesheet" href="css/mobile.css" media="(max-width : 630px)" />

```  
So here when the width is less or equal to 630px, **style.css** will be overridden by **mobile.css**. 

___

## Typography

`There are three categories of fonts :

* Serif
* Sans-serif 
* Monospace 

Inside each categories there are many fonts. `font-family` is most commonly used to set fonts for a specific paragraph, container or the whole body. If we are using **Visual Studio Code**, after typing `font-family:` if we press <kbd>Ctrl</kbd> + <kbd>Space</kbd> we can see many **stacks** of **Websafe fonts**.

```css
font-family: 'Courier New', Courier, monospace;
```

Here if **'Courier New'** is not available it will use **Courier** and so on. Some of the keyword to remember is `font-weight`, `font-style`, `font-size` and `color`.

We can also download paid or free fonts from websites like www.fonts.com,  www.myfonts.com, and www.fontsquirrel.com. There are many formats like **TTF**, **OTF**, **EOT**, **WOFF**, and **WOFF 2.0**. **WOFF** and **WOFF 2.0** are recommended for the web. To check the font is supported by which browser we can check it on www.caniuse.com. 

Let’s say we added **Open-sans WOF and WOFF 2.0** formatted file in our project directory after that we have to add the below code so that we can use it in our project:

``` css
@font-face {
  font-family: "opensans";
  src: url("./fonts/open-sans/opensans-bold-webfont.woff2") format("woff2"),
    url("./fonts/open-sans/opensans-bold-webfont.woff") format("woff");
  font-weight: bold;
  font-style: bold;
}

@font-face {
  font-family: "opensans";
  src: url("./fonts/open-sans/opensans-regular-webfont.woff2") format("woff2"),
    url("./fonts/open-sans/opensans-regular-webfont.woff") format("woff");
  font-weight: normal;
  font-style: normal;
}
```

In the place of **URL** we will write the directory of the file and change the name of the **font-family** to what we wish to call them by. It is recommended to name something easy to read and relevant. 

Sometimes due to the slow internet connection or some other reason, the text takes time to load so in that case, we can set the `display` to `swap` which will swap with another font until the styling font loads, to `fallback` or `optional` which will show the secondary font and wait let’s say 10 seconds and within that if the styling font doesn’t load it will keep the secondary font. We can also use `block` which will show nothing until the styling font loads but it is not recommended as if the font never loads the field will be empty. 

We can use some Font Services like [Google Web Fonts](fonts.google.com), [Adobe Web Fonts](fonts.adobe.com), and many more. We can also use the **System Font Stack** which selects font according to the operating system we are using. We can use the following code:

``` css

  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;

```

While selecting the `font-size`, we can help from https://type-scale.com, which will help us select a more accurate size. 


To change the **Vertical Space** between fonts we use `line-height`. The general rules of `1.5` times of the font-size but can be changed according to one’s webpage. And to change the **Horizontal Space** between letters we use `letter-spacing` and **Horizontal Space** between words we can use `word-spacing`. Something to remember, the **ideal line length is 50-70 characters**. To do that we can use the following code:

``` css

width: 50ch;

``` 

To format text we can use `text-align`, `text-intent`, `text-decoration` , `text-transform`, `white-space` and so on. 


___

## Images

To add images to our page we can use the following code:

``` html

<img class="meal" src="/images/meal.jpg" alt="A picture of a meal" />

```

If we want to choose a background image we can use code like the following:

``` css
body {
  background: url(/images/bg-paper@2x.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-attachment: fixed;
  height: 100vh
}
```

Here in `background`, the link to the image is provided. The background is repeated in default to disable the background repetition by `background-repeat` or set the axis of repetition by setting `background-repeat: repeat-x` or `background-repeat: repeat-y`. The `background-size` is set according to size and uses `cover` to cover the whole screen. We can also use `background-position` to change the image’s position and keep the image fixed relative to the viewport we can use `background-attachment: fixed`. To download **SVG** background we can visit https://www.svgbackgrounds.com.


#### CSS Sprites

We can find multiple **CSS Sprites generators** on the internet like [CSS Sprites Tool](https://cssspritestool.com/). So basically it takes all the images and makes them into one and also generates a **.css** file we have to copy the classes into our style sheet. After that, we can call them in a `span` anywhere in our project.  


#### Data URLs

We can embed our images to URL but it increases the size and complexity. To do so we can use [CSS Portal](https://www.cssportal.com/) or any other sites. 


#### Clipping 

We can clip our images on different websites such as [bennettfeely](https://bennettfeely.com/clippy/). We don’t need photoshop or other software to do that anymore. These websites code like below which we can simply use in our image class

``` css
clip-path: polygon(50% 0%, 90% 20%, 100% 60%, 75% 100%, 25% 100%, 0% 60%, 10% 20%);
```
<br/>


There are multiple screens with different resolutions, so sometimes we might see that an image is alright on mobile but looks a little blurry in a better resolution mobile. In that case, we can use the same image with different resolutions file like below:

``` html
    <img
      src="/images/meal.jpg"
      alt="A bowl of Salmon and Curry"
      class="meal"
      srcset="
        images/meal.jpg     400w,
        images/meal@2x.jpg 1000w,
        images/meal@3x.jpg 1200w
      "
    />
```

We can also switch the image resolution according to screen size like following:

``` html
<img
      src="/images/meal.jpg"
      alt="A bowl of Salmon and Curry"
      class="meal"
      srcset="
        images/meal.jpg     400w,
        images/meal@2x.jpg 1000w,
        images/meal@3x.jpg 1200w
      "
      sizes="
      (max-width: 500px) 100vw,
      (max-width: 700px) 50vw , 
      33vw"
    />

```

We can see the breakpoint of an image in https://responsivebreakpoints.com.  It is recommended to use a modern format that is **webp** but **Internet Explorer** doesn’t support this format. To use it on **Internet Explorer** we can use the below code: 

``` html
    <picture>
      <source type="image/webp" srcset="images/meal.webp" />
      <img src="/images/meal.webp" />
    </picture>

```

We can download free and paid icons from [Font Awesome](https://fontawesome.com/) or any other website. We will get a **script link** which we will put in the **head** of our **HTML** file. 

___

## Embed With Google Maps

Putting a map of a place is easier than we think all we just need is to go to the [**google map**](https://www.google.com/maps) and search for the place. After that there we will find a **share** option and after pressing it we will find **Embed a map**. From there all we have to do is copy the HTML and put it in our code. 

___

## Forms

Starting with the basic form. The code looks something like this:

``` html
<form>
      <div>
        <label for="name">Name: </label>
        <input id="name" type="text" />
      </div>
      <div>
        <label for="email">Email: </label>
        <input id="email" type="email" />
      </div>
      <button type="submit">Submit</button>
      <button type="clear">Clear</button>
</form>
```

Here we use the **form** tag to make the form and **input** and **label** for input fields and their labels respectively. To style we can use the following code:

``` css

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  line-height: 1.5;
  padding: 1rem;
}

label {
  display: block;
}

input[type="text"],
input[type="email"] {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 0.5rem 0.7rem;
  transition: border-color 0.15s, box-shadow 0.15s;
}

input[type="text"]:focus,
input[type="email"]:focus {
  border-color: #7db0fb;
  outline: 0;
  box-shadow: 0 0 0 4px rgba(24, 117, 255, 0.25);
}

button {
  background-color: #0d6efd;
  color: white;
  border: 0;
  padding: 0.5rem 0.7rem;
  border-radius: 5px;
  outline: 0;
}

.form-group {
  margin-bottom: 1rem;
}


``` 
This code is just a sample so that we can have an idea and most of the things are self-explanatory. If you don't have a backend you can use https://formspree.io to send an email and other form services. 

___


## CSS Frameworks

There are many CSS Frameworks, some of them are:

* Bootstrap 
* Semantic UI
* UI Kit
* Materialize 
* Milligram 

___

## Inputs

There are different input types, some of them are:

* `text`
* `email`
* `number`
* `date`
* `password`
* `button`
* `color`

Some attributes to remember are `readonly`, `value`, `disabled`, `placeholder`, and many more.

___

## Lists

#### Data Lists  

Sometimes we let users select suggestions from a list. To do so we can use the below code:
 
``` html
<input type="text" list="countries" autocomplete="off" />
      <datalist id="countries">
        <option>Bangladesh</option>
        <option>Canada</option>
        <option>USA</option>
        <option>Germany</option>
      </datalist>
```



#### Drop-down List 

To make a drop-down list we can do the below:

``` html
 <select>
        <option value="1">HTML</option>
        <option value="2">CSS</option>
        <option value="3" selected>JavaScript</option>
</select>

```
We can also use `optgroup` to make multiple groups: 

``` html
      <select>
        <optgroup label="Front-end">
          <option value="1">HTML</option>
          <option value="2">CSS</option>
          <option value="3" selected>JavaScript</option>
        </optgroup>
        <optgroup label="Back-end">
          <option value="1">Java</option>
          <option value="2">Python</option>
        </optgroup>
      </select>
```
___

## Transformations & Transitions

There are some functions for transformation. Some of them are **rotate()** which rotates an element, **scale()** which scales an element . **skew()** which tilts an element and **translate()** which makes an element move and if we want to move along the axis we can use **translateX()** and **translateY()**. We can also make the element transform in 3D using **perspective()** which is the distance between the user and the element and after that using **translateZ()**. To rotate an element we can use **rotateX()** and **rotateY()**. 

We can choose the time of transition by `transition: transform 0.5s` or add `color` and many more. 

___

## Animations

Our CSS animation can have many `@keyframes`. It can be used as below: 

``` css
@keyframes pop {
  0% {
    transform: scale(1);
  }

  25% {
    transform: scale(1.3);
  }

  50% {
    transform: rotate(45deg);
    background: tomato;
  }

  100% {
    transform: rotate(0);
  }
}

.box {
    width: 100px;
    height: 100px;
    background: gold;
    animation-name: pop;
    animation-duration: 4s;
    animation-delay: 1s;
    animation-iteration-count: infinite;
    animation-timing-function: ease-out;
    animation-direction: normal;

}
```

Here **0%**,**25%** and others are the fraction of `animation-duration`, and other functions are self-explanatory. We can also use reusable animation and find them on websites like https://animate.style.

___

## Variables

We can set variables and which can be used later in the code. We have to do the following:

``` css

:root {
  --color-primary: yellow;
}

```

So later in the code, we can use it only by calling `var(--color-primary)`. 

___

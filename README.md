# CSS Cribsheet 

> CSS which stands for Cascading Style Sheets which is a Styling Language. This is an initiative to make small notes on CSS which may help me or anyone else in the future while coding.

___

Starting with the basic, there are **three ways of using CSS**:

* **Embedded Stylesheets:** using CSS inside HTML file 
* **External Stylesheets:** using different file for CSS
* **Inline Styles:** using CSS in particular elements


##### N.B. External Stylesheets is recommended but others can be also used when needed 

___

## How to connect CSS with HTML?

In the HTML file, we will add the following line -

``` html
<link rel="stylesheet" href="styles.css" />
```

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

If we want to make all the elements into a specific style we use `*` as follows:

 ``` css
* {
  color: purple;
}
  ```

___
##  Selectors Specificty

While coding sometimes triggers the same elements more than once like below:

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

Border takes three values thickness, style, and color. There are different types of styles `dashed`, `solid`, and so on. Something to remember while using `border-width` it takes 4 values in the following order  **Top-Right-Bottom-Left**. We can also use `border-color`, `border-radius` and so on.

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

![boxmodel](https://user-images.githubusercontent.com/31423599/109760921-c5d48d00-7c19-11eb-8081-4b38fb4e2015.png)


___

## Overflow

Sometimes in a fixed-sized element, overflow happens. In those cases, we use `overflow: hidden;` to hide the overflowed content or we can also use `overflow: scroll;` or `overflow: auto;`. To contol by the X (Horizontal) and Y (Vertical) axis by using two values like `overflow: hidden auto;`.

___

## Measurement Units

There are two types of Measuring Categories:

* Absolute
* Relative 

In **Absolute** there is **px (Pixel)** and in **Relative** there are **% (Percentage)** which is relative to the size of the container, **vw (Viewport Width)** and **vh (Viewport Height)** which is relative to the viewport, and lastly **rem (The root element's font-size)** and **em** which is relative to the font size.   
 



___

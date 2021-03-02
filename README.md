# CSS Cheatsheet 

> CSS which stands for Cascading Style Sheets which is a Styling Language. This is an initiative to make small notes on CSS which may help me or anyone else in the future while coding

___

Starting with the basic, there are **three ways of using CSS**:

* **Embedded Stylesheets:** using CSS inside HTML file 
* **External Stylesheets:** using different file for CSS
* **Inline Styles:** using CSS in particular elements


##### N.B. External Stylesheets is recommended but others can be also used when needed 

___

### How to connect CSS with HTML?

In the HTML file, we will add the following line -

```
<link rel="stylesheet" href="styles.css" />
```

___

### Normalizing CSS

As there are different browsers and they render some HTML elements differently. So [normalize.css](https://necolas.github.io/normalize.css/8.0.1/normalize.css) is a stylesheet that provides a basic default style.  

___

### Basic Selectors

We can select elements for styling in the following ways:

* **Type:** Choosing an element by type
* **ID:** Choosing an element by ID and can be used in a single element
* **Class:** Choosing an element by Class and can be used in multiple elements  
* **Attribute:**  Choosing an element by Attribute but it is not recommended 

___

### Relational Selectors

As we know the basic selectors, we can also use some relational selectors too

*  **Descendant Selector:** Choosing an element by **ID** and **Type** like below
	
  ``` css
  #products p {
    color: purple;
  }
  ```
  
And if you want to change only the first decent or direct child use the following code

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
  
And if you want to choose all the elements after the chosen one

 ``` css
  #products ~ p {
    color: purple;
  }
  ```
  
So in the above two codes, in the first one after **products** the first **p** will be purple and in the second one after **product**, all **p** will be purple.
  
___

###  Pseudo-class Selectors

Pseudo-class is not something we define it’s something which the browser defines.

 ``` css
  article :first-class {
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

Let say you want all the even number of a list purple. We will use the following code:

 ``` css
  ul li:nth-child(even) {
  color: purple;
}
  ```
We can also use **even** and also **formula** like 3n.

___



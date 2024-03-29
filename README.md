## HTML(Hypertext Markup Language)
HTML is a markup language used to structure content on the web. It provides a standardized way to create and organize text, images, links, forms, and other types of content within a web page.
## Create an 'index.html'
1. open a vscode workplace

2. Create and name your first 'index.html'
    Right click / double click to create your first 'index.html'.
    ***Note:*** You can also drag your folder into workplace.

3. The tempplate!

    Type `!`, then get the boilerplate as below:
    ```html
    <!DOCTYPE html>
    <!-- The lang attribute in the <html> tag is used to specify the language of the document. -->
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <!-- Your code is here. -->
        <header>
            <h1>Demo: HTML</h1>

            <nav>
                <ul>
                    <li>
                        <a href = "URL"></a>
                    </li>
                    <li>
                        <a href = "URL"></a>
                    </li>
                    <li>Third item</li>
                </ul>
            </nav>
        </header>

        <figure> 
            <img src="path/pic.gif">
            <figcaption> Figure 1.1: An image </figcaption>
        </figure>

    </body>
    </html>
    ```

4. Get the extention to speed your coding!

    `Live Server`: used in web development to create a local development server and provide live reloading functionality.
    `Prettier`: code formatter

    ***Note:*** Live Server automatically reloads the web page in the browser whenever changes are made to the source code. 


### NOTE:
* `<body></body>`: choose the right elements to start coding.

* What are the differents of article, section, div?
    
    1. Semantic elements:Use `<article>`, `<figure>`
        The details of how to locate the local imgs can be found :https://synapse.brainstation.io/software-engineering-bootcamp/student-content/00a30322-4623-551a-8ad5-e033d62f59c2-->

        
        * for example: 
        ```html
        <figure> 
            <img src="path/pic.gif">
            <figcaption> Figure 1.1: An image </figcaption>
        </figure>
        ```
    2. No Semantic elements: Use `<section> `,`<div>`
    
* Format of elements:
`<element attribute="value">Content</element>`

* `MDN`: helps you seach for html elements and descriptions.

## CSS (Cascading Style Sheets):
CSS is a style sheet language used to control the presentation and layout of HTML documents. It enables designers and developers to apply styles, such as colors, fonts, spacing, and positioning, to enhance the visual appeal and user experience of a web page.
## Create an 'styles.css'

***Note:*** Type `space` when coding will not be reflected in the live pages.

**cascade** and **specifity** tell us which rules apply to different elements in the case that two rules conflict.


Example:
```html
<h1 class = "featured">Content</h1>
```
```css
h1{
    color: white;

}
.featured{
    color: red;

}
```
`white` will be overwrited by `red` since `.featured` is much more specific.

We can find the more details about selectors: https://synapse.brainstation.io/software-engineering-bootcamp/student-content/3a7f3fbc-0ffe-560b-9ebc-8d8ac5298eca


**1. General specificity**
![General specificity](img/specifcity.png)

* Element Selectors 
    ```css
    /* Link the stylesheet to any .html */
    <link rel="stylesheet" href = "./PATH/FILENAME.css">

    body{
        background-color:pink;
        font-family:sans-serif;
    }
    /* `;` IMPORTANT! */
    ul{
        list-style-type: none;
        margin: 0;
        padding: 0;
    }

    li{
        display: inline-block;
        margin-right: 1rem;
    }
    ...

    ```
    Element selectors are to the styling for the elements.

* Class Selectors

    Add attribute class `featured` to an element, any elements contain this class will be changed by `featured`.
    ```styles.css
    .featured{
        background-color:yellow;
        color:purple;
    }
    ```
    Used in `.html`
    ```html
    <a href = "./path/link" class = "featured">Content<a>

    <h2> The basic of <span class = "featured">HTML </h2>
    ```

* ID Selectors
    ```css
    #first-paragraph{
        font-weight:bold;
    }
    ```
    Used in `.html`
    ```html
    <p id = "first-paragraph"> This is a demo</p>
    ```


**2. Equal Specificity**

Two cases:

a. Equally specific selectors do not define the same property

    ANS: all the properties got applied

b. Equally specific selectors define the same property - > conflict
    
    ANS: The most recent property get applied (color black) since the previous one got overwrited.

![Equal Specificity](img/equal.png)

***Note:***
* What if we still want to apply the first rule?

    ANS: Be more specific when defining the color

![alt text](img/equal2.png)



3. Complex selectors

* **Multiple selectors**

![Multiple selectors](img/multiple.png)

* **Grouped selectors**

![Grouped selector](img/grouped.png)

* **Descendant selectors**

![Descendant selectors](img/descendant.png)

* **Child selectors**
![Child selectors](img/child.png)

4. The Cascade
When there are multiple possible values for a property of an element, the browser needs to decide which value should take precedence. It does this by considering how specific the styles are.

The specificity of a style rule, from most specific to least specific, are as follows:

* `!important`(1,0,0,0,0): highest priority for styling.
* Styles specified inline (from the style attribute)
    *  Inline style(1,0,0,0): apply the style directly into the elements.

*  Styles from ID selectors
    * ID selector(1,0,0) - > 100

* Styles from Class selectors
    * Class selector(0,1,0) - > 010

* Styles from Tag selectors
    * Element selector(0,0,1) - > 001

* Inherited styles

* Default styling

![alt text](img/selectors.png)

    ```css
    /* Equal specificity: order is important*/
    .class-one{
        color: greenyellow;
    }
    .class-two{
        color:lightsalmon;
    }

    /* Multiple selectors*/
    .class-one.class-two{
        color:orange;
    }

    /*Grouped selectors*/
    .class-one,
    #special-element{
        font-weight: bold;
        font-size:150%;
        color: black;
    }

    /*Fine example*/
     .class-one#special-element{
        font-weight: bold;
        font-size:150%;
        color: black;
    }


    .grandparent{
        margin:2px;
    }

    /* Descendant selector*/
     .grandparent .child{
        background-color: yellow;
    }

    /*child selectors*/
    .grandparent > .parent{
        background-color: pink;
    }

    /* Pseudo-classes: every two */
    ul>li:nth-of-type(2n){
        color: lightseagreen
    }


    div{
        color:white !important;
    }

    ```

## CSS Units
CSS Units refer to the possible units of measurement for CSS properties.

**Absolute**
Absolute length units are fixed in relation to each other. They are mainly used in an already known (development) environment (iPhone, tablet).

* px
    * widely used
    * ~0.26mm (CSS pixel)
    * 1 px in desktop not the same as that in mobile device
* cm, inches, mm (x)
    * Rarely used

**Relative**
specify a length relative to another length.
* % 
    * Relative to containing block
    * Containing block needs to hav a value set
    * Great for defining widths
* em, rem 
    * Relative to font size of current element (em). 
        * The em unit allows setting the font size of an element relative to the font size of its parent. When the size of the parent element changes, the size of the child changes automatically.
        * Note: When em units are used on font-size property, the size is relative to the font-size of the parent. When used on other properties, it’s relative to the font-size of that element itself. Here, only the first declaration takes the reference of the parent.
    * Relative to root font size (rem).
        * The rem is based upon the font-size value of the root element, which is the <html> element. And if the <html> element doesn’t have a specified font-size, the browser default value of 16px is used.
    * ref: https://www.geeksforgeeks.org/difference-between-em-and-rem-units-in-css/
![rem/em for an example](img/rem-em.png)
* vh,vw
    * Relative to 1% of viewport height or width （1 vh/vw）
    * shrink with height/width
    * vh is great for making full height banners
* vmin
    * Relative to 1% of viewport smallest side (vh or vw)
* vmax
    * Relative to 1% of viewport largest side (vh or vw)

***NOTE:***

1. Browser has default margin set.
![Margin, border, padding](img/structure.png)
2. `width: unset` unset the parent relation
3. Font size is bigger than the parent box (if height of parent is fixed and child is bigger than current box)
4. viewpoint represents the visible area of a web page in a browser.

## CSS Display
To display the HTML positions elements.

1. Display property has four values
* block
Default: <p><div>
![block](img/block.png)
* inline-block
Default: <img><button>
![inline-block](img/inlineblock.png)
* inline
Default: <span><a>
    Often used for text/paragraphs
![inline](img/inline.png)

2. Hiding/Showing

`display` keeps spaces while `visiblility` does not keep the space

![Hiding and Showing elements](img/showing.png)


```css
<!--Click on and showing/displaying answer-->
.reveal-answer:hover{

}

.reveal-answer:hover ~ .answer{
}

```

# Flex
Advancded understanding to box layout

Last week we have learnt what was`block/inline-block`, here we discussed `flex` which avoids use of tricks to handle alignment such as centering.

Basic info:
* `flex-direction`: `row`(default), `row-reverse`, `column` and `column-reverse`
* **flex container**: element with `display` property set to `flex`
* **flex items**: The child elements of a flex container.
![Flex](img/flex.png)

Alignment info:
* `justify-content`: align the contents along the row axis
![justify-content](img/justify-content.png)
![justify-content2](img/justify-content2.png)
* `align-items`: align the content along the column axis
![alt text](img/align-item.png)
* `flex-wrap`: to the next line if it does not fit in the available space.
* Vertical & Horizontal Centering
```css
.container{
    display:flex;
    justify-content: center;
    align-items:center;
}
.flex-items{
    margin:auto;
}
```

* `align-self`:
![align-self](img/algn-self.png)

* `flex-flow`: `row nowrap`(default), `flex-flow:<flex-direction> <flex-wrap>

* `align-content`: 

![alt text](img/align-content.png)

* Order of child elements

![alt text](img/order.png)

* flew-grow: the remaining space of a **flex item**, default is 0

* flew-shrink: the space of a **flex item** takes up, default is 1

## Telling your story

lean into the passion to

Passion 
Desire 
Education
![alt text](img/craftstory.png)
![alt text](img/craftstory-template.png)

## Position&flow

Control the flow of the elments in the page.

```css
.css_container{
    position:static|fixed|absolute| relative;

}
```
* `relative/absolute`
For example, a grey shadow box is above the background image. And assume the content of the grey shadow is larger then the container. (Apply `overflow:hidden` if the content overflow the parent box.)
```css
.css_container{
    position:relative;
    overflow:hidden;

}
<!--Hide the content and roll up if requried for appreaing-->
.css_text{
    position:absolute;
    top:180px;
    transition:0.5s

}
.css_text:hover{
    top:0;
}
```

* `fixed`
Fix the position of the element in the viewpoint. 

For example, a navigation is expected to be fixed on top of the pag always.

```css
.nav{
    position:fixed;    
}
```

`z-index`: The stack level of the box in the current stacking context

*`float`
Allow text elements to flow around the image. **Not** used for layout.


For example: locate an image on the left and let the text flow around it. The image is assumed as a cirle shape.
```css
img{
    float: left;
    shape-outside: circle(50%)
}
```
## Sass
It is like to define the globle variables of the values of properties which is much more rewritable for CSS code in future.
![SASS](https://www.w3schools.com/sass/sass_variables.php)

Features:

1. Variables: `$<variable_name>`
```SCSS
$primary-color:#333;
body{
    color:$primary-color
}
```
2. Mixins: `@mixin` + `@include`
```SCSS
@mixin border-radius($radius){
    border-radius:$radius;
    margin:0;
}
.box{
    @include border-radius(10px);
}
```
3. Extend: `@extend` 

## Typography

## Responsive 
```SCSS
@media (min-width:600px){
  body{
    background-color: #8ddaf8;
  .site-header{
    &__wrapper{
      flex-direction:row;
      }
  }
  .card{
    width:50%
  }
  }
}
```
* `@media (min-width: 600px)`: A media query specifying a condition that the viewport's minimum width must be 600 pixels or more for the styles inside the media query to take effect.

* `body { background-color: #8ddaf8;}`: When the viewport width meets the condition, the background color of the body element is set to #8ddaf8.

* `.site-header__wrapper { flex-direction: row; }`: If an element with the class `.site-header__wrapper` exists, its flex-direction property is set to row. This is commonly used in Flexbox layouts to arrange its child elements horizontally.

* `.card { width: 50%; }`: If an element with the class .card exists, its width is set to 50% of the viewport width. This can make card elements occupy a certain width on larger screens.

The purpose of the code is to adjust the styles of page elements based on different viewport widths, aiming to provide a better user experience on various devices. This concept is fundamental to responsive design.


 
 ## Media Query
 A max-width media query triggers styles for smaller screens when the viewport or device width is less than a certain number or pixels. It is the maximum width before styles stop being applied. CSS styles are ordered from largest to smallest.

 `_variables.scss`:
 ```scss
 $tablet-breakpoint: 768px;
```
Import `__variables.scss` in `_mixins.scss`:
 ```scss
@use 'variables' as *;

@mixin tablet {
  @media screen and (min-width: $tablet-breakpoint) {
    @content;
  }
}
```
In `main.scss`, here is the content in the scss file as `@content;`


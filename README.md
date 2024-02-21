# HTML(Hypertext Markup Language)
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

# CSS (Cascading Style Sheets):
CSS is a style sheet language used to control the presentation and layout of HTML documents. It enables designers and developers to apply styles, such as colors, fonts, spacing, and positioning, to enhance the visual appeal and user experience of a web page.
## Create an 'styles.css'
***Note:*** Type `space` when coding will not be reflected in the live pages.


1. Element Selectors 
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
2. Class Selectors

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

3. ID Selectors
```css
#first-paragraph{
    font-weight:bold;
}
```
Used in `.html`
```html
<p id = "first-paragraph"> This is a demo</p>
```

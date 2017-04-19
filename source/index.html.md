---
title: Tweak User Guide

language_tabs:
  - html
  - css
  - javascript

toc_footers:
  - <a href='https://tweak.crewspace.io'>Get Tweak</a>

search: true
---

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-template-2/images/tweak-share-img.png)
# Introduction

Welcome to Tweak User Guide. Tweak is a Chrome Extension that allows you to design in the browser. 

It gives you the benefits of visual design tools on your browser while still using your HTML and CSS. With a click on the extension the page becomes editable and you can add elements and sections.

Use this guide as a reference to get the most out of Tweak.

# Installing

1. Install Nodejs:[https://nodejs.org/en/download/](https://nodejs.org/en/download/) (Required for Tweak server)
3. Install Chrome: [https://www.google.com/chrome/browser/desktop/index.html](https://www.google.com/chrome/browser/desktop/index.html)
2. Install Tweak Chrome Extension: [https://tweak.crewspace.io/](https://tweak.crewspace.io/)

#Launching Tweak
Click Tweak browser icon after installing the extension.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/browser-action.png)

If prompted login or signup using your gmail credentials.

Choose a template to start from.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-18+at+15.33.22.png)

# Setting up Tweak template
##Installing Tweak server
Templates come with local instance of Tweak server. Tweak requires a server to serve the page, which Tweak can then access through the browser. In theory Tweak can be used with any server, however only with Tweak server is it possible to use save and live reload features.

Download and extract a template to a location of your choice.

To install the server instance of the template execute using a termincal or command line from the template folder:

`npm install`
##Starting Tweak server
To start the server and serve the Tweak template on your browser execute from the template folder:

`npm start`

This will serve the page at the address: `http://localhost:8080`

#Editing a page
Make sure you have Tweak server running and serving a Tweak template. 

Simple click the Tweak browser icon to start editing the page with Tweak.

Now all the elements in the page are editable in the browser.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-03+at+12.50.29.png)


##Adding a section 
To add a section click on Tweak Floating Action Button on the bottom left, and click on add.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-18+at+16.14.44.png)

This will open the add sidebar, choose sections from the sidebar tab and click on the section you want to add.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-18+at+13.02.47.png)

Add section indicators will appear on the page, click on the position where you want to add the section.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-18+at+16.21.19.png)


##Editing a section
On the left side of each section there is section actions. These actions are:

1. Section background
2. Remove section

Additionally each section height can be resized by dragging the section from the bottom border.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-18+at+16.06.08.png)

##Adding an element 
To add an element click on Tweak Floating Action Button on the bottom left, and click on add.

This will open the add sidebar, choose elements from the sidebar tab and click on the element you want to add.

Click on the section that you want to add the element to.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-18+at+13.06.37.png)

##Editing an element
When an element is clicked element actions will appear above the element. These actios are:

1. Edit (Only on text and button elements)
2. Text align actions (Only on text and button elements)
3. Remove element
4. Element color

Additionally each element can be dragged and position absolutely relative to its parent section. Elements can be also resized by dragging them from left or right border.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-18+at+16.33.04.png)

##Mobile layout
To switch to mobile layout click on Tweak Floating Action Button on the bottom left and choose mobile view.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/desktop-mobile.png)

In mobile view all elements that are within the inner narrow border of the section will be drawn on the screen.

##Save/Download
###Save (Tweak server only)
Save action is only available with Tweak server. To save simply click on the Tweak Floating Action Button on the bottom left and choose save. This will save all the changes of the page.

###Download
Download action is available when there is no Tweak server running and the page is server by other server. 
To download simply click on the Tweak Floating Action Button on the bottom left and choose download. 

This will generate a zip file that contains index.html and a css file. Replace the old index.html with the extracted index.html and copy the css file to the css folder of your page.

#Customizing a Tweak template
To truly get the full benefit of Tweak, you need some HTML and CSS knowledge to create your own custom components and sections.

Tweak templates are normal HTML and CSS files, making it very simple to customize.

![alt_text](https://s3.eu-central-1.amazonaws.com/tweak-documentation-assets/Screen+Shot+2017-04-18+at+15.51.34.png)

##Sections

```html
	<div class="section" style="height: 500px">
        <div class="section-inner"></div>
    </div>
```

```css
	.section {
    position: relative;
    width: 100%
  }
```

```css
	.section-inner {
    position: relative;
    max-width: 960px;
    margin: 0 auto;
    height: 100%
  }
```

A section must be a div HTML element, and have the class section. 
The class section has the width 100%, the initial height of the section must be defined in the sections.html.

Inner section is a child of section. It has the maximum width of 960px and is the container of components. 
On hand held devices inner section is 100%, any component outside it’s width borders on the mobile view is not drawn on the screen.


##Adding a custom section
Launch the Tweak server of the template that you want to customize and on the browser click on the Tweak browser action. Go to the directory the templates directory. Open sections.html in code editor of your choice.

On sections.html are listed all the sections of the Tweak template. Add a section with the height 750px. 

Add nice gradient background to the section by giving it a child div with the class nice-gradient. In the main.css add new style for the nice-gradient.

```html
	<div class="section" style="height: 750px">
        <div class="nice-gradient"></div>
        <div class="section-inner"></div>
    </div>
```

```css
	.nice-gradient {
    height: 100%;
    width: 100%;
    overflow: hidden;
    background-image: linear-gradient(150deg, #3f51b1 0%, #5a55ae 13%, #7b5fac 25%, #8f6aae 38%, #a86aa4 50%, #cc6b8e 62%, #f18271 75%, #f3a469 87%, #f7c978 100%);
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
  }
```

Now back on your browser open Tweak add sidebar and open the sections tab, if your sections tab was already open click on the refresh icon.
Your newly added section should appear now there.

##Components

```html
    <div class="component" style="width: 100px">
        <h1 class="logo-text">tweak</h1>
    </div>
```

```css
	.component {
    position: absolute;
  }

  .component img {
    width: 100%;
  }
```

Component is the containing div of elements that can be positioned using Tweak. 
Component is absolutely positioned relative to inner section. 
Component can contain any HTML element (p, div, span, h1, h2, h3, input, button etc).


##Adding a custom element
Launch the Tweak server of the template that you want to customize and on the browser click on the Tweak browser action. Go to the directory the templates directory. Open components.html in code editor of your choice.

On compnents.html are listed all the elements of the Tweak template. 
Add a component with the width 200px and an anchor child element with the class example-button.

In the main.css add new style for the example-button.

```html
	<div class="component" style="width: 200px">
        <a href="" class="example-button">Example button</a>
    </div>
```

```css
	.example-button {
    color: #3f51b1;
    white-space: nowrap;
    display: inline-block;
    height: 40px;
    line-height: 40px;
    padding: 0;
    box-shadow: 0 4px 6px rgba(50, 50, 93, .11), 0 1px 3px rgba(0, 0, 0, .08);
    background: #fff;
    border-radius: 4px;
    font-size: 15px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: .025em;
    width: 100%;
    text-decoration: none;
    text-align: center;
  }
```

Now back on your browser open Tweak add sidebar and open the elements tab, if your elements tab was already open click on the refresh icon.
Your newly added element should appear now there.

##Editing CSS with livereload

Tweak fully supports editing the projects CSS in a code editor of your choice. Infact this is the reccomended way of using Tweak. 
You can also use CSS preprocessor of your choice (LESS, SASS, etc) as long as the output CSS is saved on the css folder.

Tweak server listens for changes in the CSS folder and when it detects them it will notify the browser and the CSS stylesheets will be reloaded automatically on the served page.


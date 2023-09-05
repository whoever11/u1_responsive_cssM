<img src="https://i.imgur.com/RZwMZi2.png">

# Responsive Web Design

---
## Learning Objectives

| Students Will Be Able To: |
| --- |
| Describe what Responsive Design is |
| Explain the benefits of Mobile First design |
| Use CSS Media Queries to alter page layout and styling |

## Road Map

1. Setup
2. Intro to Responsive Web Design
3. Examples of Responsive Design
4. Mobile First Design Philosophy
5. First Step to Enabling a Better Experience on Mobile
6. Using Media Queries to Apply Different CSS Rules to a Page
7. Essential Questions
8. References


## Breakpoints and Media Queries



For this lesson we will be working with Media Queries to conditionally resize our pages based off the size of the devices you are using.


The main code we want to use in our CSS looks something like this:

```
@media screen and (max-width: 800px) {

<-CSS Code goes here ->

}
````


## 1. Setup

To experiment with responsive design, open up a new HTML/CSS file and paste the following HTML into the body:

<body>

  <header>
    <h1> Responsive CSS</h1>
  </header>

  <nav id="navbar">  
    <button> Login </button>
    <button> Register </button>
    <button> Sign Out </button>
  </nav>

  <div>

    
  </div>

  
</body>




## 2. Intro to Responsive Web Design

### Background

Not that long ago, building a successful online presence meant just ensuring that your website worked correctly in all the major desktop browsers. 

Fast-forward to today and desktop browsing has rapidly been replaced by surfing on our mobile devices.

Over 87% percent of the world's population now own a smartphone and 92.3% of internet users access the internet using a mobile phone.

It's becoming more and more important that our web apps be usable via mobile devices!

### Enter - Responsive Web Design

[Responsive Web Design](https://en.wikipedia.org/wiki/Responsive_web_design), refers to the process of making web pages display and function correctly on a variety of devices.

Specifically, the most important criteria to respond to is the **width** of the device's screen.

#### What specifically responds/adapts?

Primarily, the overall layout of the page.

But you can pretty much change anything on the page you want.  For example, I'm sure you've seen the menu links in a navigation bar disappear and be replaced with a "hamburger" icon before.

Take a look at the image at the top of this lesson too - notice how the number of columns changes?

Now that we know what Responsive Design is, let's look at some real-world examples out there.

## 3. Examples of Responsive Design

An excellent example of a responsive site is one you've become very familiar with, [GitHub](https://github.com/).

For another example, check out the [Bootstrap](https://getbootstrap.com/) CSS framework's site.

## 4. Mobile First Design Philosophy

When designing and coding the base/main CSS for a site or app, there are two approaches that can be followed:

1. Write the base CSS for a large, desktop screen, then apply "new" CSS (using media queries) as the screen width **decreases**, or
2. Write the starting CSS for a mobile screen, then apply additional CSS as the width **increases**.

The experts tell us that it's better to use the second, **mobile-first**, approach for the following reasons:

- Translating the design from mobile to desktop is easier than vice-versa, thus it should require less time to build the site.
- Mobile-first encourages you to think about what content is the most important - and prioritize it.
- It's easier to detect performance related issues - such as the slow loading of large image files - on mobile devices, and it's better to deal with performance issues early-on.
- A design based on a small screen-width (although not ideal) will still display correctly on larger devices, where the reverse is often not the case.

## 5. First Step to Enabling a Better Experience on Mobile

For those of us who remember using smartphones to browse the web when they first came out, will also remember seeing tiny, unreadable content like this:

<img src="https://i.imgur.com/BXhiZRF.jpg">

Unlike on desktop browsers that render pixel-by-pixel, mobile browsers first render to a *virtual* **viewport** and then shrink the page to fit the screen.

For example, the browser internally might render the webpage virtually at 980px then display it by shrinking it down to the device's actual screen size, e.g., 640px.  This is what leads to the scenario seen above.

To improve this situation, Apple introduced the "viewport meta tag"...

#### `<meta name="viewport" ...>` to the Rescue

The viewport [`<meta name="viewport" ...>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag) informs the browser not to scale the page as seen above, and instead to display the content based upon the physical number of pixels available - just like desktop browsers do.

This viewport `meta` tag is **so** important, that tools such as Emmet/VS Code add it automatically in the HTML boilerplate.

The following should look familiar...

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

With that `meta` tag in the document's `head` element, the above page will now render as:

<img src="https://i.imgur.com/hdSBUzg.jpg">

Much better! Be sure to always have `<meta name="viewport" ...>` in every web app you write!

## 6. Using Media Queries to Apply Different CSS Rules to a Page

### What's a Media Query?

A [media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) provides a way to **conditionally** include CSS rules.

A media query contains its own section of CSS that is used to modify the current CSS when certain "media" conditions exist.

The media query can be composed of any number of _media feature expressions_, such as `(min-width: 768px)`, and optional _media types_, such as `print`, `screen`, or `all`.

### Our First Media Query

Let's add a media query to improve our current layout for devices **larger** than mobile.

The following conditionally adds CSS as the screen increases in width, to at least 768 pixels - typically considered a common "breakpoint" width for tablets:

```css
@media only screen and (min-width: 768px) {
  body {
    background-color: red
  }
}
```

Note that we only add CSS declarations for the properties we want to change - Don't repeat any of the CSS **above** the media query.

Resize the window and check it out!

### Order May Matter

Be sure to put media queries **after** the "base" CSS rules in the stylesheet.

Also, the ordering of the media queries themselves may matter. For example:

```css
/* Base CSS */
* {
  color: red;
}

/* Desktop Device CSS */
@media (min-width: 1024px) {
  * {
    color: green;
  }
}

/* Tablet Device CSS */
@media (min-width: 768px) {
  * {
    color: blue;
  }
}
```

❓ Do you see why there can never be any green text?




### Adding More :

Lets change up our Navbar to be spaced out according to our size, and then change the display types of our images, so that we only see the ones we want at certain sizes!

```CSS
#image1 {
display: block}
#image2 {
display: none}
```

And convert it to this:

```CSS
#image1 {
display: none}
#image2 {
display: block}
```

### 👉 YOU DO - Media Query (5 min)

- Add another media query with a breakpoint of `(min-width: 1024px)` (a common breakpoint width for desktop displays).

- Within the media query, add some CSS to change the `color` property of at least one element.

- Within the media query, add some CSS to change the `background-color` property of at least one element.

<hr>

Let's wrap up with a few review questions...


## 8. References

[MDN - Using media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)

[MDN - grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas)


We can change up these values based of what sized devices we are expecting users to use.


## Standard breakpoints and widths

- Large Screen Monitor :  1200px 

- Standard Monitor : 1000px

- Tablet (Landscape) : 800px

- Table (Portrait) : 600px

- Phone (Landscape) : 450px

- Phone (Portrait) : 400px

- Apple Watch : 200px


First, lets try something simple, just changing the background color when the screen gets a bit smaller


```
@media screen and (max-width: 800px) {

body {
background-color: aqua;

}
````
We are creating a new block of scope with this, which means we can change up anything we want. Lets take it a step further and make our font a bit smaller when we get to this size


```
@media screen and (max-width: 800px) {

  body {
     background-color: aqua;
  }


  h1 {
    font-size: 20px;
  }
}
````

We can run multiple media queries with breakpoints, but just know that the order of numbers will matter due to the Cascading nature of CSS. Having a Max-width of 500 under a Max-width of 300 is not going to do what you want it to do!


Its not just things like colors and fonts that can change. Lets create a Nav element in our HTML, put 3 buttons in it, and make it so when we have it as a flex row in standard view, but in a column at a smaller view. 



```

@media screen and (max-width: 800px) {

  body {
    background-color: aqua;
  }

  nav{
    display: flex
  }
}

@media screen and (max-width: 500px) {
  nav {
    flex-direction: column
  }
}
````

Notice how the "display: flex" will still be inherited into the smaller block at 500px, you do not need to re-enter that for each.


There are many different ways to play with responsive code. Changing font sizes, Flex Directions, Grid Columns, and setting larger elements to have a display of "none" while in small sizes are just a few of the different things we can do. Play around, look at existing pages you can work off of, and challenge yourself to create professional looking, responsive web pages!

Lets throw 2 images in our html with Id's of "image1" and "image2". Give one a display of "block", and the other "none" in the main CSS scope. Then put this in your CSS and watch what happens as one image vanishes, and the other appears in its place!




```
@media screen and (max-width: 500px) {
  #image1 {
    display: none
  }
  
  
  #image2 {
    display: block
  }
}
```


## Breakpoints and Media Queries



For this lesson we will be working with Media Queries to conditionally resize our pages based off the size of the devices you are using.


The main code we want to use in our CSS looks something like this:

```
@media screen and (max-width: 800px) {

<-CSS Code goes here ->

}
````

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

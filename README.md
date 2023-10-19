# CSS Explained

I have worked with CSS for quite a while at this point, and there is now so much of it that it can be quite hard for newcommers to properly understand what each ...

## Grid

CSS grid is one of the advanced display methods...

### Template Areas

Grid template areas are often the best, and most certainly the most straight forward way of defining and managing a grid. They allow you to name sections of the grid, and then use those names to position elements inside that section of the grid.

The following example uses the whole viewport. It splits it up into a navbar, three content sections and a footer. This is all achieved with one grid.

```css
.layout {
    /* set display to grid */
    display: grid;

    /* define the areas of the grid */
    grid-template-areas: 
        "nav nav nav"
        "content1 content2 content3"
        "footer footer footer";

    /* set height of each row in the grid */
    grid-template-rows: 100px calc(100vh - 200px) 100px;

    /* same as above can be done for columns (grid-template-columns)
    but is not needed for example */
    
    & .navbar {
        /* setting the grid area of the div with this class
        NOTE: while in the layout class the area was defined
        as a string, here it is not referenced as a string */
        grid-area: nav;
    }

    & .content:nth-child(1) {
        grid-area: content1;
    }

    & .content:nth-child(2) {
        grid-area: content2;
    }

    & .content:nth-child(3) {
        grid-area: content3;
    }

    & .footer {
        grid-area: footer;
    }
}
```

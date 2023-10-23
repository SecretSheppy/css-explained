# CSS Explained

I have worked with CSS for quite a while at this point, and there is now so much of it that it can be quite hard for 
newcomers to properly understand what each ...

## Nesting

CSS Nesting is a relatively new (at time of writing) and actually isn't yet fully supported by all web browsers, however
as it will more than likely become standard at some point, and because I just like it, all the demonstrations in this
document written with it. Due to that, I'll start by explaining CSS nesting and why you should adopt it.

### Why Nesting?

CSS nesting allows you to write classes inside other classes. This is useful for a number of reasons, but the main
one is that you don't have to write the class names out over and over again (which is not only quicker but more
efficient). At time of writing it is only fully supported by firefox (on both mobile and desktop), however the majority
of it is supported on most browsers.

### Nesting Example

```css

```

## Selectors

### Before & After

```css
.speech {
    /* ... */
    &::before,
    &::after {
        content : "\"";
    }
}
```

## Grid

CSS grid is one of the advanced display methods...

### Template Areas

Grid template areas are often the best, and most certainly the most straight forward way of defining and managing a 
grid. They allow you to name sections of the grid, and then use those names to position elements inside that section of
the grid.

The following example uses the whole viewport. It splits it up into a navbar, three content sections and a footer. This
is all achieved with one grid.

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

Add some color and format it correctly, you'll get the following result.

<div align="center">
    <img src="grid-template-areas/result.png" alt="grid-template-area-result" style="width: 450px;">
</div>

# CSS-Grid

---
##  Overview
---

Flexbox is a new (ish) specification that allows us to create expressive 2D grid formats in CSS. It allows us to bypass libraries like bootstrap based column system is with over 90% browser share it's now ready for prime time.

An added bonus is cleaner markup as we no longer need express our markup with HTML.

---
##  The basics
---

### Setup


`display` - Set to grid to enable CSS grid

### Properties

`grid-gap` - How many PX we wish to have between each item

`grid-template-columns` - Define how many columns we want the grid to have

> `10px auto 100px` - This is the more explicit way to create 3 different size columns

> `repeat(3, 1fr)` - Shorthand for # of columns, size of each

`grid-template-columns` - Define how many rows we want (e.g `100px auto 10px`)

---
##  Positioning / Sizing
---

We can set individual grid elements width using the `grid-column-start` and `grid-column-end` properties, or for the shorthand form just use `grid-column` / `grid-row`

### __[Demo](https://codesandbox.io/s/200p886lyn)__

Another cool way of reperesing the shape of our grid is using a `grid-template-area`. These are a super simple and expressive way of expressing our layout
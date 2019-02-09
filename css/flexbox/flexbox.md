# Flexbox

##  Basic flexbox
---

If we begin with a basic set of three `<div/>` elements they will be rendered below eachother as they are all block level elements ( Meaning they will span 100% of available parent width );

```html
  <nav class="container">
      <div>Home</div>
      <div>Search</div>
      <div>Logout</div>
  </nav>
```

Renders like so

```
------------------------------------------------------------
  Home
  ------------------------------------------------------------
  Search
  ------------------------------------------------------------
  Logout
  ------------------------------------------------------------
```

> Display: flex;

By adding display:flex to our container we'll render them from left-right ( By default flex-box distributes content from LEFT to RIGHT ).

The reason we go from left-right by default is due to the *main axis* defaulting to being horizonal, with the cross axis being vertical

```css
  .container {
    display: flex;
  }
```

```
  ------------------------------------------------------------
   Home | Search | Logout
  -------------------------------------------------------------
```

---
##  Flex direction
---

By providing a `flex-direction` we control whether the main axis flows along the vertical or the horizonal. I.E above our content is set to the default left to right behaviour ( `flex-direction: row` ). By changing the `row` property to `column` we can go from to bottom  ( `flex-direction: column ` ).

---
## Aligning the content
---

The default behaviour will force items to squeeze over on the left hand side. Most likely we will want some space between them, Or push them over to the right hand side of the container

We can more granularly control how things are laid out along the main axis via the following attributes

> justify-content

`flex-start` - The default behaviour of rendering from the left hand side

`flex-end` - Right hand side ( end of the main axis )

`center` - Center along the main axis

`space-around` - Equal space between left / right hand side

### __[Demo](https://codesandbox.io/s/rlmy2my30m)__

> align-items

the `align-items` is the property which controls items along the cross-axis similar to the `justify-content`.

### __[Demo](https://codesandbox.io/s/6x816o3v5n)__


---
## Positioning items
---

> Margins

The justify content do not always quite have the customisation we need ( E.g we need item 1 on the left hand side, but 2 + 3 on the right hand side)

In order to do this we'll need to individually target the children elements to position them along the main axis.

```html
  <div class="container">
      <div class="home">Home</div>
      <div class="search">Search</div>
      <div class="logout">Logout</div>
  </div>
```

```css
  .container {
    display: flex;
  }

  .search {
    margin-left: auto;
  }
```

```
  ------------------------------------------------------------
   Home |                                      Search | Logout
  ------------------------------------------------------------
```

Another way to achieve this layout, Is to render all items on the right, and then push the home to the left instead

```css
  .container {
    display: flex;
    justify-content: flex-end;
  }

  .home {
    margin-right: auto;
  }
```

```
  ------------------------------------------------------------
   Home |                                      Search | Logout
  ------------------------------------------------------------
```

> Flex property

If we want all items to stretch across all the main-axis, and grow / shrink with it we can use the `flex` property.

This allows us to not worry about setting widths, and will mean additional items can be easily applied into the new layout.

### __[Demo](https://codesandbox.io/s/l34x2j31vm)__

This are all shorthand for properties

`flex-grow` ( default zero for all children ) - How much of the extra space should be distributed to the additional items

`flex-shrink` ( Default 1 for all children )

`flex-basis` - This sets the base width of the element

### __[Demo](https://codesandbox.io/s/lyw76o6737)__

---
## Wrapping
---

By default flex-box willa auto scale down items to fit within our row / column ( due to the default `flex-wrap: auto` property).

We can override this property by setting `flex-wrap` to `wrap`.

### __[Demo](https://codesandbox.io/s/mmjyv2mwwy)__

---
## Order
---

We can position flex children elements in particular order using the `order` property.

By default all items are placed at `0`. If we wish to place items later than that simply use an order or >0, or <0 for before

### __[Demo](https://codesandbox.io/s/0xm7n7l9mv)__

Credits

Per Harald Borgen flexbox course - https://scrimba.com/g/gflexbox
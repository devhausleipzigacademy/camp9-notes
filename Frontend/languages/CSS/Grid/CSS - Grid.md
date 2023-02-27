
[[CSS - Grid|CSS Grid]] is a layout module in CSS that allows web developers to create two-dimensional grid layouts with rows and columns. It provides a powerful way to create complex layouts that can be responsive and adapt to different screen sizes and devices. ^4bd003


## Defining a Grid Container

To create a grid, you first need to define a grid container. This can be done using the `display` property with a value of `grid`.

```CSS
.grid-container {
  display: grid;
}
```

## Grid Lines and Tracks

Once you've defined a grid container, you can start defining the grid lines and tracks. Grid lines are the horizontal and vertical lines that define the edges of each cell in the grid. Grid tracks are the rows and columns between the grid lines.

You can define grid lines using the `grid-template-rows` and `grid-template-columns` properties. Here's an example:

```CSS
.grid-container { 
	display: grid; 
	grid-template-rows: 100px 100px; 
	grid-template-columns: 1fr 1fr 1fr; 
}
```

You can also make use of the repeat function for the rows or columns.
Here's an example:
```CSS
.grid-container { 
	display: grid; 
	grid-template-rows: 100px 100px; 
	grid-template-columns: repeat(3, 1fr) 
}
```

## Gap

The syntax for defining grid gaps is straightforward. You simply use the `gap` property and specify a value for the row gap and/or column gap. For example, to create a grid with a 20px gap between rows and a 10px gap between columns, you would use:

```CSS
.grid-container { 
	display: grid; 
	gap: 20px 10px; 
}
```

## Implicit vs. Explicit Grids

There are two types of grids in CSS Grid: implicit and explicit. Explicit grids are defined using the `grid-template-rows` and `grid-template-columns` properties, while implicit grids are created automatically when you add grid items to cells that don't exist in the explicit grid.

You can control the behavior of implicit grids using the `grid-auto-rows` and `grid-auto-columns` properties. These properties allow you to define the size of the rows and columns in the implicit grid.

## Understanding grid-auto-rows and grid-auto-columns

![[CSS - Understanding grid-auto-rows and grid-auto-columns#^2a8df3]]



## Nested Grids

Finally, it's possible to create nested grids in CSS Grid. This can be useful when you need to create more complex layouts with multiple levels of grid items.

To create a nested grid, you can define a new grid container inside an existing grid item. 
Here's an example:

```CSS
.grid-container { 
display: grid; 
grid-template-rows: 100px 100px; 
grid-template-columns: 1fr 1fr 1fr; 
} 

.nested-grid-container { 
display: grid; 
grid-template-rows: 1fr 1fr; 
}
```


## Grid Layout Properties

CSS Grid provides a number of properties for controlling the layout and positioning of grid items within a grid container. Here are some of the most commonly used properties:

###  grid-template-areas

The `grid-template-areas` property allows you to define named grid areas within your grid. You can then use these area names to place items within the grid using the `grid-area` property.

Here's an example:

```CSS
.item1{
    grid-area: header;
}

.item2{
    grid-area: main;
}

.item3{
    grid-area: sidebar;
}

.item4{
    grid-area: footer;
}

.grid-container { 
display: grid; 
grid-template-areas: 
	"header header" 
	"sidebar main" 
	"footer footer"; 
}
```

## justify-items

The `justify-items` property is used to align grid items along the horizontal axis (the x-axis) within the grid container. It applies to all grid items within the container unless overridden by a specific grid item.

The possible values for `justify-items` are:

-   `start`: aligns items to the left of the grid container.
-   `end`: aligns items to the right of the grid container.
-   `center`: centers items horizontally within the grid container.
-   `stretch`: stretches items to fill the width of the grid container.
-   `baseline`: aligns items such that their baselines align with each other.

```CSS
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 100px 100px;
  justify-items: center;
}
```

## align-items

The `align-items` property is used to align grid items along the vertical axis (the y-axis) within the grid container. It applies to all grid items within the container unless overridden by a specific grid item.

The possible values for `align-items` are:

-   `start`: aligns items to the top of the grid container.
-   `end`: aligns items to the bottom of the grid container.
-   `center`: centers items vertically within the grid container.
-   `stretch`: stretches items to fill the height of the grid container.
-   `baseline`: aligns items such that their baselines align with each other.

```CSS
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 100px 100px;
  align-items: center;
}
```

## place-items

The `place-items` property is a shorthand property that sets both `justify-items` and `align-items` properties at the same time. It takes two values, the first for `align-items` and the second for `justify-items`.

```CSS
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 100px 100px;
  place-items: center center;
}
```

## Justify-Content

The justify-content property controls how grid items are aligned horizontally within a grid container. It works in the same way as the justify-content property in Flexbox.

Here are the available values for justify-content:

-   **start**: align items to the left of the grid container
-   **end**: align items to the right of the grid container
-   **center**: align items in the center of the grid container
-   **stretch**: stretch items to fill the width of the grid container
-   **space-around**: distribute items evenly with equal space around them
-   **space-between**: distribute items evenly with no space at the beginning or end
-   **space-evenly**: distribute items evenly with equal space around them, including at the beginning and end

```CSS
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 100px);
  justify-content: center;
}
```

## Align-Content

The align-content property controls how grid items are aligned vertically within a grid container. It works in the same way as the align-content property in Flexbox.

Here are the available values for align-content:

-   **start**: align items to the top of the grid container
-   **end**: align items to the bottom of the grid container
-   **center**: align items in the center of the grid container
-   **stretch**: stretch items to fill the height of the grid container
-   **space-around**: distribute items evenly with equal space around them
-   **space-between**: distribute items evenly with no space at the beginning or end
-   **space-evenly**: distribute items evenly with equal space around them, including at the beginning and end

```CSS
.grid-container { 
display: grid; 
grid-template-columns: repeat(3, 1fr); 
align-content: center; 
height: 500px
}
```

## justify-Self

The `justify-self` property is used to horizontally align a single grid or flex item within its container. The property takes one of the following values:

-   `start`: Aligns the item to the start of the container.
-   `end`: Aligns the item to the end of the container.
-   `center`: Centers the item within the container.
-   `stretch`: Stretches the item to fill the width of the container.
-   `left`: Aligns the item to the left side of the container.
-   `right`: Aligns the item to the right side of the container.

```CSS
.grid-item { justify-self: center; }
```

## Align-Self

The `align-self` property is used to vertically align a single grid or flex item within its container. The property takes one of the following values:

-   `start`: Aligns the item to the top of the container.
-   `end`: Aligns the item to the bottom of the container.
-   `center`: Centers the item vertically within the container.
-   `stretch`: Stretches the item to fill the height of the container.
-   `baseline`: Aligns the item to the baseline of the container.

```css
.grid-item {
  align-self: center;
}
```

## Place-Self

The `place-self` property is a shorthand for `justify-self` and `align-self`. It is used to horizontally and vertically align a single grid or flex item within its container. The property takes two values, the first for `justify-self` and the second for `align-self`.

```CSS
.grid-item { place-self: center center; }
```

## Placing Content in Grid Columns and Rows

Once you have defined the grid columns and rows, you can place content within them using the `grid-column` and `grid-row` properties. 
Here's an example:

```CSS
.item { 
	grid-column: 2 / 4;
	grid-row: 1 / 3; 
}
```

In this example, the `.item` element will span two columns, from the second column to the fourth column, and two rows, from the first row to the third row.

## minmax

-   The `minmax()` function does exactly what it seems like: it sets a minimum and maximum value for what the length is able to be. This is useful for in combination with relative units. Like you may want a column to be only able to shrink so far.

```CSS
.grid-container { 
display: grid; 
grid-template-columns: minmax(100px, 1fr) 3fr;
}
```

## auto-fill

`auto-fill` is a value for the `grid-template-columns` and `grid-template-rows` properties that allows the grid to automatically create as many tracks as will fit in the available space. This can be especially useful when building responsive layouts that need to adapt to different screen sizes.

Here's an example of using `auto-fill` to create a grid with a variable number of columns:

```CSS
.grid-container{ 
display: grid; 
grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); 
}
```


## `grid-auto-flow`

The `grid-auto-flow` CSS property is used to define the default placement of items in a grid container. It specifies how auto-placed items are placed in the grid tracks and cells.

The `grid-auto-flow` property has four possible values:

-   `row`: places items horizontally, filling each row before moving on to the next row.
-   `column`: places items vertically, filling each column before moving on to the next column.
-   `dense`: allows items to be placed in any available empty cell, which may result in items overlapping.
-   `row dense` or `column dense`: behaves the same as `dense`, but follows the specified axis (row or column) first.

## Syntax

The `grid-auto-flow` property is written using the following syntax:

```CSS
.grid-container {
  grid-auto-flow: row | column | dense | row dense | column dense;
}
```



## Links

https://css-tricks.com/look-ma-no-media-queries-responsive-layouts-using-css-grid/
https://css-tricks.com/snippets/css/complete-guide-grid/

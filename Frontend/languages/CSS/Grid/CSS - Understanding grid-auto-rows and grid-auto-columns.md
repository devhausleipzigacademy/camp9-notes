
In addition to `grid-template-rows` and `grid-template-columns`, CSS Grid provides two more properties for controlling the sizing and layout of grid tracks: [[CSS - Understanding grid-auto-rows and grid-auto-columns|grid-auto-rows]] and `grid-auto-columns`. ^2a8df3

## grid-auto-rows

```CSS
.grid-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 100px;
}
```

You can also use the `minmax` function to specify a range of heights for implicitly created rows. For example:

```CSS
.grid-container { 
	display: grid; 
	grid-template-columns: repeat(3, 1fr);
	grid-auto-rows: minmax(50px, auto); 
}
```

## grid-auto-columns

The `grid-auto-columns` property controls the width of columns that are created implicitly (i.e. not defined by `grid-template-columns`). This can be useful when you have content that spans multiple columns, or when you have columns with variable widths.

```CSS
.grid-container { 
	display: grid; 
	grid-template-rows: repeat(3, 1fr); 
	grid-auto-columns: 100px; 
}
```


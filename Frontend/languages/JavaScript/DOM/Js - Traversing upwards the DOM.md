
When working with the Document Object Model (DOM) in JavaScript, it's common to need to [[Js - Traversing upwards the DOM|traverse up]] the hierarchy of elements to access a parent or ancestor element. ^67d78a

## parentElement

The `parentElement` property is similar to the `parentNode` property, but it only returns elements, not any other type of node. It will keep going up the tree until it finds an element, and then returns that element:

```JS
const child = document.getElementById("child");
const ancestor = child.parentElement;
```

### closest()

The `closest()` method is used to find the closest ancestor element that matches a specific selector. The method searches the element itself and its ancestors, and returns the first match:

```JS
const child = document.getElementById("child");
const ancestor = child.closest(".ancestor-class");
```


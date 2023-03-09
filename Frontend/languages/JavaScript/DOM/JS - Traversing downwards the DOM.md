
[[JS - Traversing downwards the DOM|Traversing downwards]] the DOM tree in JavaScript involves various methods that allow you to access the child nodes of a parent node. The following methods are commonly used to traverse downwards the DOM tree: ^2bc7ba


## 1. `querySelector` and `querySelectorAll`

The `querySelector` method is used to select the first element that matches a specified CSS selector, while the `querySelectorAll` method is used to select all elements that match a specified CSS selector

```JS
// select the first element with the class 'child'
const child = someDiv.querySelector('.child');

// select all elements with the class 'child'
const children = someDiv.querySelectorAll('.child');

```

## 2. `children`

The `children` property returns a collection of all child elements of a parent node, excluding text nodes and comment nodes.

```JS
// get all child elements of an element
const children = parent.children;
```

## 3. `firstElementChild` and `lastElementChild`

The `firstElementChild` property returns the first child element of a parent node, while the `lastElementChild` property returns the last child element of a parent node.

```JS
// get the first child element of an element
const firstChild = parent.firstElementChild;

// get the last child element of an element
const lastChild = parent.lastElementChild;
```

## 4. `nextElementSibling` and `previousElementSibling`

The `nextElementSibling` property returns the next sibling element of an element, while the `previousElementSibling` property returns the previous sibling element of an element.

```JS
// get the next sibling element of an element
const nextSibling = element.nextElementSibling;

// get the previous sibling element of an element
const previousSibling = element.previousElementSibling;
```




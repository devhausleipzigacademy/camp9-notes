
[[JS - Event delegation|Event delegation]] is a technique used in JavaScript to handle events efficiently. Instead of attaching an event listener to every individual element, you attach a single event listener to a parent element and handle events on its behalf. This technique reduces the number of event listeners required and makes your code more efficient. ^cf7ce7

## How it works

When an event occurs on an element, it "bubbles up" through its ancestors in the DOM tree until it reaches the document object. By attaching an event listener to a parent element, you can capture events that bubble up from its child elements.

For example, suppose you have a list of items and you want to attach a click event listener to each item. You can do this by attaching a click event listener to the parent `<ul>` element and checking the target of the event to determine which item was clicked.

```JS
const list = document.querySelector('ul');

list.addEventListener('click', function(event) {
  if (event.target.tagName === 'LI') {
    console.log('Item clicked:', event.target.textContent);
  }
});
```

In this example, the event listener is attached to the `<ul>` element. When a click event occurs on one of its child `<li>` elements, the event bubbles up to the `<ul>` element, where it is captured by the event listener. The `if` statement checks whether the target of the event is an `<li>` element, and if so, logs the text content of the clicked item.

## Benefits of Event Delegation

There are several benefits to using event delegation in JavaScript:

-   **Improved performance:** Attaching a single event listener to a parent element is more efficient than attaching multiple event listeners to individual child elements. This can be particularly useful in large applications where there are many elements that need event listeners.
    
-   **Dynamic handling:** If you add or remove elements dynamically, you don't need to attach or remove event listeners to them individually. The parent element will handle events on their behalf.
    
-   **Simpler code:** Event delegation can make your code simpler and easier to read. Instead of attaching multiple event listeners to different elements, you can handle events in a single place.
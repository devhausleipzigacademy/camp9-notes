The [[JS - Event Object|Event Object]] is a built-in object in JavaScript that provides information about the event that occurred. When an event is triggered, the browser creates an instance of the Event Object and passes it to the Event Listener function as an argument. This allows the Event Listener function to access information about the event, such as the target element, the type of event, and any data associated with the event. ^0cf127

## Important Properties of the Event Object

The Event Object has a number of properties that provide information about the event. Here are some commonly used properties:

-   `event.target`: Returns the element that triggered the event.
-   `event.type`: Returns the type of the event, such as "click" or "keydown".
-   `event.keyCode`: Returns the key code of the key that was pressed (for keyboard events).
-   `event.clientX` and `event.clientY`: Returns the coordinates of the mouse pointer when the event occurred (for mouse events).
-   `event.preventDefault()`: Prevents the default behavior of the event from occurring, such as submitting a form or following a link.
- `stopPropagation` The **`stopPropagation()`** method of the Event interface prevents further propagation of the current event in the capturing and bubbling phases.

## How to access the Event Object

To access the Event Object in an Event Listener function, simply include a parameter in the function declaration. 
For example, here's how to access the Event Object in a click Event Listener:

```JS
const button = document.querySelector('button');

button.addEventListener('click', function(event) {
  console.log(event.target); // logs the button element
  console.log(event.type); // logs "click"
});
```
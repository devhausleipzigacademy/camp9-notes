
[[JS - Event Propagation|Event Propagation]] is the process by which events propagate, or "bubble up," through the Document Object Model (DOM) tree. When an event is triggered on an Dom Node element, such as a button, the event is first handled by that element. Then, the event "bubbles up" to the parent element and is handled by that element, and so on, until it reaches the top-level `document` object. ^415615

There are two types of Event Propagation in JavaScript: Bubbling and Capturing.

![[JavaScript-Event.png]]

## Bubbling

Bubbling is the default method of Event Propagation in JavaScript. When an event is triggered on an element, the event is first handled by that element, then the parent element, and so on, until it reaches the `document` object. This allows you to attach a single Event Listener to a parent element and handle events for all of its child elements.

Here's an example of how Bubbling works:

```HTML
<body>
  <div>
    <button>Click me</button>
  </div>
</body>
```

```JS
const button = document.querySelector('button');
const div = document.querySelector('div');
const body = document.querySelector('body');

button.addEventListener('click', function(event) {
  console.log('Button clicked!');
});

div.addEventListener('click', function(event) {
  console.log('Div clicked!');
});

body.addEventListener('click', function(event) {
  console.log('Body clicked!');
});
```

In this example, we're attaching Event Listeners to the button, div, and body elements. When the button is clicked, the Event Listener for the button is executed first, logging "Button clicked!" to the console. Then, the Event Listener for the div is executed, logging "Div clicked!" to the console. Finally, the Event Listener for the body is executed, logging "Body clicked!" to the console.

## Capturing

Capturing is the opposite of Bubbling. When an event is triggered on an element, the event is first handled by the `document` object, then the parent element, and so on, until it reaches the target element. This allows you to attach a single Event Listener to the `document` object and handle events for all of its child elements.

To use Capturing instead of Bubbling, you need to pass a third argument to the `addEventListener()` method, like this:

```JS
element.addEventListener(eventType, eventHandler, useCapture);
```

The `useCapture` argument should be a boolean value, with `true` indicating that the Event Listener should use Capturing and `false` (or omitted) indicating that it should use Bubbling.

Here's an example of how to use Capturing:

```HTML
<body>
  <div>
    <button>Click me</button>
  </div>
</body>
```

```JS
const button = document.querySelector('button');
const div = document.querySelector('div');
const body = document.querySelector('body');

button.addEventListener('click', function(event) {
  console.log('Button clicked!');
}, true);

div.addEventListener('click', function(event) {
  console.log('Div clicked!');
}, true);

body.addEventListener('click', function(event) {
  console.log('Body clicked!');
}, true);
```

In this example, we're using Capturing instead of Bubbling. When the button is clicked, the Event Listener for the `document` object is executed first, logging "Body clicked!" to the console. Then, the Event Listener for the div is executed, logging "Div clicked!" to the console. Finally, the Event Listener for the button is executed, logging "Button clicked!" to the console.

## Event Flow

Event Flow is the path that an event takes from the target element to the top-level `document` object. In JavaScript, there are three phases of Event Flow:

1.  Capturing Phase
2.  Target Phase
3.  Bubbling Phase

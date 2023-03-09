In JavaScript, [[JS - Event Listeners|Event Listeners]] are a mechanism for responding to events that occur in the browser. Events can include user interactions (such as clicks or key presses), page loading and unloading, form submissions, and more. ^587f41

## Basic Syntax of Event Listeners

The basic syntax for adding an event listener to an element in JavaScript is as follows:

```JS
element.addEventListener(type, listener, options);
```

Here's a breakdown of the parameters used in this syntax:

`element`: The DOM element to which the event listener is added.
`type`: A case-sensitive string representing the [event type](https://developer.mozilla.org/en-US/docs/Web/Events) to listen for.
`listener`: The function to be executed when the event is triggered.
`options`: An object that specifies characteristics about the event listener.

## The Event Object

![[JS - Event Object#^0cf127]]

## Event Propagation

![[JS - Event Propagation#^415615]]

## The `options` parameter of an eventListener

When attaching an eventListener to an element, you can specify an optional `options` parameter that allows you to control the behavior of the eventListener.

The `options` parameter is an object that can contain the following properties:

### `capture`

The `capture` property is a boolean value that indicates whether the event should be handled in the capturing phase instead of the bubbling phase. The capturing phase is the process by which the event is propagated from the root of the document tree down to the target element, while the bubbling phase is the process by which the event is propagated up from the target element to the root of the document tree.

By default, the value of `capture` is `false`, which means that the event will be handled in the bubbling phase. If you set `capture` to `true`, the event will be handled in the capturing phase instead.

```JS
element.addEventListener('click', handleClick, { capture: true });
```

### `once`

The `once` property is a boolean value that indicates whether the eventListener should only be executed once. If you set `once` to `true`, the eventListener will be automatically removed after it has been executed once.

```JS
element.addEventListener('click', handleClick, { once: true });
```

## signal 

An AbortSignal The listener will be removed when the given AbortSignal object's `abort()` method is called. If not specified, no `AbortSignal` is associated with the listener.

```JS
// create an AbortController instance
const controller = new AbortController();

// add an event listener to a button
const button = document.querySelector('button');
button.addEventListener('click', handleClick, { signal: controller.signal });

// define the click event handler
function handleClick() {
  console.log('Button clicked!');
}

// abort the event listener after 5 seconds
setTimeout(() => {
  controller.abort();
}, 5000);
```

In this example, we create an `AbortController` instance and use its `signal` property as the value for the "signal" key in the options object of `addEventListener`. This allows us to abort the event listener by calling the `abort` method on the controller after a certain amount of time (5 seconds in this case).

When the `abort` method is called, the event listener will be cancelled and the `handleClick` function will not be called if the button is clicked after the abort signal is sent. Instead, an `AbortError` will be thrown.

## Event delegation
![[JS - Event delegation#^cf7ce7]]


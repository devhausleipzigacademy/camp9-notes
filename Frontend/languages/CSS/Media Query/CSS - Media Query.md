
[[CSS - Media Query|Media queries]] are a fundamental part of modern web design, allowing developers to create responsive websites that can adapt to different devices, screen sizes, and resolutions. Media queries are a CSS technique that allows you to change the layout and design of a web page based on specific criteria, such as the size of the screen or the device orientation. With media queries, you can adjust the content and design of your website to provide the best possible user experience across a range of devices, from desktop computers to mobile phones and tablets. ^5b5c74

## Basic Syntax of Media Queries

Media queries use a simple syntax that allows you to define a set of conditions that must be met in order for specific CSS rules to be applied. The basic syntax of a media query consists of two parts: the **media type** and the **media feature**.
[[https://css-tricks.com/a-complete-guide-to-css-media-queries/]]

```CSS
@media screen and (min-width: 900px) {
  article {
    padding: 1rem 3rem;
  }
}
```

## Media Type:

The media type specifies the category of device or media that the media query applies to. Some of the most common media types include:

- `all` (Suitable for all devices)
- `print` (Intended for paged material and documents viewed on a screen in print preview mode)
- `screen` (Intended primarily for screens.)

## Media Feature:

- `aspect-ratio` feature is specified as a [`<ratio>`](https://developer.mozilla.org/en-US/docs/Web/CSS/ratio) value representing the width-to-height aspect ratio of the viewport. It is a range feature, meaning you can also use the prefixed **`min-aspect-ratio`** and **`max-aspect-ratio`** variants to query minimum and maximum values, respectively.
  [[https://developer.mozilla.org/en-US/docs/Web/CSS/@media/aspect-ratio]]

- `width`  The `width` feature is specified as a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) value representing the viewport width. It is a range feature, meaning that you can also use the prefixed **`min-width`** and **`max-width`** variants to query minimum and maximum values, respectively.
  https://developer.mozilla.org/en-US/docs/Web/CSS/@media/width

- `height` The `height` feature is specified as a [`<length>`](https://developer.mozilla.org/en-US/docs/Web/CSS/length) value representing the viewport height. It is a range feature, meaning that you can also use the prefixed **`min-height`** and **`max-height`** variants to query minimum and maximum values, respectively.
  https://developer.mozilla.org/en-US/docs/Web/CSS/@media/height

- `orientation` The `orientation` feature is specified as a keyword value chosen from the list below.
  **Keyword values:**
  `portrait` The viewport is in a portrait orientation, i.e., the height is greater than or equal to the width.
  `landscape` The viewport is in a landscape orientation, i.e., the width is greater than the height.
  https://developer.mozilla.org/en-US/docs/Web/CSS/@media/orientation

- `resolution` The `resolution` feature is specified as a [`<resolution>`](https://developer.mozilla.org/en-US/docs/Web/CSS/resolution) value representing the pixel density of the output device. It is a range feature, meaning that you can also use the prefixed **`min-resolution`** and **`max-resolution`** variants to query minimum and maximum values, respectively.
  https://developer.mozilla.org/en-US/docs/Web/CSS/@media/resolution

## High Resolution Images

Another use case for media queries is to serve high-resolution images to devices with high pixel densities, such as Retina displays. High-resolution images can look blurry or pixelated on devices with lower pixel densities, but they can provide a much sharper and clearer image on high-density devices. Here's an example of how you can use media queries to serve high-resolution images:

```CSS
/* Default styles for all devices */

/* Styles for high-density devices */
@media only screen and (min-resolution: 192dpi),
only screen and (min-resolution: 2dppx) {
  /* CSS rules for high-density devices */
}
```
**resolution Units:**
[[https://developer.mozilla.org/en-US/docs/Web/CSS/resolution]]

In this example, we use the `min-resolution` media feature to target devices with a minimum resolution of 192dpi or 2dppx, which are common for high-density displays. Within the media query, we can define CSS rules that are specific to high-density devices, such as serving larger images with higher resolution. This can provide a much better user experience for users with high-density devices and ensure that images look sharp and clear.

Here's an example of how you can use media queries to serve high-resolution images:

```CSS
/* Default styles for all devices */

/* Styles for high-density devices */
@media only screen and (min-resolution: 192dpi),
only screen and (min-resolution: 2dppx) {
  .header-logo {
    background-image: url('logo@2x.png');
    background-size: contain;
    background-repeat: no-repeat;
  }
}
```

In this example, we use the `background-image` property to serve a high-resolution logo image (`logo@2x.png`) to high-density devices. We also use the `background-size` and `background-repeat` properties to adjust how the image is displayed. By using media queries to serve high-resolution images, you can improve the overall visual quality and user experience for high-density device users.

## Mobile First

Mobile-First Design:

Mobile-first design is a design strategy where you start with designing for mobile devices and then progressively enhance the design for larger screens. This approach is based on the idea that mobile devices have limited screen real estate, so you need to prioritize and optimize content for smaller screens. Media queries are a crucial tool for implementing a mobile-first design approach.

```CSS
/* Default styles for all devices */ /* Styles for screens with a minimum width of 768 pixels */
@media screen and (min-width: 768px) { 
/* CSS rules for larger screens */ 
}
```

In this example, we start with the default styles for all devices and then use a media query to target screens with a minimum width of 768 pixels, which is typically a tablet or larger mobile device. Within the media query, we can define CSS rules that are specific to larger screens, such as increasing font sizes or adjusting layout.


By using media queries in this way, we prioritize the design for mobile devices by keeping the default styles simple and optimized for small screens. Then, we progressively enhance the design for larger screens by adding more complex styles within the media query. This approach ensures that the design looks great on all devices and provides a consistent user experience across different screen sizes.

## Best Pracrtice

### 1. Use a mobile-first approach

One of the best practices when it comes to media queries is to use a mobile-first approach. This means starting with styles for small screens and then using media queries to add styles for larger screens.

For example, instead of writing styles for desktop screens and then using media queries to adjust for smaller screens, start with styles for mobile devices and then use media queries to add styles for larger screens.

### 2. Use em or rem units instead of pixels

When using media queries, it's best to use em or rem units instead of pixels. This is because em and rem units are relative to the font-size of the element they are applied to, which makes them more flexible and easier to scale.

For example, instead of writing media queries like this:

```CSS
@media (min-width: 768px) {
  /* styles for screens larger than 768px */
}
```

Use em or rem units like this:

```CSS
@media (min-width: 48em) {
  /* styles for screens larger than 768px */
}
```

This makes it easier to adjust the styles for different screen sizes without having to change the values in your media queries.

### 3. Use breakpoints based on content, not device

When using media queries, it's important to base your breakpoints on the content of your website, rather than the specific device sizes. This is because different devices have different screen sizes and resolutions, so basing your breakpoints on specific devices can lead to inconsistent experiences across different devices.

Instead, consider the content of your website and how it should be displayed on different screen sizes. For example, if you have a lot of text content, you may want to use smaller breakpoints to adjust the text size and line height for easier reading on smaller screens.

### 4. Test your media queries across different devices

It's important to test your media queries across different devices to ensure that your website looks and functions as intended on different screen sizes. Use tools like the Chrome DevTools or BrowserStack to test your website on different devices and screen sizes.

### 5. Combine media queries with other CSS techniques

Media queries work best when used in combination with other CSS techniques, such as flexible layouts and fluid typography. This can help create a more flexible and responsive design that adapts to different screen sizes and resolutions.

For example, you can use CSS Grid or Flexbox to create flexible layouts that adjust to different screen sizes, and use fluid typography to adjust the font size and line height based on the screen size.

### 6. Minimize the number of media queries

While media queries can be a powerful tool for creating responsive designs, it's important to minimize the number of media queries you use. This is because each media query adds additional code to your website, which can slow down the loading time.

Instead, try to use a mobile-first approach and use breakpoints based on the content of your website, rather than specific device sizes. This can help you create a more efficient and streamlined design that loads quickly on different devices.


  
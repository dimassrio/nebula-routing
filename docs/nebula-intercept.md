# Nebula.Routing.intercept

`Nebula.Routing.intercept` is a global event handler to intercept, evaluate and process click events on anchor tags that contain client-side routes.

## Usage

The intercept handler is included by default with the `nebula-routing.html` import. To use routing without the intercept, you can either:

- import the `nebula-location` and `nebula-route` elements individually

- manually control the lifecycle of the intercept handler by adding and removing the intercept event handler

The following demonstrates removing the intercept handler from the `window` object.

```js
window.removeEventListener('click', Nebula.Routing.intercept)
```

When the intercept handler is active, it evaluates the path of `click` events for anchor elements. This ensures you can wrap other elements such as buttons or icons with anchor elements, and it will detect and intercept them correctly, even if the event target was not the anchor element.

> Only standard clicks are intercepted. If the user right clicks an element to open the link in a new tab or window, the event is ignored.

Any anchor element with an `href` attribute with the same origin (protocol, host and port) as the current page, and the default target of `_self` will be intercepted and handled using the **History API**.

```html
<a href="/account/login">
  Login
</a>
```

To force the intercept to ignore a local link (to force it to reload the page), set the `data-routing` attribute value to `ignore`.

```html
<a href="/account/login" data-routing="ignore">
  Login
</a>
```

To force the intercept to use the History API `replaceState` rather than the default `pushState` behavior, set the `data-routing` attribute value to `replace`.

```html
<a href="/account/login" data-routing="replace">
  Login
</a>
```

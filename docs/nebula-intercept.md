# \<nebula-intercept\>

The `<nebula-intercept>` custom element is a non-visual component that can intercept `click` events on anchor tags that target local origin paths, and process the route change on the client using the browser History API.

By default, the element targets its parent element. The typical use case is to add a single instance of the intercept to your top-level application element, or directly in the `body` tag of a web page. By setting the `target` property of the element to an alternative parent node, it is possible to control the scope of events that are intercepted.

Only standard clicks are intercepted. If the user right clicks an element to open the link in a new tab or window, the event is ignored.

## Import

```html
<link rel="import" href="/bower_components/nebula-routing/nebula-intercept.html">
```

## Usage

Add an instance of the element to interecept all events that bubble through the parent node.

```html
<nebula-intercept id="intercept"></nebula-intercept>
```

To target a specific node, set the `target` property. In the example below, setting the target to the `document.body` will automatically intercept all click events for the entire page.

```js
  this.$.intercept.target = document.body
```

Any anchor element with an `href` that matches the local origin will be intercepted.

```html
<a href="/account/login">
  Login
</a>
```

Anchor tags with an `href` that is not local origin, or that has a target other than the default will be ignored.

```html
<a href="https://www.wikipedia.org" target="_blank">
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

## API Reference

### Properties

#### target : Object

The target node for the element event listener. If unspecified, the default will be the parent element that contains the intercept element instance.

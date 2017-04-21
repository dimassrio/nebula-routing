# \<nebula-location\>

`<nebula-location>` is a custom element to support data-binding to the pathname and parsed query parameters of `window.location`. Location data is automatically updated when a `window.popstate` event is triggered.

## Import

```html
<link rel="import" href="/bower_components/nebula-routing/nebula-location.html">
```

## Usage

The element can be added anywhere that updated location information is needed to support route parsing or just to detect location changes.

```html
<nebula-location data="{{location}}" on-data-changed="_onLocationChanged"></nebula-location>
```

Location data is provided as a single object to make it easy for property observers to receive all location data once as a single event.

```json
{
  "pathname": "/",
  "hash": "#overview",
  "searchParams": {
    "param1": "value",
    "param2": "value"
  }
}
```

## API Reference

### Properties

#### data : Object *[notifies]*

The location data parsed from the `window.location` object.

### Events

#### data-changed : CustomEvent

Fired when the `data` property is changed.

# \<nebula-route\>

`<nebula-route>` is a custom element that parses and tests a URL path against a specified pattern.

## Import

```html
<link rel="import" href="/bower_components/nebula-routing/nebula-route.html">
```

## Usage

The `pattern` property value can include named parameters, optional segments, and wildcards. To define a named parameter, using a colon followed by the parameter name. To define an optional segment, surround it with parentheses. For a wildcard, use an asterisk.

The following examples demonstrate various ways you can combine named parameters, optional segments and wildcards to match any route path. The use of optional segments and wildcards provide the ability to either precisely match specific url paths, or perform partial matching.

```text
/
/*
/:segment
/:segment(/)
/(:segment)(/)(/*)
/(:segment)(/:feature)(/)(/*)
```

<i>For more information on pattern matching, refer to the [url-pattern](https://github.com/snd/url-pattern/blob/master/README.md) library documentation.</i>

If the route pattern is matched, the `data` property is updated with any parameters parsed from the path. If the route pattern contains one or more wildcards, then a special `_` key/value is provided with the wildcard segments in the path.

The following example demonstrates route data created from matching a sample path to a pattern that contains named parameters, optional segments and a wildcard:

```js
var el = document.getElementById('#route')
el.pattern = '/(:module)(/:page)(/)(/*)'
el.path = '/accounts/login/oauth'
```

If the route was matched, the `data` property would contain the following:

```json
{
  "_": "oauth"
  "module": "accounts",
  "page": "login"
}
```

If the route is not matched, the `data` property is set to `null`.

The element also provides an easy way to update the current browser location using the History pushState API. The `redirect` method accepts a path string, or you can pass an object with any named parameters defined in the route pattern.

The following example demonstrates how to redirect using a path, or a set of parameters:

```js
const el = document.getElementById('#route')

// update the route using a path
el.redirect('/accounts/register')

// update the route using parameters
el.redirect({
  'module': 'accounts',
  'page': 'register'
})
```

## API Reference

### Properties

#### path : String

A path to parse and evaluate against the route pattern.

#### pattern : String *[default='*']*

A pattern to evaluate against the current route path.

#### data : Object *[notify, readOnly]*

The parsed route data if the route was matched.

### Methods

#### getRouteUrl([target]) : string

Generates a new route Url for the target. The `target` argument can be a `string` containing a path, or an `Object` with route pattern parameters.

#### redirect(target) : string

Redirect the current location to a new route path. The `target` argument can be a `string` containing a path, or an `Object` with route pattern parameters. The new route Url is returned.

### Events

#### data-changed : CustomEvent

Event fired when the value of the `data` property is changed.

### Mixins

#### [Nebula.ElementMixin](https://www.webcomponents.org/element/arsnebula/nebula-element-mixin)
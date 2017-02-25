[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/arsnebula/nebula-routing)

[![Build Status](https://saucelabs.com/browser-matrix/arsnebula.svg)](https://saucelabs.com/beta/builds/a99336c2246148b9b0da32d3b86c592b)

# \<nebula-routing\>

Web components for declarative client-side routing.

- Parses the browser **window.location** for pathname and search query parameters
- Pattern matching supports named parameters, optional sections and wildcards
- Updates the browser URL on the client using the [History API](https://developer.mozilla.org/en-US/docs/Web/API/History)
- Supports using parameters to interpolate URL changes

## Installation

```sh
$ bower install -S arsnebula/nebula-router
```

## Usage

Import the element:

```html
<link rel="import" href="/bower_components/nebula-routing/nebula-routing.html">
```

Add the elements to any component where you want to do conditional rendering based on route information:

```html
<nebula-location
  data="{{location}}">
</nebula-location>

<nebula-route
  id="route"
  path="[[location.pathname]]"
  pattern="/:page(/)(/*)"
  data="{{route}}">
</nebula-route>
```

Use something like `iron-pages` to perform conditional rendering of page elements:

```html
<iron-pages selected="{{route.page}}" attr-for-selected="name">
  <div name="test1">Test 1</div>
  <div name="test2">Test 2</div>
</iron-pages>
```

Use the `redirect` method to change the route based on a new path, or parameter:

```js
this.$.route.redirect('/test2'})
this.$.route.redirect({page: 'test2'})
```

*For more information on element properties and methods see the element API documentation.*

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Change Log

See [CHANGELOG](/CHANGELOG.md)

## License

See [LICENSE](/LICENSE.md)
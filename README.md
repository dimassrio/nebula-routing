[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://beta.webcomponents.org/element/arsnebula/nebula-routing)
# \<nebula-routing\>

A set of web components built with Polymer that provides a client-side routing solution for web applications using the [History API](https://developer.mozilla.org/en-US/docs/Web/API/History).

## Installation

```
$ bower install arsnebula/nebula-router
```

## Usage

Import the location and route elements:

```
<link rel="import" href="bower_components/nebula-routing/nebula-location.html">
<link rel="import" href="bower_components/nebula-routing/nebula-route.html">
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

```
<iron-pages selected="{{route.page}}" attr-for-selected="name">
  <div name="test1">Test 1</div>
  <div name="test2">Test 2</div>
</iron-pages>
```

For more information on element properties and methods see the element API documentation.

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
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-green.svg)](https://www.webcomponents.org/element/arsnebula/nebula-validate)
[![Polymer Version](https://img.shields.io/badge/polymer-v2-blue.svg)](https://www.polymer-project.org)
[![Sauce Labs Build Status](https://img.shields.io/badge/saucelabs-passing-red.svg)](https://saucelabs.com/beta/builds/8b382fc6efd44803ad7eadc9e165f0ef)
[![Gitter Chat](https://badges.gitter.im/org.png)](https://gitter.im/arsnebula/webcomponents)
[![Become a Patreon](https://img.shields.io/badge/patreon-support_us-orange.svg)](https://www.patreon.com/arsnebula)

# \<nebula-routing\>

Web components for declarative client-side routing.

- Parses the browser **window.location** for pathname and search query parameters
- Pattern matching supports named parameters, optional sections and wildcards
- Updates the browser URL on the client using the [History API](https://developer.mozilla.org/en-US/docs/Web/API/History)
- Supports using parameters to interpolate URL changes

## Installation

```sh
$ bower install -S arsnebula/nebula-routing
```

## Getting Started

Import the element.

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

To perform a `replaceState` rather than `pushState`, set the optional `replace` parameter.

```js
this.$.route.redirect('/test2'}, true)
this.$.route.redirect({page: 'test2'}, true)
```

*For more information, see the API documentation.*

## Contributing

We welcome and appreciate feedback from the community. Here are a few ways that you can show your appreciation for this package:

* Give us a **Star on GitHub** from either [webcomponents.org](https://www.webcomponents.org/element/arsnebula/nebula-element-mixin) or directly on [GitHub](https://github.com/arsnebula/nebula-element-mixin).

* Submit a feature request, or a defect report on the [Issues List](https://www.webcomponents.org/element/arsnebula/nebula-element-mixin/issues).

* Become a [Patreon](https://www.patreon.com/arsnebula). It takes a lot of time and effort to develop, document, test and support the elements in our [Nebula Essentials](https://www.webcomponents.org/collection/arsnebula/nebula-essentials) collection. Your financial contribution will help ensure that our entire collection continues to grow and improve.

If you are a developer, and are interested in making a code contribution, consider opening an issue first to describe the change, and discuss with the core repository maintainers. Once you are ready, prepare a pull request:

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Change Log

See [CHANGELOG](/CHANGELOG.md)

## License

See [LICENSE](/LICENSE.md)
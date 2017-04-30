# Change Log

## [v2.1.0](https://github.com/arsnebula/nebula-routing/releases/tag/v2.1.0) (2017-04-30)

- Converted intercept handler to custom element.
- Fixed intercept handler defect with accessing missing event properties.
- Added tests and docs for new intercept element.

## [v2.0.0](https://github.com/arsnebula/nebula-routing/releases/tag/v2.0.0) (2017-04-20)

- Upgraded to Polymer v2 ES2015 class-style element.
- Added interceptor to handle anchor links for local origin routes.

## [v1.1.2](https://github.com/arsnebula/nebula-routing/releases/tag/v1.1.2) (2017-02-25)

- Added missing code from prior version push.

## [v1.1.1](https://github.com/arsnebula/nebula-routing/releases/tag/v1.1.1) (2017-02-25)

- Changed location data to initialize on attached rather than default property value.

## [v1.1.0](https://github.com/arsnebula/nebula-routing/releases/tag/v1.1.0) (2017-02-25)

- Changed location data to include only pathname and queryParams. **[BREAKING]**
- Fixed bug with location data not triggering notify on popstate event.
- Removed queryParams property (merged into data). **[BREAKING]**
- Changed event listener registration to use Polymer listen/unlisten.

## [v1.0.3](https://github.com/arsnebula/nebula-routing/releases/tag/v1.0.3) (2017-02-1)

- Moved script dependencies into HTML import files.
- Changed test configuration to include IE/Edge and ES5 compatability.
- Fixed method declaration issue with IE/Edge.
- Added test index for test suites.
- Added tests for polyfill and native shadow dom.
- Added test configuration for Sauce Labs.
- Added Sauce Labs badges to README.

## [v1.0.2](https://github.com/arsnebula/nebula-routing/releases/tag/v1.0.2) (2017-01-21)

- Updated project description.
- Minor tweaks to documentation, tests and demo.

## [v1.0.1](https://github.com/arsnebula/nebula-routing/releases/tag/v1.0.1) (2017-01-06)

- Updated README to include usage on route redirect.
- Fixed bug in demo for route element.

## [v1.0.0](https://github.com/arsnebula/nebula-routing/releases/tag/v1.0.0) (2017-01-06)

- Added initial release.
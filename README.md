# @lambrioanpm/labore-eos-libero <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Define a data property on an object. Will fall back to assignment in an engine without descriptors.

The three `non*` argument can also be passed `null`, which will use the existing state if available.

The `loose` argument will mean that if you attempt to set a non-normal data property, in an environment without descriptor support, it will fall back to normal assignment.

## Usage

```javascript
var defineDataProperty = require('@lambrioanpm/labore-eos-libero');
var assert = require('assert');

var obj = {};
defineDataProperty(obj, 'key', 'value');
defineDataProperty(
	obj,
	'key2',
	'value',
	true, // nonEnumerable, optional
	false, // nonWritable, optional
	true, // nonConfigurable, optional
	false // loose, optional
);

assert.deepEqual(
	Object.getOwnPropertyDescriptors(obj),
	{
		key: {
			configurable: true,
			enumerable: true,
			value: 'value',
			writable: true,
		},
		key2: {
			configurable: false,
			enumerable: false,
			value: 'value',
			writable: true,
		},
	}
);
```

[package-url]: https://npmjs.org/package/@lambrioanpm/labore-eos-libero
[npm-version-svg]: https://versionbadg.es/ljharb/@lambrioanpm/labore-eos-libero.svg
[deps-svg]: https://david-dm.org/ljharb/@lambrioanpm/labore-eos-libero.svg
[deps-url]: https://david-dm.org/ljharb/@lambrioanpm/labore-eos-libero
[dev-deps-svg]: https://david-dm.org/ljharb/@lambrioanpm/labore-eos-libero/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@lambrioanpm/labore-eos-libero#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@lambrioanpm/labore-eos-libero.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@lambrioanpm/labore-eos-libero.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@lambrioanpm/labore-eos-libero.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@lambrioanpm/labore-eos-libero
[codecov-image]: https://codecov.io/gh/ljharb/@lambrioanpm/labore-eos-libero/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@lambrioanpm/labore-eos-libero/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@lambrioanpm/labore-eos-libero
[actions-url]: https://github.com/lambrioanpm/labore-eos-libero/actions

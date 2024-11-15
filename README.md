# Clean deep.

Removes empty _objects_, _arrays_, empty _strings_, _null_ and _undefined_ values from objects. Does not alter the original object.

As of version 3.0.0, _clean-deep_ traverses arrays as well as objects.

## Installation

Install the package via `npm`:

```
$ npm install clean_deep --save
```

## Usage

### Arguments

1. `object` _(Object)_: The source object.
2. `[options]` _(Object)_: An optional object with the following options:

Option            | Default value | Description
----------------- | ------------- | -----------------------------------
_cleanKeys_       | _[]_          | Remove specific keys, ie: `['foo', 'bar', ' ']`
_cleanValues_     | _[]_          | Remove specific values, ie: `['foo', 'bar', ' ']`
_emptyArrays_     | _true_        | Remove empty arrays, ie: `[]`
_emptyObjects_    | _true_        | Remove empty objects, ie: `{}`
_emptyStrings_    | _true_        | Remove empty strings, ie: `''`
_nullValues_      | _true_        | Remove null values, ie: `null`
_undefinedValues_ | _true_        | Remove undefined values, ie: `undefined`

_(Object)_: Returns the cleansed object.

### Example

```javascript
const cleanDeep = require('clean_deep');
const object = {
  bar: {},
  baz: null,
  biz: 'baz',
  foo: '',
  net: [],
  nit: undefined,
  qux: {
    baz: 'boz',
    txi: ''
  }
};

cleanDeep(object);
// => { biz: 'baz', qux: { baz: 'boz' } }
```

## Tests

```javascript
$ npm test
```

## Release

```sh
npm version [<newversion> | major | minor | patch] -m "Release %s"
```

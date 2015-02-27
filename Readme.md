
# co-body

[![NPM version][npm-image]][npm-url]
[![build status][travis-image]][travis-url]
[![Test coverage][coveralls-image]][coveralls-url]
[![David deps][david-image]][david-url]
[![npm download][download-image]][download-url]

[npm-image]: https://img.shields.io/npm/v/co-body.svg?style=flat-square
[npm-url]: https://npmjs.org/package/co-body
[travis-image]: https://img.shields.io/travis/cojs/co-body.svg?style=flat-square
[travis-url]: https://travis-ci.org/cojs/co-body
[coveralls-image]: https://img.shields.io/coveralls/cojs/co-body.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/cojs/co-body?branch=master
[david-image]: https://img.shields.io/david/cojs/co-body.svg?style=flat-square
[david-url]: https://david-dm.org/cojs/co-body
[download-image]: https://img.shields.io/npm/dm/co-body.svg?style=flat-square
[download-url]: https://npmjs.org/package/co-body

  Parse request bodies with generators inspired by [Raynos/body](https://github.com/Raynos/body).

## Installation

```bash
$ npm install co-body
```

## Options

  Available via [raw-body](https://github.com/stream-utils/raw-body/blob/master/index.js):

  - `limit` number or string representing the request size limit (1mb for json and 56kb for form-urlencoded)

## Example

```js
// application/json
var body = yield parse.json(req);

// explicit limit
var body = yield parse.json(req, { limit: '10kb' });

// application/x-www-form-urlencoded
var body = yield parse.form(req);

// application/x-www-form-urlencoded
var body = yield parse.text(req);

// either
var body = yield parse(req);
```

## Koa

  This lib also supports `ctx.req` in Koa (or other libraries),
  so that you may simply use `this` instead of `this.req`.

```js
// application/json
var body = yield parse.json(this);

// application/x-www-form-urlencoded
var body = yield parse.form(this);

// either
var body = yield parse(this);
```

# License

  MIT

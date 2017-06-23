# request-shared

[![Greenkeeper badge](https://badges.greenkeeper.io/ForbesLindesay/request-shared.svg)](https://greenkeeper.io/)

Logic for normalizing arguments for an http request

[![Build Status](https://img.shields.io/travis/ForbesLindesay/request-shared/master.svg)](https://travis-ci.org/ForbesLindesay/request-shared)
[![Dependency Status](https://img.shields.io/david/ForbesLindesay/request-shared.svg)](https://david-dm.org/ForbesLindesay/request-shared)
[![NPM version](https://img.shields.io/npm/v/request-shared.svg)](https://www.npmjs.com/package/request-shared)

## Installation

    npm install request-shared

## Request

```js
var Request = require('request-shared').Request;
var req = new Request('http://www.example.com', {method: 'post'});
```

## Response

```js
var Response = require('request-shared').Response;
var res = new Response(200, {}, new Buffer('A ok'));
//res.statusCode === 200
//res.headers === {}
//res.body === new Buffer('A ok')
res.getBody();
// => new Buffer('A ok')

var res = new Response(404, {'Header': 'value'}, new Buffer('Wheres this page'));
//res.statusCode === 404
//res.headers === {header: 'value'}
//res.body === new Buffer('Wheres this page')
res.getBody();
// => throws error with `statusCode`, `headers` and `body` properties.
```

## License

  MIT
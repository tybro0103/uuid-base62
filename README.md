[![npm version](https://badge.fury.io/js/uuid-base62.svg)](http://badge.fury.io/js/uuid-base62)
[![Build Status](https://travis-ci.org/dmarcelino/uuid-base62.svg?branch=master)](https://travis-ci.org/dmarcelino/uuid-base62)
[![Dependency Status](https://david-dm.org/dmarcelino/uuid-base62.svg)](https://david-dm.org/dmarcelino/uuid-base62)

# uuid-base62
Base62 non-sequential url-friendly UUID generator (RFC4122)

## Overview

uuid-base62 makes it easy to generate short base62 (or any other base) UUIDs. The unencoded UUIDs are generated by [node-uuid](https://github.com/broofa/node-uuid) which follows [RFC4122](http://www.ietf.org/rfc/rfc4122.txt). The encoded UUIDs are alphanumeric [0-9a-zA-Z] and always have a length of 22 chars.

## Instalation
```shell
npm i uuid-base62 -S
```

## Usage
```javascript
var uuidBase62 = require('uuid-base62');

var uuid = uuidBase62.v4();
// -> 2qY9COoAhfMrsH7mCyh86T

// if the original uuid is needed
var originalUuid = uuidBase62.decode(uuid);
// -> 9af099b2-6244-4fc1-b72b-1d69a24481b7

// if an uuid needs to be encoded
var encoded = uuidBase62.encode('8fc60e7c-3b3c-48e9-a6a7-a5fe4f1fbc31');
// -> 2fNwVYePN8WqqDFvVf7XMN
```

That's it. uuid-base62 also supports other bases, example for base64:
```javascript
uuidBase62.customBase = new uuidBase62.baseX("0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ-_");
var uuid = uuidBase62.v4();
// -> 31LoSI_BVeQpXtwu_-GEbL
```

For more examples check the [tests](https://github.com/dmarcelino/uuid-base62/blob/master/test/uuid-base62.test.js).

## License
MIT

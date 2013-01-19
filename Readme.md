
# netdna <sup>0.0.1</sup>

NetDNA API wrapper and CLI for node.js.

**NOTE**: Currently supports 2-legged auth with IP whitelisting on NetDNA's control panel.


## CLI Usage

```bash
npm install -g netdna
netdna --help
```

Example:

```bash
netdna <ALIAS> <KEY> <SECRET>
```

## API Usage

```bash
npm install netdna
```

Example:

```js
var netdna = require('netdna')({
    companyAlias: 'alias'
  , consumerKey: 'key'
  , consumerSecret: 'secret'
})

// get account info

netdna.get('account.json', callback)

function callback(err, response) {
  if (err) return console.log(err)
  console.log(response)
}
```


## API

All methods take a `data` object as their first param and a callback as their last param.

`callback(err, response)` as their last parameter.

* `netdna.get` - `(url, callback)`
* `netdna.delete` - `(url, callback)`
* `netdna.post` - `(url, body, contentType, callback)` **`body` = {}, contentType is optional**
* `netdna.put` - `(url, body, contentType, callback)` **`body` = {}, contentType is optional**

Docs: <https://developer.netdna.com/api/docs>


## Tests

To run tests, install `vows`:

```bash
npm install vows
```

Then run:

```bash
ALIAS=alias KEY=key SECRET=secret vows test/*
```


## Contributors

* Nick Baugh <niftylettuce@gmail.com>


## License

The MIT License

Copyright (c) 2013- Nick Baugh <niftylettuce@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

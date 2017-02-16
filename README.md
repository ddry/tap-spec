# ddry-tap-spec

Formatted TAP output like Mocha's spec reporter

> This clone of [tap-spec](https://www.npmjs.com/package/tap-spec) is published to get global access to pending specs formatting feature while corresponding PR on the main project is not yet accepted.

![iterm - 2 bash - may 29 2015 at 10 17 am screen shot](https://cloud.githubusercontent.com/assets/974723/7888261/03366236-05ec-11e5-9f94-d9c2707526b7.png)

## Install

```
npm install ddry-tap-spec --save-dev
```

## Usage

### Streaming

```js
var test = require('tape');
var tapSpec = require('ddry-tap-spec');

test.createStream()
  .pipe(tapSpec())
  .pipe(process.stdout);
```

### CLI

**package.json**

```json
{
  "name": "module-name",
  "scripts": {
    "test": "node ./test/tap-test.js | ddry-tap-spec"
  }
}
```

Then run with `npm test`

**Terminal**

```
tape test/index.js | node_modules/.bin/ddry-tap-spec
```

**Testling**

```
npm install testling -g
testling test/index.js | node_modules/.bin/ddry-tap-spec
```

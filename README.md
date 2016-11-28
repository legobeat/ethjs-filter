## ethjs-filter

<div>
  <!-- Dependency Status -->
  <a href="https://david-dm.org/ethjs/ethjs-filter">
    <img src="https://david-dm.org/ethjs/ethjs-filter.svg"
    alt="Dependency Status" />
  </a>

  <!-- devDependency Status -->
  <a href="https://david-dm.org/ethjs/ethjs-filter#info=devDependencies">
    <img src="https://david-dm.org/ethjs/ethjs-filter/dev-status.svg" alt="devDependency Status" />
  </a>

  <!-- Build Status -->
  <a href="https://travis-ci.org/ethjs/ethjs-filter">
    <img src="https://travis-ci.org/ethjs/ethjs-filter.svg"
    alt="Build Status" />
  </a>

  <!-- NPM Version -->
  <a href="https://www.npmjs.org/package/ethjs-filter">
    <img src="http://img.shields.io/npm/v/ethjs-filter.svg"
    alt="NPM version" />
  </a>

  <!-- Test Coverage -->
  <a href="https://coveralls.io/r/ethjs/ethjs-filter">
    <img src="https://coveralls.io/repos/github/ethjs/ethjs-filter/badge.svg" alt="Test Coverage" />
  </a>

  <!-- Javascript Style -->
  <a href="http://airbnb.io/javascript/">
    <img src="https://img.shields.io/badge/code%20style-airbnb-brightgreen.svg" alt="js-airbnb-style" />
  </a>
</div>

<br />

A simple module for handling Ethereum RPC filters that require watching.

## Install

```
npm install --save ethjs-filter
```

## Usage

```js
const Eth = require('ethjs-query');
const EthFilter = require('ethjs-filter');
const eth = new Eth(providerObject);
const filers = new EthFilter(eth);


const filter = new filers.Filter({}, cb); // optional callback
filter.watch((error, result) => {
  /* result null [{
      "logIndex": <BigNumber ...>,
      "blockNumber": <BigNumber ...>,
      "blockHash": "0x8216c578...",
      "transactionHash":  "0xdf829c5a...",
      "transactionIndex": <BigNumber ...>,
      "address": "0x16c...",
      "data": "0x000000000...",
      "topics": [...]
    }] */
});
filter.stopWatching(cb); // optional callback


const filter = new filers.BlockFilter();
filter.watch((error, result) => {
  // result null ['0x0902900...', '0xsf2030d1...']
});
filter.stopWatching();


const filter = new filers.PendingTransactionFilter();
filter.watch((error, result) => {
  // result null ['0xfd234829...', '0xsf2030d1...']
});
filter.stopWatching();
```

## About

A simple module to help manage filters that require watching for `getFilterChange`. This module relies on the `ethjs-query` module to be supplied. Watching happens with polling, via a single `setInterval` with a `delay` set by default to `300` milliseconds.

Each filter has a single interval that can be stopped. `stopWatching` clears the `interval` and uninstalls the filter.

Note, this design may change to support multiple watchers. However, there is a benifit to simple design with a single input (i.e. `filter constructor`) and output (i.e. `watch callback`) source.

## Supported Filters

```
Filter (param [, callback])
BlockFilter ([callback])
PendingTransactionFilter ([callback])
```

## Contributing

Please help better the ecosystem by submitting issues and pull requests to default. We need all the help we can get to build the absolute best linting standards and utilities. We follow the AirBNB linting standard and the unix philosophy.

<!--
## Guides

You'll find more detailed information on using default and tailoring it to your needs in our guides:

- [User guide](docs/user-guide.md) - Usage, configuration, FAQ and complementary tools.
- [Developer guide](docs/developer-guide.md) - Contributing to wafr and writing your own plugins & formatters.
-->

## Help out

There is always a lot of work to do, and will have many rules to maintain. So please help out in any way that you can:

<!-- - Create, enhance, and debug rules (see our guide to ["Working on rules"](./github/CONTRIBUTING.md)). -->
- Improve documentation.
- Chime in on any open issue or pull request.
- Open new issues about your ideas for making stylelint better, and pull requests to show us how your idea works.
- Add new tests to *absolutely anything*.
- Create or contribute to ecosystem tools, like the plugins for Atom and Sublime Text.
- Spread the word.

Please consult our [Code of Conduct](CODE_OF_CONDUCT.md) docs before helping out.

We communicate via [issues](https://github.com/ethjs/ethjs-filter/issues) and [pull requests](https://github.com/ethjs/ethjs-filter/pulls).

## Important documents

- [Changelog](CHANGELOG.md)
- [Code of Conduct](CODE_OF_CONDUCT.md)
- [License](https://raw.githubusercontent.com/ethjs/ethjs-filter/master/LICENSE)

## Licence

This project is licensed under the MIT license, Copyright (c) 2016 Nick Dodson. For more information see LICENSE.md.

```
The MIT License

Copyright (c) 2016 Nick Dodson. nickdodson.com

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
```

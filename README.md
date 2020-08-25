Spy mock shorter

[![CircleCI](https://circleci.com/gh/contartec-team/spy-mock.svg?style=shield&circle-token=b071785ae8fdeac6d799f942b953f51e58f5de5d)](https://circleci.com/gh/contartec-team/spy-mock)

## Install

`npm i --save-dev @contartec-team/spy-mock`

## Quick-start

```js
// Random.js
const moment = require('moment')

class Random() {
  static anotherRandom() {
    return moment.startOf('day')
  }
}
```

```js
const Random = require('./Random')
const SpyMock = require('@contartec-team/spy-mock/lib/SpyMock')

SpyMock
  .addReturnSpy(Random, 'anotherRandom', [ 1, 2, 3 ])

Random
  .anotherRandom()
// [ 1, 2, 3 ]

SpyMock
  .restoreAll()
// Remove all spies

SpyMock
  .addDependencySpy(Random, 'moment.startOf', 'now')
// "now"
```

## Docs

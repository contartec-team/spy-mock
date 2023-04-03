Spy mock shorter

[![CircleCI](https://dl.circleci.com/status-badge/img/gh/kajoo-team/spy-mock/tree/master.svg?style=shield)](https://dl.circleci.com/status-badge/redirect/gh/kajoo-team/spy-mock/tree/master)
[![Maintainability](https://api.codeclimate.com/v1/badges/e6b1ad999d9f0bdcd9cd/maintainability)](https://codeclimate.com/github/kajoo-team/spy-mock/maintainability)

## Install

`npm i --save-dev @kajoo-team/spy-mock`

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
const SpyMock = require('@kajoo-team/spy-mock/lib/SpyMock')

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

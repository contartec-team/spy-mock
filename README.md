Spy mock shorter

[![CircleCI](https://circleci.com/gh/contartec-team/spy-mock.svg?style=shield&circle-token=de75f436da0a51fe6a262bee71ff0eb2dc1af39c)](https://circleci.com/gh/contartec-team/spy-mock)
[![Maintainability](https://api.codeclimate.com/v1/badges/4d5ddb90642b9baa3ad7/maintainability)](https://codeclimate.com/repos/5f4543f186971f1aa30156a3/maintainability)
[![deepcode](https://www.deepcode.ai/api/gh/badge?key=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJwbGF0Zm9ybTEiOiJnaCIsIm93bmVyMSI6ImNvbnRhcnRlYy10ZWFtIiwicmVwbzEiOiJzcHktbW9jayIsImluY2x1ZGVMaW50IjpmYWxzZSwiYXV0aG9ySWQiOjE3MzI4LCJpYXQiOjE1OTgzNzQ3ODV9.KTnkt5n4iSZc5PR62ptQzSFdMsRMySzBf2tVZKKcjDA)](https://www.deepcode.ai/app/gh/contartec-team/spy-mock/_/dashboard?utm_content=gh%2Fcontartec-team%2Fspy-mock)

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

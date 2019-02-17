### leakage
---
https://github.com/andywer/leakage

```
mocha test/sample.test

npm install --save-dev leakage
yarn --deb leakage

mocha test/sample.test.js --heap-file heap-diff.json
```

```js
import myLib from 'my-lib'
import { iterate } from 'leakage'

describe('myLib', () => {
  it('does not leak when doing stuff', () => {
    iterate(() => {
      const instance = myLib.createInstance()
      instance.doStuff('foo', 'bar')
    })
  })
})


import test from 'tape'
import myLib from 'my-lib'
import { iterate } from 'leakage'

test('myLib does not leak when doing stuff', () => {
  iterate(() => {
    const instance = myLib.createInstance()
    instance.doStuff('foo', 'bar')
  })
})

import fetch from 'isomorphic-fetch'
import { iterate } from 'leakage'

describe('isomorphic-fetch', () => {
  it('does not leak when requesting data and parsing JSON', async () => {
    await iterate.async(async () => {
      const response = await fetch()
      await response.json()
    })
  })
})
```

```
```



# cfx-phishing-detect

<!-- [![Greenkeeper badge](https://badges.greenkeeper.io/MetaMask/cfx-phishing-detect.svg)](https://greenkeeper.io/) -->

Utility for detecting phishing domains targeting Conflux and Ethereum users. This is forked from cfx-phishing-detect. There's nothing changed yet in the list (same with https://github.com/MetaMask/eth-phishing-detect/blob/bdcd288d76dc574ff93e68d148f66d14f432d48c/src/config.json).

For checking why a given domain was blocked, try our interactive page [here](https://metamask.github.io/cfx-phishing-detect)

## Blocking Policy

We are constantly evolving the ideal policy that guides this list, but a few clearly defined rules have emerged. We will be quick and decisive to block websites that:
- Impersonate other known and established sites.
- Use their interfaces to collect user signing keys (especially cryptocurrency keys) and send them back to home servers.

There are other grounds for blocking, and we will ultimately do our best to keep our users safe.

### basic usage

```js
const checkForPhishing = require('cfx-phishing-detect')

const value = checkForPhishing('etherclassicwallet.com')
console.log(value) // true
```

### advanced usage

```js
const PhishingDetector = require('cfx-phishing-detect/src/detector')

const detector = new PhishingDetector({ whitelist, blacklist, fuzzylist, tolerance })
const value = detector.check('etherclassicwallet.com')
console.log(value)
/*
{
  type: "blacklist",
  result: true,
}
*/
```

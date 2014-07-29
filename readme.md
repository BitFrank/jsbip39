# jsBIP39

Ported from the reference implementation at https://github.com/trezor/python-mnemonic

Mnemonic code for generating deterministic keys

BIP39 Specification at https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki

# Usage

```
var m = new Mnemonic("english")

// Generate new mnemonics
var words = m.generate();
"canyon subway other flower grocery diagram cigar such custom rude couch horror"

// Check mnemonics are valid
var isValid = m.check(words);
true

// Generate BIP32 seeds from mnemonics
var seed = m.toSeed(words, "mysecretpassword");
"b4f0524dd1fcfc15ac2408fc9228df71c706aab238f8558d3b2bb3f4bce8ea25be9a3a6fc684a16ebfbb1240aee3decb404b856dd57298ce150441965c91c6e9"

// Generate mnemonics of different strengths
var lessWords = m.generate(64)
"safe soon minute hungry toss mobile"

// Test mnemonics are valid
var invalidMnemonic = "safe soon minute hungry toss cigar";
m.check(invalidMnemonic);
false
```

# Tests

Tests run in the browser.

```
$ cd /path/to/repo/
$ python -m SimpleHTTPServer
```

Open `http://localhost:8000/test/` in your browser

# Minifcation

This library was minified to jsbip39.min.js using Google Closure Compiler

`java -jar compiler.jar --js jsbip39.js --js_output_file jsbip39.min.js --language_in ECMASCRIPT5`

https://developers.google.com/closure/compiler/

# Thanks

This code uses asmCrypto
https://github.com/tresorit/asmcrypto.js

The people who authored and contributed to BIP39 and the reference client

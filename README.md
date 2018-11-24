Ascension Core integration/staging tree
=====================================

[![Build Status](https://travis-ci.org/ascension/bitcoin.svg?branch=master)](https://travis-ci.org/ascension/ascension)

https://ascensioncoin.org

What is Ascension Coin?
----------------

Ascension coin is an experimental digital currency that enables instant payments to
anyone, anywhere in the world. Ascension uses peer-to-peer technology to operate
with no central authority: managing transactions and issuing money are carried
out collectively by the network. Ascension Core is the name of open source
software which enables the use of this currency.

For more information, as well as an immediately useable, binary version of
the Ascension Core software, see https://ascensioncoin.org/en/download.

License
-------

Ascension Core is released under the terms of the MIT license. See [COPYING](COPYING) for more
information or see https://opensource.org/licenses/MIT.

Development Process
-------------------

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/bitcoin/bitcoin/tags) are created
regularly to indicate new official, stable release versions of Ascension Core.

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md).

The developer [mailing list](https://lists.linuxfoundation.org/mailman/listinfo/ascension-dev)
should be used to discuss complicated or controversial changes before working
on a patch set.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write [unit tests](/doc/unit-tests.md) for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run
(assuming they weren't disabled in configure) with: `make check`

There are also [regression and integration tests](/qa) of the RPC interface, written
in Python, that are run automatically on the build server.
These tests can be run (if the [test dependencies](/qa) are installed) with: `qa/pull-tester/rpc-tests.py`

The Travis CI system makes sure that every pull request is built for Windows, Linux, and OS X, and that unit/sanity tests are run automatically.

### Manual Quality Assurance (QA) Testing

Changes should be tested by somebody other than the developer who wrote the
code. This is especially important for large or high-risk changes. It is useful
to add a test plan to the pull request description if testing the changes is
not straightforward.

Translations
------------

Changes to translations as well as new translations can be submitted to
[Ascension Core's Transifex page](https://www.transifex.com/projects/p/bitcoin/).

Translations are periodically pulled from Transifex and merged into the git repository. See the
[translation process](doc/translation_process.md) for details on how this works.

**Important**: We do not accept translation changes as GitHub pull requests because the next
pull from Transifex would automatically overwrite them again.

Translators should also subscribe to the [mailing list](https://groups.google.com/forum/#!forum/ascension-translators).



[Dev info] Forking from Bitcoin
------------

This repository is a clone of https://github.com/bitcoin/bitcoin/tree/0.13.

Batch renaming steps:
1) Used Atom for case-sensitive replacing in this order:

```
bitcoin
Bitcoin
BITCOIN
BTC
```

2) And then fix some back:

```
The Ascension Core developers
The Ascension developers
#endif // ASCENSION_
#ifndef ASCENSION_
#define ASCENSION_
#include "ascension
ascension-config.h
AscensionUnits
.ascension.
CAscensionAddress
CAscensionSecret
CAscensionExtKeyBase
ASCENSION_CONF_FILENAME
ascensiond-res.rc
https://github.com/ascension/ascension/
https://github.com/ascension/bips/
https://ascension
_ASCENSION
ASCENSION_
_ascension.
ascension.qrc
libascension
ascensionconsensus
AscensionGUI
AscensionAddress
AscensionAmount
"ascension-core"
Ascension Core Developers
<name>ascension-core</name>
AscensionTestFramework
qt/locale/bitcoin
moc_ascension
qt/ascension
res/ascension
locale/bitcoin
test_ascension
test/ascension
```

3) Exclude folders.
Discovered by comparing bitcoin and Litecoin sources at the same branch (0.13)
Overwrite these files with original contents:
```
.tx
build-aux
contrib/init
contrib/verify-commits
cotrib/verifybinaries
depends
doc/release-notes
doc/gitian-building
All subfolders in “src” but “qt”, “rpc”, “test”, “wallet”
```

4) Some more replacements
```
"Satoshi"  ->  “Ascension”
github.com/ascension/ascension  ->  github.com/ascensioncoin/AscensionCoin
ASCENSIONS -> ASCENSION COINS
ascensions -> ascension coins
```


TODO:

1) Fix filenames/code (that got broken by batch renaming)
2) Add ASN images
3) Verify all compiles and works with BTC blockchain, but UI shows ASN
4) Add ASN chain params, ports
5) Add qubit hashing
6) Add POS
7) Add AscendChat
8) Add AscendSend ?

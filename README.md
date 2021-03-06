bcompare: Launches Beyond Compare via Wine
==========================================

Launching [Beyond Compare](http://www.scootersoftware.com) via `wine` itself is hard because of the need to
translate the arguments from Unix paths to Wine paths.

`bcompare` does that for you, using `winepath`. It also passes other helpful
options like `/leftreadonly`.

I'm using a Mac, but it might work on Linux too (let me know!).


Usage
-----

    bcompare diff remote local
    bcompare merge local remote base merged


Requirements
------------

- `wine` and `winepath` installed and available on the `PATH` (e.g. with [MacPorts](http://www.macports.org))
- `BCOMP_PATH` environment variable pointing to `BComp.exe`


Installation
------------

    git clone https://github.com/bchallenor/bcompare.git
    ln -s $PWD/bcompare/bcompare /usr/local/bin/bcompare


Integration with Git
--------------------

To use Beyond Compare with Git, put the following in your `~/.gitconfig`:

    [diff]
      tool = bcompare
    [difftool]
      prompt = false

    [merge]
      tool = bcompare
    [mergetool]
      prompt = false

    [difftool "bcompare"]
      cmd = bcompare diff "$LOCAL" "$REMOTE"
    [mergetool "bcompare"]
      cmd = bcompare merge "$LOCAL" "$REMOTE" "$BASE" "$MERGED"


License
-------

    Copyright (C) 2012 Ben Challenor <ben@challenor.org>

    Permission is hereby granted, free of charge, to any person obtaining a copy of
    this software and associated documentation files (the "Software"), to deal in
    the Software without restriction, including without limitation the rights to
    use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
    the Software, and to permit persons to whom the Software is furnished to do so,
    subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
    FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
    COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
    IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
    CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


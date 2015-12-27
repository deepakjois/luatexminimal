[LuaTeX] is a TeX-based computer typesetting system, which provides a Lua based scripting environment. However, it is not enough to merely have LuaTeX as a binary program to be able to produce fully typeset documents. Most people depend on software like [TeX Live] for document production, which provides LuaTeX (and many other TeX related programs) in a pre-configured environment, ready to be used. TeXLive is a bit unwieldy, and not suitable for experimenting with latest releases. It could also take up a large amount of space.

[LuaTeX]:http://www.luatex.org/
[TeX Live]:https://www.tug.org/texlive/

## _luatexminimal_ – a minimal environment for LuaTeX

A minimal installation of LuaTeX could be useful for experimentation and learning. Therefore, this repo provides a tree for a barebones LuaTeX installation that can compile simple plain TeX documents into PDF. You should be able to drop in a LuaTeX binary compiled from source into the root of the tree, set some environment variables (see below), and start using it.

_luatexminimal_ is largely inspired from Graham Douglas’ [series of blog posts](http://www.readytext.co.uk/?cat=30), so a lot of credit must go to him. It is also highly recommended that you read through the posts before attempting to use this repo.

### Usage
* Clone this repo.

* [Download a copy][dl] of the LuaTeX binary, or better still, [compile it from sources][svn]. The repo tree has currently been tested against LuaTeX Version beta-0.87.1, on OS X El Capitan.

[dl]:http://www.luatex.org/download.html
[svn]:https://foundry.supelec.fr/projects/luatex

* Drop the binary into the root of the tree and add it to the PATH.

* Set `TEXMFCNF` to point to the `texmf/web2c` folder in the cloned repo: ``export TEXMFCNF=`pwd`/texmf/web2c/``

* Optionally, set `KPATHSEA_DEBUG` to `-1`, to troubleshoot any path and file-finding issues: `export KPATHSEA_DEBUG=-1`

* Generate a `plain.fmt` file, by doing:
```
$> cd texmf/web2c

$> luatex --ini plain.tex
This is LuaTeX, Version beta-0.87.1 (TeX Live 2016/dev)  (INITEX)

(/Users/deepak/code/personal/luatex/luatexminimal/texmf/tex/plain/base/plain.te
x Preloading the plain format: codes, registers, parameters, fonts,
more fonts, macros, math definitions, output routines, hyphenation
(/Users/deepak/code/personal/luatex/luatexminimal/texmf/tex/generic/hyphen/hyph
en.tex))
*\dump
Beginning to dump on file plain.fmt
 (format=plain 2015.12.27)
…
50 preloaded fonts
No pages of output.
Transcript written on plain.log.
```
* Test the installation by doing: `luatex --fmt=plain --output-format=pdf  hello.tex`. It should produce a PDF file called `hello.pdf`.

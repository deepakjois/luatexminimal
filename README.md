[LuaTeX] is a TeX-based computer typesetting system, which provides a Lua based scripting environment. However, it is not enough to merely have LuaTeX as a binary program to be able to produce fully typeset documents. Most people depend on software like [TeX Live] for document production, which provides LuaTeX (and many other TeX related programs) in a pre-configured environment, ready to be used.

[LuaTeX]:http://www.luatex.org/
[TeX Live]:https://www.tug.org/texlive/

## _luatexminimal_ – a minimal environment for LuaTeX

A minimal installation of LuaTeX could be useful for experimentation and learning. Therefore, this repo provides a tree for a barebones LuaTeX installation that can compile simple plain TeX documents into PDF. You should be able to drop in a LuaTeX binary compiled from source into the root of the tree, set some environment variables (see below), and start using it.

_luatexminimal_ is largely inspired from Graham Douglas’ [series of blog posts](http://www.readytext.co.uk/?cat=30), so a lot of credit must go to him. It is also highly recommended that you read through the posts before attempting to use this repo.

### Usage

1. [Download a copy][dl] of the LuaTeX binary, or [compile it from sources][svn]. The repo tree has currently been tested against LuaTeX Version beta-0.87.1, on OS X El Capitan.

[dl]:http://www.luatex.org/download.html
[svn]:https://foundry.supelec.fr/projects/luatex

2. Clone this repo, drop the binary into the root of the tree and add it to the PATH.

3. Optionally, set `KPATHSEA_DEBUG` to `-1`, to troubleshoot any path and file-finding issues: `export KPATHSEA_DEBUG=-1`

4. Test the installation by doing: `luatex --fmt=plain --output-format=pdf  hello.tex`. It should produce a PDF file called `hello.pdf`.
